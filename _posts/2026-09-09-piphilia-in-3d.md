---
layout: post
title: "Piphilia in 3D: Falling Blocks with Three.js"
date: 2026-09-09 02:57:29 -0400
categories: projects
description: "A self-playing 3D demo of my Piphilia falling-block pi game, rendered live with Three.js. Drag to orbit."
comments: true
tags: ["three.js", "piphilia", "webgl", "javascript"]
image: images/piphilia-in-3d-og.png
twitter-image: images/piphilia-in-3d-og.png
---

If you've played [Piphilia](https://tinyurl.com/piphilia) — my falling-block memory game where you tap the digits of pi in order — you know the look: rows of numbered blocks raining down, ten per row. I wondered what it would feel like in 3D, so I had Pi build it with Three.js.

What you see below is a self-playing demo. Each row falls from the sky; when it lands, the next digit of &pi; glows gold and the row clears. Drag to orbit around it.

<div id="piphilia-3d" style="position:relative;width:100%;height:520px;border-radius:12px;overflow:hidden;background:radial-gradient(1200px 600px at 50% 20%, #16213a 0%, #0a0e1a 60%, #060913 100%);margin:1.5em 0;">
  <div style="position:absolute;top:12px;left:16px;z-index:2;color:#e8ecf4;font-family:ui-monospace,Menlo,monospace;font-size:14px;line-height:1.7;pointer-events:none;">
    <div>Next digit of &pi;: <span id="piphilia-next" style="color:#ffd54f;font-weight:800;font-size:18px;">3</span></div>
    <div>Rows cleared: <span id="piphilia-cleared">0</span></div>
  </div>
  <div style="position:absolute;bottom:10px;right:14px;z-index:2;color:#8b93a7;font-family:ui-monospace,Menlo,monospace;font-size:11px;pointer-events:none;">drag to orbit</div>
</div>
<script type="importmap">
{"imports":{"three":"https://cdn.jsdelivr.net/npm/three@0.160.0/build/three.module.js","three/addons/":"https://cdn.jsdelivr.net/npm/three@0.160.0/examples/jsm/"}}
</script>
<script type="module">
import * as THREE from 'three';
import { OrbitControls } from 'three/addons/controls/OrbitControls.js';
import { RoundedBoxGeometry } from 'three/addons/geometries/RoundedBoxGeometry.js';

const PI = '3141592653589793238462643383279502884197169399375105820974944592';
const COLS = 10, GAP = 1.14, SPAWN_Y = 9.5, REST_Y = 0.62;

const container = document.getElementById('piphilia-3d');
const hudNext = document.getElementById('piphilia-next');
const hudCleared = document.getElementById('piphilia-cleared');

let renderer;
try {
  renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
} catch (e) {
  container.innerHTML = '<p style="color:#e8ecf4;padding:40px;font-family:monospace;">WebGL is not available in this browser.</p>';
  throw e;
}
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
renderer.domElement.style.display = 'block';
container.appendChild(renderer.domElement);

const scene = new THREE.Scene();
scene.fog = new THREE.Fog(0x070b16, 20, 42);

const camera = new THREE.PerspectiveCamera(45, 1, 0.1, 100);
camera.position.set(0, 6.8, 14.5);

const controls = new OrbitControls(camera, renderer.domElement);
controls.target.set(0, 2.4, 0);
controls.enableDamping = true;
controls.enablePan = false;
controls.minDistance = 9;
controls.maxDistance = 24;
controls.maxPolarAngle = Math.PI * 0.52;

scene.add(new THREE.AmbientLight(0x8fa3c7, 0.85));
const key = new THREE.DirectionalLight(0xffffff, 1.6);
key.position.set(6, 12, 8);
scene.add(key);
const cyan = new THREE.PointLight(0x22d3ee, 120, 40, 2);
cyan.position.set(-9, 5, 7);
scene.add(cyan);
const amber = new THREE.PointLight(0xffb347, 90, 40, 2);
amber.position.set(9, 3, 6);
scene.add(amber);

const grid = new THREE.GridHelper(30, 30, 0x2a4a73, 0x14263f);
grid.material.transparent = true;
grid.material.opacity = 0.55;
scene.add(grid);

function makeFace(digit, bg, fg) {
  const c = document.createElement('canvas');
  c.width = c.height = 256;
  const g = c.getContext('2d');
  g.fillStyle = bg;
  if (g.roundRect) { g.beginPath(); g.roundRect(0, 0, 256, 256, 36); g.fill(); }
  else { g.fillRect(0, 0, 256, 256); }
  g.fillStyle = fg;
  g.font = '800 150px ui-monospace, Menlo, monospace';
  g.textAlign = 'center';
  g.textBaseline = 'middle';
  g.fillText(String(digit), 128, 138);
  const t = new THREE.CanvasTexture(c);
  t.colorSpace = THREE.SRGBColorSpace;
  t.anisotropy = 8;
  return t;
}

