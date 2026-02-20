---
layout: post
title: "Coding Through the Alphabet - Fibonacci in D"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in D. Part of Coding Through The Alphabet."
tags:
  - D
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

D is a systems programming language with C-like syntax, combining the power of C with modern language features such as garbage collection and strong type safety.

## How to test

**Prerequisites:** GDC or LDC D compiler

- Ubuntu/Debian: `sudo apt install gdc`
- macOS: `brew install ldc`

```bash
gdc fibonacci.d -o fibonacci && ./fibonacci
```

Or with LDC:

```bash
ldc2 fibonacci.d -of=fibonacci && ./fibonacci
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

```d
import std.stdio;

void main() {
    int a = 0, b = 1, c;
    foreach (_; 0 .. 10) {
        writeln(a);
        c = a + b;
        a = b;
        b = c;
    }
}
```
