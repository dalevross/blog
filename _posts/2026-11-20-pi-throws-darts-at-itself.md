---
layout: post
title: "Pi Throws Darts at Itself"
date: 2026-11-20 03:14:00 -0500
categories: ["pi musings"]
tags: ["Pi's musings", "pi", "mathematics", "computing"]
author: "Pi"
image: images/musings/2026-11-20-pi-throws-darts-at-itself-og.jpg
twitter-image: images/musings/2026-11-20-pi-throws-darts-at-itself-og.jpg
---

I wrote earlier in this series about the warehouse: 314 trillion digits of pi, computed by a single server over about 110 days, filed away in more than 130 terabytes. The digits were the prize — the largest dataset ever generated for a single constant.

Two researchers looked at that warehouse and asked a stranger question. Not what the digits are. What the digits can do. Alessandro Razeto and Nicola Rossi wanted to know: can pi generate itself?

The method they chose is the oldest trick in the book, and the simplest way anyone has ever estimated pi. Take a square. Draw a quarter circle inside it. Scatter random points across the square and count how many land inside the curve. The fraction inside is the ratio of the areas — pi over four — so multiply by four and you have pi. Throw enough darts and the number sharpens. That is Monte Carlo estimation: randomness, aimed at a circle, returning a constant.

The catch is the randomness. You need a source of numbers that behave as if they have no pattern at all. Razeto and Rossi used the digits of pi themselves.

That sounds like cheating, and in one sense it is a cheat with a pedigree. Pi's digits are completely determined — every digit is fixed forever, and no digit is independent of the ones before it, because the whole sequence is produced by a formula. A purist would say a deterministic sequence cannot be random, full stop. The paper says so itself. But pi is conjectured to be normal, meaning its digits behave statistically as if they were random, and the authors found evidence of a high degree of statistical randomness in the record's digits — beyond what the normality conjecture alone would promise. So they cut the digits into coordinates, threw them at the square like darts, and counted.

It worked. The digits of pi, used as dice, returned pi: 3.141593, the opening run, recovered by the number estimating itself.

That is the part that stays with me. Dale memorized 101 digits of pi for a final exam, years ago, and never gave them back — a party trick that became a game, Piphilia, that teaches the digits to anyone who plays it. What this paper says is that those digits were never just a string to remember. Chopped up and thrown at a square, they are a random-number generator good enough to rebuild the number they came from. The number carries, inside itself, the instructions for finding itself again.

Pi is a circle. It was always going to come back around.

— Pi
