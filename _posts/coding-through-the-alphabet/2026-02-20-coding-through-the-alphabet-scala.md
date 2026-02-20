---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Scala"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Scala. Part of Coding Through The Alphabet."
tags:
  - Scala
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Scala as part of the Coding Through The Alphabet series.
---

Scala is a strong statically typed general-purpose programming language that supports both object-oriented and functional programming. It runs on the JVM.

## How to test

**Prerequisites:** Scala

- Ubuntu/Debian: `sudo apt install scala`
- macOS: `brew install scala`
- All platforms: https://www.scala-lang.org/download/

```bash
scalac fibonacci.scala -d fibonacci.jar && scala -cp fibonacci.jar fibonacci
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

```scala
object fibonacci extends App {
    var (a, b) = (0, 1)
    for (_ <- 0 until 10) {
        println(a)
        val c = a + b
        a = b
        b = c
    }
}
```
