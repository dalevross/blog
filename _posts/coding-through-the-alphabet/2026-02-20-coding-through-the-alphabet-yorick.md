---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Yorick"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Yorick. Part of Coding Through The Alphabet."
tags:
  - Yorick
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Yorick as part of the Coding Through The Alphabet series.
---

Yorick is an interpreted programming language for scientific computing, developed at Lawrence Livermore National Laboratory. It is particularly strong at array operations and numerical computation.

## How to test

**Prerequisites:** Yorick

- Ubuntu/Debian: `sudo apt install yorick`
- macOS: `brew install yorick`

```bash
yorick -batch fibonacci.i
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

```yorick
a = 0;
b = 1;
for (i = 0; i < 10; i++) {
    write, format="%d\n", a;
    c = a + b;
    a = b;
    b = c;
}
```

Local Testing Screenshot
![Image][screenshot]

[screenshot]: {{ site.url }}/blog/images/yorick.png
