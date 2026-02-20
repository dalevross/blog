---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Julia"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Julia. Part of Coding Through The Alphabet."
tags:
  - Julia
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

Julia is a high-level, high-performance, dynamic programming language well-suited to numerical analysis and computational science.

## How to test

**Prerequisites:** Julia

- Ubuntu/Debian: `sudo apt install julia`
- macOS: `brew install julia`
- All platforms: https://julialang.org/downloads/

```bash
julia fibonacci.jl
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

```julia
a = 0
b = 1
for _ in 1:10
    println(a)
    global a, b
    a, b = b, a + b
end
```
