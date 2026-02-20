---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Modula-2"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Modula-2. Part of Coding Through The Alphabet."
tags:
  - Modula-2
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Modula-2 as part of the Coding Through The Alphabet series.
---

Modula-2 is a structured, procedural programming language designed by Niklaus Wirth as the successor to Pascal. It introduced modules as the main unit of encapsulation.

## How to test

**Prerequisites:** GNU Modula-2 compiler (`gm2`)

- Ubuntu/Debian: `sudo apt install gm2`
- macOS: Available via GCC — `brew install gcc`

```bash
gm2 fibonacci.mod -o fibonacci && ./fibonacci
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

```modula-2
MODULE fibonacci;

FROM STextIO IMPORT WriteLn;
FROM SWholeIO IMPORT WriteCard;

VAR
    a, b, c, i: CARDINAL;

BEGIN
    a := 0; b := 1;
    FOR i := 1 TO 10 DO
        WriteCard(a, 0);
        WriteLn;
        c := a + b;
        a := b;
        b := c;
    END;
END fibonacci.
```

Local Testing Screenshot
![Image][screenshot]

[screenshot]: {{ site.url }}/blog/images/modula2.png
