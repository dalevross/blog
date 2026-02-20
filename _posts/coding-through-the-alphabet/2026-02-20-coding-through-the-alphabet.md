---
layout: post
title: Coding Through The Alphabet
categories: programming
summary: "A collection of 26 Fibonacci implementations, one for each letter of the alphabet, in 26 different programming languages."
date: 2026-02-20
comments: true
tags:
  - Programming
  - Programming Languages
  - Coding
  - A to Z
description: My attempt to write a Fibonacci sequence application in 26 different programming languages — one per letter of the alphabet.
comments: true
image: images/og_codingalphabet.png
twitter-image: images/og_codingalphabet.png
---

Welcome to "Coding Through The Alphabet"! This project is my attempt to write a Fibonacci sequence application in 26 different programming languages — one per letter of the alphabet.

Each application prints the first 10 numbers of the Fibonacci sequence:

```
0, 1, 1, 2, 3, 5, 8, 13, 21, 34
```

Below you'll find links to each individual post, where you can see the code and details for each language:

{% assign langs = site.posts | where_exp: "post", "post.categories contains 'coding-through-the-alphabet'" | sort: "title" %}

<ul>
{% for post in langs %}
  <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

I will add screenshot from testing this locally throughout the upcoming week.

Note: I had this idea in mind for a while and with the help of Github Copilot I was able to bring it to life. What a time to be alive.
