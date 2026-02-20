---
layout: post
title: "Coding Through the Alphabet - Fibonacci in OCaml"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in OCaml. Part of Coding Through The Alphabet."
tags:
  - OCaml
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

OCaml is a general-purpose, multi-paradigm programming language that extends the ML language with object-oriented features. It emphasizes safety and expressiveness.

## How to test

**Prerequisites:** OCaml

- Ubuntu/Debian: `sudo apt install ocaml`
- macOS: `brew install ocaml`
- All platforms: https://ocaml.org/install

```bash
ocaml fibonacci.ml
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

```ocaml
let () =
  let a = ref 0 and b = ref 1 in
  for _ = 0 to 9 do
    Printf.printf "%d\n" !a;
    let c = !a + !b in
    a := !b;
    b := c
  done
```