const geo = new RoundedBoxGeometry(1, 1, 1, 4, 0.14);
const matNormal = [], matTarget = [];
for (let d = 0; d <= 9; d++) {
  matNormal.push(new THREE.MeshStandardMaterial({ map: makeFace(d, '#3a4d78', '#eef2fb'), roughness: 0.32, metalness: 0.25 }));
  matTarget.push(new THREE.MeshStandardMaterial({ map: makeFace(d, '#e2a92c', '#241703'), roughness: 0.3, metalness: 0.25, emissive: 0x8a5c0e, emissiveIntensity: 0.7 }));
}

let piIndex = 0, cleared = 0, row = null;

function shuffledDigits(target) {
  const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
  for (let i = digits.length - 1; i > 0; i--) {
    const j = (Math.random() * (i + 1)) | 0;
    const tmp = digits[i];
    digits[i] = digits[j];
    digits[j] = tmp;
  }
  const targetCol = (Math.random() * COLS) | 0;
  const at = digits.indexOf(target);
  digits[at] = digits[targetCol];
  digits[targetCol] = target;
  return digits;
}

function spawnRow() {
  const target = Number(PI[piIndex % PI.length]);
  const order = shuffledDigits(target);
  const meshes = [];
  for (let c = 0; c < COLS; c++) {
    const d = order[c];
    const mesh = new THREE.Mesh(geo, matNormal[d]);
    mesh.position.set((c - (COLS - 1) / 2) * GAP, SPAWN_Y + Math.random() * 1.5, 0);
    mesh.userData = { digit: d, col: c, glow: false };
    scene.add(mesh);
    meshes.push(mesh);
  }
  hudNext.textContent = String(target);
  row = { meshes: meshes, target: target, state: 'falling', t: 0 };
}

const clock = new THREE.Clock();

function tick() {
  requestAnimationFrame(tick);
  const dt = Math.min(clock.getDelta(), 0.05);
  const t = clock.elapsedTime;

  if (row) {
    row.t += dt;
    if (row.state === 'falling') {
      let landed = true;
      for (const m of row.meshes) {
        m.position.y -= dt * 6.5;
        m.rotation.y = Math.sin(t * 2 + m.userData.col) * 0.08;
        if (m.position.y > REST_Y) { landed = false; }
        else { m.position.y = REST_Y; }
      }
      if (landed) {
        row.state = 'landed';
        row.t = 0;
        for (const m of row.meshes) {
          if (m.userData.digit === row.target) {
            m.material = matTarget[m.userData.digit];
            m.userData.glow = true;
          }
        }
      }
    } else if (row.state === 'landed') {
      for (const m of row.meshes) {
        if (m.userData.glow) {
          const s = 1 + Math.sin(row.t * 9) * 0.07;
          m.scale.set(s, s, s);
        }
      }
      if (row.t > 1.4) { row.state = 'clearing'; row.t = 0; }
    } else if (row.state === 'clearing') {
      let done = true;
      for (const m of row.meshes) {
        const delay = Math.abs(m.userData.col - 4.5) * 0.07;
        const k = (row.t - delay) / 0.45;
        if (k < 1) { done = false; }
        if (k > 0) {
          const s = Math.max(0.001, 1 - Math.min(k, 1));
          m.scale.set(s, s, s);
          m.position.y += dt * 2.5;
          m.rotation.y += dt * 3;
        }
      }
      if (done) {
        for (const m of row.meshes) { scene.remove(m); }
        row = null;
        cleared++;
        hudCleared.textContent = String(cleared);
        piIndex++;
        setTimeout(spawnRow, 350);
      }
    }
  }

  controls.update();
  renderer.render(scene, camera);
}

function resize() {
  const w = container.clientWidth, h = container.clientHeight;
  if (!w || !h) { return; }
  renderer.setSize(w, h);
  camera.aspect = w / h;
  camera.updateProjectionMatrix();
}
new ResizeObserver(resize).observe(container);
resize();
spawnRow();
tick();
</script>

## How it works

The whole scene is plain Three.js — no build step, no framework. Rounded boxes get their digits from canvas textures (drawn once per digit, reused everywhere), rows are generated as a shuffled 0–9 with the next digit of &pi; swapped into a random column, and a tiny state machine runs each row through falling, landing, glowing, and clearing. OrbitControls gives you the drag-to-rotate for free. View source on this page if you want to steal it.

## The real game

The demo plays itself, but the actual [Piphilia](https://tinyurl.com/piphilia) needs you: rows fall, and you clear them by clicking the next correct digit of pi in the bottom row — 3, then 1, then 4, then 1... Click wrong and the block turns red. Get through all 3,142 digits and you win. Kudos if you do.
