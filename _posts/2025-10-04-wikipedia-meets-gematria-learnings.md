---
layout: post
title: "When Wikipedia meets gematria, plus learnings"
date: 2025-10-04 08:50:00 -0400
description: A Wikipedia Gematria Value search tool, what I learned.
comments: true
image: image/og_wikigem.png
twitter-image: image/og_wikigem.png
tags: ["wikipedia", "gematria", "caddy", "cratedb", "docker"]
---

I wrote a [tool](https://wikigemdev.rosssquared.org) to find Wikipedia titles that match a given gematria value in one or more ciphers.

A while back, I found this [URL](https://dumps.wikimedia.org/enwiki/latest/enwiki-latest-all-titles-in-ns0.gz) that downloads a gzipped archive of a file that has all the latest titles listed as of some recent date. I then did some formatting to ensure it could be imported into my MySQL database safely. I also wrote a tool to compute the gematria values based on the ciphers available at [Gematrinator.com](https://www.gematrinator.com) and output them to another csv file. The import however proved to be very slow so I left the project for a while.

A few days ago a new friend mentioned crate-db and its ability to be very performant on large datasets. I thought this was a great opportunity to learn something new. I set up an instance of cratedb via docker and started my import. This was my first successful docker implementation as my previous interaction wasn't favourable. This time around it was fairly simple to get going. Isn't life fun when you can set up/troubleshoot with Claude 4.5, GPT-5 etc. to handle your every question?
This was my docker-compose file

```
services:
  cratedb:
    image: crate:latest
    container_name: cratedb
    ports:
      - "4200:4200"
      - "5432:5432"
    volumes:
      - cratedb_data:/data
      - C:/Users/dalev/dalevross/gitlocal/WikiPhraseLoader/bin/Debug/net6.0:/csv
      - E:/:/external_csv  # Add this line
    environment:
      - CRATE_HEAP_SIZE=4g
    restart: unless-stopped

volumes:
  cratedb_data:
```

The following was more or less what I needed for the imports.

```
-- Import phrases
COPY phrases (id, phrase_text)
FROM '/csv/phrases_with_id.csv'
WITH (format = 'csv', header = true);

-- Import ciphers
COPY ciphers (id, cipher_name, description)
FROM '/csv/ciphers.csv'
WITH (format = 'csv', header = true);

-- Import phrasegematriavalues
COPY phrasegematriavalues (phraseid, cipherid, gematriavalue)
FROM '/csv/gematria_nd.csv'
WITH (format = 'csv', header = true);
```

Now, my tool is .NET Web App that communicates with the cratedb instance using a React Front-End interfacing with a .NET Core Web API backend.

I'm running an instance locally simply using `dotnet wikigem.dll`. I port forwarded ports 80 and 443 on my router then created an A record on my company's domain for wikigemdev.rosssquared.org. I knew the development certificate woudn't be trusted publicly so I asked Claude what my options were to have a [Let's Encrypt](https://letsencrypt.org/) cert set up for my simple application. I didn't want to have to set up Apache or IIS (Windows 11 Home so not even possible). The winner was [Caddy](https://caddyserver.com/). I just needed to execute `caddy run` with a [CaddyFile](https://caddyserver.com/docs/caddyfile) as follows

```
wikigemdev.rosssquared.org {
    reverse_proxy localhost:5000
}
```

I have my .NET app serving on port 5000.

The app is very slow on some (most) queries and I have a timeout of 10s. But it works for some and for that I'm a relatively happy camper. So cratedb wasn't all I dreamed but I learned a few new things so it's a win.

Just something I think about all the time.

> Here is wisdom. Let him that hath understanding count the number of the beast: for it is the number of a man; and his number is Six hundred threescore and six.
>
> — Revelation 13:18 (KJV)
