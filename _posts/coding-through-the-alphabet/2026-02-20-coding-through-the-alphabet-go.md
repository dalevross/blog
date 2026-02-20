---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Go"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Go. Part of Coding Through The Alphabet."
tags:
  - Go
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

Go (also known as Golang) is an open-source programming language created by Google. It is statically typed, compiled, and designed for simplicity and efficiency.

## How to test

**Prerequisites:** Go

- Ubuntu/Debian: `sudo apt install golang-go`
- macOS: `brew install go`
- All platforms: https://go.dev/dl/

```bash
go run fibonacci.go
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

```go
package main

import "fmt"

func main() {
	a, b := 0, 1
	for i := 0; i < 10; i++ {
		fmt.Println(a)
		a, b = b, a+b
	}
}
```
