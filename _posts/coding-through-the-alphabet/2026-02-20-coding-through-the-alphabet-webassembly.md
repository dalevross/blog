---
layout: post
title: "Coding Through the Alphabet - Fibonacci in WebAssembly"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in WebAssembly (WAT). Part of Coding Through The Alphabet."
tags:
  - WebAssembly
  - WAT
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
---

WebAssembly (Wasm) is a binary instruction format for a stack-based virtual machine. The human-readable text format (WAT) is used here. The `fib` function is compiled to `.wasm` and called from Node.js.

## How to test

**Prerequisites:** WABT (WebAssembly Binary Toolkit) and Node.js

- Ubuntu/Debian: `sudo apt install wabt nodejs`
- macOS: `brew install wabt node`

```bash
node run.js
```

**Expected output:**
```
0
1
1
2
3
5
8
13
21
34
```

## Source Code

```wat
(module
  (func $fib (export "fib") (param $n i32) (result i32)
    (local $a i32)
    (local $b i32)
    (local $c i32)
    (local $i i32)
    (local.set $a (i32.const 0))
    (local.set $b (i32.const 1))
    (local.set $i (i32.const 0))
    (block $break
      (loop $loop
        (br_if $break (i32.ge_s (local.get $i) (local.get $n)))
        (local.set $c (i32.add (local.get $a) (local.get $b)))
        (local.set $a (local.get $b))
        (local.set $b (local.get $c))
        (local.set $i (i32.add (local.get $i) (i32.const 1)))
        (br $loop)
      )
    )
    (local.get $a)
  )
)
```
