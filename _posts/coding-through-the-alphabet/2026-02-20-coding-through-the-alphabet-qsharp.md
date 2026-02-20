---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Q#"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Q#. Part of Coding Through The Alphabet."
tags:
  - Q#
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Q# as part of the Coding Through The Alphabet series.
---

Q# is a domain-specific programming language from Microsoft used for expressing quantum algorithms. It also supports classical computation, as demonstrated here.

## How to test

**Prerequisites:** Python 3 and the `qsharp` package

```bash
pip install qsharp
```

```bash
python3 run.py
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

```qsharp
// Fibonacci sequence in Q#
// Run with: python3 run.py

operation Main() : Int[] {
    mutable a = 0;
    mutable b = 1;
    mutable results : Int[] = [];
    for _ in 0 .. 9 {
        set results += [a];
        let c = a + b;
        set a = b;
        set b = c;
    }
    return results;
}
```

Local Testing Screenshot
![Image][screenshot]

[screenshot]: {{ site.url }}/blog/images/qsharp.png
