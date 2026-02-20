---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Lua"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Lua. Part of Coding Through The Alphabet."
tags:
  - Lua
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

Lua is a lightweight, high-level, multi-paradigm scripting language designed primarily for embedded use in applications. It is widely used in game development.

## How to test

**Prerequisites:** Lua

- Ubuntu/Debian: `sudo apt install lua5.4`
- macOS: `brew install lua`

```bash
lua fibonacci.lua
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

```lua
local a, b = 0, 1
for _ = 1, 10 do
    print(a)
    a, b = b, a + b
end
```
