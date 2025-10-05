---
layout: post
title: "Cleaning up twitter"
tags:
  - twitter cleanup
  - twitter
  - unfollow
description: I've hit the limit, so I've got some work to do.
comments: true
image: image/oghitdalimit.png
twitter-image: image/oghitdalimit.png
---

Over the years, I've used twitter in a way it was possibly not meant to be used. I didn't really dwell on my follower count too much. I however had/have an insatiable desire to know all the things, almost to an omniscient level. So I followed a looot of people to keep my finger on the pulse of the world. If twitter suggested it, I obliged.

This is frowned upon in some circles however, but honey badger don't... I actually saw a tweet from someone \*achoo\*@levelsio\*achoo\* about writing a script to auto-block people with a wonky ratio. While typing this up I decided to run a search and found another one of Pieter's creations. Smart fellow, but I probably met the mute list thanks to 2017.

<blockquote class="twitter-tweet" data-conversation="none"><p lang="en" dir="ltr">Okay so I made it:<br><br>✨ Blunble Bot ✨<br><br>&quot;Blunble&quot; is Korean slang for BLock UNBLock. If you block and unblock someone on Twitter, they stop following you. It&#39;s a polite way of getting rid of trolls. This bot does that to whoever you mute.<a href="https://t.co/s8w6VBTgNi">https://t.co/s8w6VBTgNi</a> <a href="https://twitter.com/naval?ref_src=twsrc%5Etfw">@naval</a> <a href="https://twitter.com/balajis?ref_src=twsrc%5Etfw">@balajis</a> <a href="https://t.co/9jz9I0ZTZA">pic.twitter.com/9jz9I0ZTZA</a></p>&mdash; ؜ (@levelsio) <a href="https://twitter.com/levelsio/status/1145691748913430528?ref_src=twsrc%5Etfw">July 1, 2019</a></blockquote>

Anyhoo, I saw a tweet from Anil Dash and my eyes lit up.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Hey, for folks who&#39;ve noticed — I&#39;m unfollowing everybody again as part of a fresh start for the new year. Please don&#39;t be hurt, it doesn&#39;t mean I don&#39;t love you or want to hear from you! Just a reset, and feel free to DM me if needed. More on unfollowing: <a href="https://t.co/dAudGTAdQ3">https://t.co/dAudGTAdQ3</a></p>&mdash; Anil Dash 🥭 (@anildash) <a href="https://twitter.com/anildash/status/1211144189032972289?ref_src=twsrc%5Etfw">December 29, 2019</a></blockquote>

I've been meaning to figure out twitter automation to run some analysis according to my own parameters but it just never happened.

Thanks to Anil, I now have a base to start from which should reduce the effort required. He also mentioned a [Glitch App][glitch-app] that I might just remix for the grand designs I have in mind.

For now I've hit my limit so in addition to the list suggestion made by Anil, I also decided to export my list for posterity.

First I exported the list to a markdown file.

```
t followings > my5000.markdown
```

Could have been text but hey, I'm feeling markdown. Maybe I'll style it later. Twitter reports 5000, but the file only had 4998. Interesting.

Now I'll pause a sec to run a regex transform on those handles to produce [this][c5000]

The below worked, I just needed to add the rest of the html markup.

```
sed -E 's/(^.+$)/<span><a class="twitter-follow-button" href="https:\/\/twitter.com\/\1" data-size="large"> Follow @\1
<\/a><\/span>/g' my5000.markdown > my5000.html
```

It's taking each line and slotting it into the markup for making handle links twitter follow buttons, and all that's left is to add the twitter SDK. I'm probably stepping into the "doing the most" territory right now but I do things to learn and sometimes just to do it.

For now you only get the ZZZs which is what I should have been doing when I started this.

Fun tip: Running js on 5000(4998) records, for certain use cases is possibly unwise. I'll likely insert paging/search with some GraphQL and maybe [React+TypeScript][tejas-talk]

The follow stuff was influenced by [another thing][convert-links] I did when I'd just moved to Kansas City, MO.

Here ends the reading of Phase 1. I won't be unfollowing everyone, so I'll need to map out the criteria for nixing. I'm a people hoarder, I find value in every one. Brands, weeeell!

<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

[glitch-app]: https://tokimeki-unfollow.glitch.me/
[c5000]: https://dalevross.com/blog/my5000.html
[tejas-talk]: https://www.youtube.com/watch?v=LUHecE-kO9s

[convert-links]: {% post_url 2013-10-01-converting-twitter-links-to-follow %}
