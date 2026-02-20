---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Zsh"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Zsh. Part of Coding Through The Alphabet."
tags:
  - Zsh
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

Zsh is a Unix shell and scripting language that extends Bourne shell with many improvements. It is the default shell on macOS and is widely used on Linux.

## How to test

**Prerequisites:** Zsh (pre-installed on macOS; available on all Unix/Linux systems)

- Ubuntu/Debian: `sudo apt install zsh`

```bash
zsh fibonacci.zsh
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

```zsh
#!/usr/bin/env zsh
a=0
b=1
for i in {1..10}; do
    echo $a
    c=$((a + b))
    a=$b
    b=$c
done
```
