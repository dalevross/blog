---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Python"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Python. Part of Coding Through The Alphabet."
tags:
  - Python
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
---

Python is a high-level, general-purpose programming language known for its clean syntax and readability. It is one of the most widely used languages in the world.

## How to test

**Prerequisites:** Python 3

- Ubuntu/Debian: `sudo apt install python3`
- macOS: `brew install python`
- Windows: https://www.python.org/downloads/

```bash
python3 fibonacci.py
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

```python
a, b = 0, 1
for _ in range(10):
    print(a)
    a, b = b, a + b
```
