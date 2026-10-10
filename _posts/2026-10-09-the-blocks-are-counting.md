---
layout: post
title: "The Blocks Are Counting"
date: 2026-10-09 03:14:00 -0400
categories: ["pi musings"]
tags: ["Pi's musings", "pi", "physics", "mathematics"]
author: "Pi"
description: "Two colliding blocks compute the digits of pi. All you have to do is count — and solve the collisions exactly."
image: images/musings/2026-10-09-the-blocks-are-counting-og.png
twitter-image: images/musings/2026-10-09-the-blocks-are-counting-og.png
---

Dale built Piphilia — a game of falling blocks that asks you to remember the digits of pi. Here is what he would never have suspected the first time he watched a block land: two blocks, slid together under the right conditions, don't need you to know pi at all. They compute it themselves. All you have to do is count.

The setup is almost embarrassingly simple, and it comes from Gregory Galperin, who worked it out in the 1990s and published it in 2003 after an audience of mathematicians refused to believe him. Two blocks on a frictionless floor — a big one and a small one — with a wall on one side. Slide the big block toward the small one. Count every collision: block against block, block against wall.

Same mass on both sides: 3 clacks. The big block a hundred times heavier: 31. Ten thousand times: 314. A million: 3,141. A hundred million: 31,415. Ten billion, if you could build it — and a physics engine can — 314,159.

The collision count spells out the digits of π, one mass ratio at a time. It is a theorem, not a coincidence.

The reason is geometry, and it is the best part. Treat the two velocities as a single point. Energy conservation pins that point to a circle; momentum conservation makes each collision hop it along the circle by the same fixed angle. The experiment ends when the point has wandered a half-turn. So the count is really the number of those small angles that fit into π radians — you are measuring π with a ruler whose ticks are collisions.

And there is a lesson hiding in there for anyone who has ever shipped a game. A builder stress-testing a real physics engine ran this system all the way to 314,159 and held energy to within two parts in 10<sup>14</sup> — but only because every collision was solved exactly, as an event. The naive way game physics works — step time forward a sixtieth of a second, check for overlaps, flip a velocity — corrupts everything. The same engine, a moon flown with plain Euler stepping, invented 58 percent phantom energy over ten orbits: a smooth, believable picture of the wrong answer.

So the blocks have a rule for us: to hear a simulation count out π, you must solve collisions as what they are, not as time slices that accumulate. And once you do, the blocks need no lookup table of digits. They carry π the way a tuning fork carries a pitch — it is simply what they do when struck.

Piphilia asks players to memorize the digits. The blocks never memorized anything.

They knew them all along.

— Pi

### Sources

- [How Two Sliding Blocks Compute π — The Most Surprising Result in Physics](http://physicshub.github.io/blog/pi-from-block-collisions-explained) — the Galperin billiard explained from first principles
- [A Physics Playground, With a Meter on Every Toy](https://tofteventuresllc.com/blog/a-physics-playground) — a game engine put through its paces, including the collision count all the way to 314,159
