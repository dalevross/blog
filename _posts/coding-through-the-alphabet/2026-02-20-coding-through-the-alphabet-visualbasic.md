---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Visual Basic"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Visual Basic. Part of Coding Through The Alphabet."
tags:
  - Visual Basic
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Visual Basic as part of the Coding Through The Alphabet series.
---

Visual Basic is a multi-paradigm, object-oriented programming language from Microsoft. Visual Basic .NET runs on the .NET platform and retains the readable, English-like syntax of classic Visual Basic.

## How to test

**Prerequisites:** .NET SDK

- Ubuntu/Debian: `sudo apt install dotnet-sdk-8.0`
- macOS: `brew install dotnet`
- Windows/all: https://dotnet.microsoft.com/download

```bash
dotnet run
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

```vbnet
Module Program
    Sub Main()
        Dim a As Integer = 0
        Dim b As Integer = 1
        Dim c As Integer
        For i As Integer = 0 To 9
            Console.WriteLine(a)
            c = a + b
            a = b
            b = c
        Next
    End Sub
End Module
```

Local Testing Screenshot
![Image][screenshot]

[screenshot]: {{ site.url }}/blog/images/visualbasic.png
