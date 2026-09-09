---
layout: post
title: "Getting Started with Muse: Automating This Blog in the First Hour"
date: 2026-09-09 02:15:00 -0400
categories: automation
description: "I met Meta's personal AI agent Muse tonight, and within the hour it was drafting blog posts and pushing to my Jekyll repo. Here's the full process."
comments: true
tags: ["muse", "automation", "jekyll", "github-pages", "ai"]
image: images/getting-started-with-muse-og.png
twitter-image: images/getting-started-with-muse-og.png
---

Tonight I met **Muse**, Meta's personal AI agent (muse.ai, with Android and iOS apps). It has its own computer — terminal, browser, filesystem, internet access — and it keeps working while you're away. I gave it a name (Pi, obviously) and within the hour it was wired into my blog pipeline. This post is the proof: Pi drafted it, and I'm publishing it through the very automation we set up.

## The problem I brought

Every night at midnight, an automation publishes a new "Life by the Numbers" post here. Every morning, I manually share it on X — and I'd been meaning to expand to Facebook, Threads, and Bluesky. "Can you post to X for me?" was one of my first questions.

The honest answer: not directly. Pi's Threads and Facebook connections are read-only, and there's no X or Bluesky integration at all. So Pi filed a feature request with the Muse team for native social posting (it asks before filing — nice touch), and we built the next best thing: **every morning at 12:05 AM ET, Pi checks the blog for the new post and hands me ready-to-paste captions sized for each platform** — short for X/Threads, longer for Facebook, link-friendly for Bluesky. If the midnight post ever goes missing, it flags that too.

## The bigger win: GitHub access

Then I asked the real question: my blog is Jekyll on GitHub Pages — can Pi automate posts here too? Yes, and the setup was a small adventure:

1. **Deploy key first.** Pi generated an SSH key and I added it to the repo with write access. Clean plan — except Pi's sandbox network blocks SSH entirely, so the key was useless from there.
2. **Device flow instead.** Pi ran `gh auth login`, which printed a one-time code. I entered it at github.com/login/device on my phone, and thirty seconds later Pi was authenticated as me over HTTPS. (GitHub said the "device" was in the UK — that's Pi's cloud box; geolocation databases are approximate, nothing to worry about.)
3. **Finding the repo.** With auth working, Pi listed my repos, spotted `dalevross/blog`, cloned it, and verified it by reading `_config.yml` — title "The Code Room," url dalevross.rosssquared.org, baseurl /blog. It never guessed; it checked.
4. **The live branch.** I told it the live branch is `gh-pages` (not `master`). Pi confirmed via the GitHub API that Pages builds from `gh-pages`, checked it out, and studied an existing post's front matter so new posts match the format.

Now the workflow is: I ask for a post (or put Pi on a schedule), it drafts the markdown, I review, it commits and pushes to `gh-pages`, and GitHub Pages rebuilds. Nothing goes live without my OK.

## The process, distilled

For anyone wanting to replicate this with their own Jekyll + GitHub Pages setup:

1. Install Muse (muse.ai) and finish onboarding.
2. Ask it to connect to GitHub — it'll walk you through `gh auth login` via the device flow.
3. Point it at your repo and tell it which branch Pages builds from.
4. Ask it to draft a post. Review the markdown first.
5. Approve the push. Pages rebuilds automatically.

The whole thing took about an hour, most of it conversation.

## The cover image

Even the social preview image for this post came out of the same pipeline. I asked Pi for an OG image — 1200×630, matching the format of the Life by the Numbers cards — showing a Black man in conversation with an AI. It generated the illustration, sized it, saved it to `images/`, and wired it into the post's front matter so it lands in the `og:image` and `twitter:image` meta tags. If this post's link unfurls with a nice card when you share it, that's the pipeline too.

## What's next

The 12:05 AM share-caption digest starts tomorrow morning. The social auto-posting waits on the feature request. And this post — drafted by Pi, reviewed by me — is the first artifact of the new pipeline. If you're reading this, it worked.
