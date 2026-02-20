---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Nim"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Nim. Part of Coding Through The Alphabet."
tags:
  - Nim
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Nim as part of the Coding Through The Alphabet series.

---

Nim is a statically typed, compiled systems programming language that combines successful concepts from Python, Ada, and Modula.

## How to test

**Prerequisites:** Nim compiler

- Ubuntu/Debian: `sudo apt install nim`
- macOS: `brew install nim`
- All platforms: https://nim-lang.org/install.html

```bash
nim c -r fibonacci.nim
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

```nim
var a = 0
var b = 1
for _ in 0 ..< 10:
    echo a
    let c = a + b
    a = b
    b = c
```
