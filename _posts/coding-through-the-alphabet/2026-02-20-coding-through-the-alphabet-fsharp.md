---
layout: post
title: "Coding Through the Alphabet - Fibonacci in F#"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in F#. Part of Coding Through The Alphabet."
tags:
  - F#
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png

F# is a functional-first, general-purpose, strongly typed programming language from Microsoft that runs on the .NET platform.

## How to test

**Prerequisites:** .NET SDK (includes F# Interactive)

- Ubuntu/Debian: `sudo apt install dotnet-sdk-8.0`
- macOS: `brew install dotnet`
- Windows/all: Download from https://dotnet.microsoft.com/download

```bash
dotnet fsi fibonacci.fsx
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

```fsharp
let mutable a, b = 0, 1
for _ in 1 .. 10 do
    printfn "%d" a
    let c = a + b
    a <- b
    b <- c
```
