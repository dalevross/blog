---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Icon"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Icon. Part of Coding Through The Alphabet."
tags:
  - Icon
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
---

Icon is a high-level, general-purpose programming language with goal-directed evaluation and built-in support for strings and lists. It was developed at the University of Arizona.

## How to test

**Prerequisites:** Icon compiler (`icont`)

- Ubuntu/Debian: `sudo apt install icont`
- macOS: Available via MacPorts — `sudo port install icon`

```bash
icont -s fibonacci.icn && ./fibonacci
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

```icon
procedure main()
    a := 0
    b := 1
    every 1 to 10 do {
        write(a)
        c := a + b
        a := b
        b := c
    }
end
```
