---
layout: post
title: "Coding Through the Alphabet - Fibonacci in TypeScript"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in TypeScript. Part of Coding Through The Alphabet."
tags:
  - TypeScript
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in TypeScript as part of the Coding Through The Alphabet series.

---

TypeScript is a strongly typed programming language that builds on JavaScript. It is developed and maintained by Microsoft and compiles to plain JavaScript.

## How to test

**Prerequisites:** Node.js and TypeScript compiler

- Install Node.js: https://nodejs.org/
- Install TypeScript: `npm install -g typescript`

```bash
tsc fibonacci.ts && node fibonacci.js
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

```typescript
let a: number = 0;
let b: number = 1;

for (let i = 0; i < 10; i++) {
  console.log(a);
  [a, b] = [b, a + b];
}
```

Local Testing Screenshot
![Image][screenshot]

[screenshot]: {{ site.url }}/blog/images/typescript.png
