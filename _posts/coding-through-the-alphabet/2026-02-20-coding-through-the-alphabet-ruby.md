---
layout: post
title: "Coding Through the Alphabet - Fibonacci in Ruby"
date: 2026-02-20
categories: coding-through-the-alphabet
summary: "Fibonacci sequence in Ruby. Part of Coding Through The Alphabet."
tags:
  - Ruby
  - Fibonacci
  - Coding Through The Alphabet
  - Programming Languages
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
description: Implementation of the Fibonacci sequence in Ruby as part of the Coding Through The Alphabet series.
---

Ruby is a dynamic, open source programming language focused on simplicity and productivity. It is the language that powers the Ruby on Rails web framework.

## How to test

**Prerequisites:** Ruby

- Ubuntu/Debian: `sudo apt install ruby`
- macOS: `brew install ruby`
- All platforms: https://www.ruby-lang.org/en/downloads/

```bash
ruby fibonacci.rb
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

```ruby
a, b = 0, 1
10.times do
    puts a
    a, b = b, a + b
end
```
