---
layout: post
title: "npx pub-recs dalevross"
date: 2025-09-29 21:29:00 -0400
categories: npx
description: An npm package to show off recommendations.
comments: true
image: og_pub_recs.png
twitter-image: og_pub_recs.png
tags: ["recommendations", "JSON", "npm package", "npx pub-recs"]
---

Today I decided to check out what was hot on [Hacker News](https://news.ycombinator.com). The first thing that caught my eyes
was [Play snake in the URL address bar ](https://demian.ferrei.ro/snake/) which I thought was pretty cool. The next thing that made an impact was [Go ahead, write the “stupid” code](https://news.ycombinator.com/item?id=45408617). In the past, I loved to hack and make little tools/apps that would simplify tasks for myself and others. Life happened and I stopped.

I went over to LinkedIn and saw [David Neal's virtual card project](https://github.com/reverentgeek/reverentgeek-card) and decided to implement [my own](https://github.com/dalevross/dalevross-card)

Bolstered by the fact that it wasn't too complex to implement the card and the knowledge that I have coding agents to assist where I fall short, I remembered an idea I had in the past to share recommendations. Within a few hours, I had more or less what I had in mind implemented. I borrowed the idea of using public gists from the [jsonresume](jsonresume.org) project and here is a look at how it works. The initial idea was to make it available on the web with themes to display just like jsonresume but I thought this was a neat variation to attempt.

![Image][pubrecs]

This is a demo I did of it in action.

<iframe width="538" height="314" src="https://www.youtube.com/embed/C-E5WqyPOms" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The code is available [here](https://github.com/dalevross/recommendations) with a README that shows usage instructions.

[pubrecs]: {{ site.url }}/blog/images/og_pub_recs.png
