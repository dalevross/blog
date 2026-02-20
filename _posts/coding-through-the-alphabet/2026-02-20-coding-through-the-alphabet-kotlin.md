---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Kotlin"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Kotlin. Part of Coding Through The Alphabet."
tags:
  - Kotlin
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Kotlin as part of the Coding Through The Alphabet series.
---

Kotlin is a modern, statically typed programming language from JetBrains that targets the JVM, Android, JavaScript, and native platforms.

## How to test

**Prerequisites:** Kotlin

- Ubuntu/Debian: `sudo apt install kotlin`
- macOS: `brew install kotlin`
- All platforms: https://kotlinlang.org/docs/command-line.html

```bash
kotlinc -script fibonacci.kts
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

```kotlin
var a = 0
var b = 1
repeat(10) {
    println(a)
    val c = a + b
    a = b
    b = c
}
```

Local Testing Screenshot
![Image][screenshot]

[screenshot]: {{ site.url }}/blog/images/kotlin.png
