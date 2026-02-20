---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Elixir"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Elixir. Part of Coding Through The Alphabet."
tags:
  - Elixir
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

Elixir is a dynamic, functional language built on the Erlang VM. It is designed for building scalable and maintainable applications.

## How to test

**Prerequisites:** Elixir

- Ubuntu/Debian: `sudo apt install elixir`
- macOS: `brew install elixir`

```bash
elixir fibonacci.exs
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

```elixir
defmodule Fibonacci do
  def run(n) do
    Stream.unfold({0, 1}, fn {a, b} -> {a, {b, a + b}} end)
    |> Enum.take(n)
    |> Enum.each(&IO.puts/1)
  end
end

Fibonacci.run(10)
```
