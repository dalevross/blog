---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Uiua"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Uiua. Part of Coding Through The Alphabet."
tags:
  - Uiua
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Uiua as part of the Coding Through The Alphabet series.
---

Uiua (pronounced "wee-wah") is a stack-based array programming language inspired by APL and BQN. It uses a unique set of Unicode glyphs for its built-in operations and is designed for concise, expressive array manipulation.

## How to test

**Prerequisites:** Uiua

Install via Cargo (Rust package manager):

```bash
cargo install uiua
```

Or download a pre-built binary from https://github.com/uiua-lang/uiua/releases

```bash
uiua run fibonacci.ua
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

```uiua
# Fibonacci sequence in Uiua
# ⍥⊡+ repeats ⊡+ (add-below) 10 times, collecting each initial value
# Starting from 1 and 0, the 10 collected values are the Fibonacci sequence
≡&p ⍥⊡+10 1 0
```
