---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Bash"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Bash. Part of Coding Through The Alphabet."
tags:
  - Bash
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png

Bash (Bourne Again SHell) is the default shell and scripting language on most Linux distributions and macOS.

## How to test

**Prerequisites:** Bash (pre-installed on all Unix/Linux/macOS systems)

```bash
bash fibonacci.sh
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

```bash
#!/usr/bin/env bash
a=0
b=1
for i in $(seq 1 10); do
    echo $a
    c=$((a + b))
    a=$b
    b=$c
done
```
