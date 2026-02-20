---
layout: post
title: "Coding Through the Alphabet - Fibonacci in AWK"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in AWK. Part of Coding Through The Alphabet."
tags:
  - AWK
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in AWK as part of the Coding Through The Alphabet series.

---

AWK is a domain-specific language designed for text processing. It is available on all Unix-like systems.

## How to test

**Prerequisites:** AWK (pre-installed on all Unix/Linux/macOS systems)

```bash
awk -f fibonacci.awk
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

```awk
BEGIN {
    a = 0
    b = 1
    for (i = 0; i < 10; i++) {
        print a
        c = a + b
        a = b
        b = c
    }
}
```

Local Testing Screenshot
![Image][screenshot]

[screenshot]: {{ site.url }}/blog/images/awk.png
