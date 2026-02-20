---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Haskell"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Haskell. Part of Coding Through The Alphabet."
tags:
  - Haskell
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

Haskell is a purely functional programming language with strong static typing and lazy evaluation. The Fibonacci sequence is expressed here using an infinite lazy list.

## How to test

**Prerequisites:** GHC (Glasgow Haskell Compiler)

- Ubuntu/Debian: `sudo apt install ghc`
- macOS: `brew install ghc`
- All platforms: https://www.haskell.org/downloads/

```bash
runghc fibonacci.hs
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

```haskell
fibs :: [Integer]
fibs = 0 : 1 : zipWith (+) fibs (tail fibs)

main :: IO ()
main = mapM_ print (take 10 fibs)
```
