---
layout: post
title: "Coding Through the Alphabet - Fibonacci in C"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in C. Part of Coding Through The Alphabet."
tags:
  - C
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png

C is a general-purpose, procedural programming language. It is one of the most widely used languages in systems programming.

## How to test

**Prerequisites:** GCC (install with `sudo apt install gcc` or `brew install gcc`)

```bash
gcc fibonacci.c -o fibonacci && ./fibonacci
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

```c
#include <stdio.h>

int main(void) {
    int a = 0, b = 1, c;
    for (int i = 0; i < 10; i++) {
        printf("%d\n", a);
        c = a + b;
        a = b;
        b = c;
    }
    return 0;
}
```
