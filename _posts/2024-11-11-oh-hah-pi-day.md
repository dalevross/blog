---
layout: post
title: Oh Hah Pi Day!
date: 2024-11-11 2:01 -0500
tags:
- Wikipedia Query
- Pi
- Pi Day
- "1915"
description: Querying Wikipedia like a bawse!
comments: true
image: ogpi.png
twitter-image: ogpi.png
published: true
---

I've always been a fan of numbers for as long as I can remember. Later in my life I developed an obsession for pi
as chronicled in [my first blog post.][firstpost]. I also, due to my affinity for numbers found gematria appealing (more on this later).

Last night I happened upon the wikipedia page of [Charles Evans Hughes III][charles] and noticed he was born on March 14, 1915 (3/14/15). This of course made me smile! What a find for a pi lover. I was then curious about who else was born on this day. After a failed google search, I decided to ask Chat GPT how to do this. After a few rounds of prompts I was given the following sample code for the [Wikidata Query Service][wqs]

<div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-sparql">SELECT ?person ?personLabel ?birthDate WHERE { <br>
  ?person wdt:P31 wd:Q5;  # Instance of human<br>
          wdt:P569 "1990-01-01T00:00:00Z"^^xsd:dateTime.  # Birthdate<br>
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }<br>
}<br>
LIMIT 100<br>
</code></div>

I of course checked my date of birth first by replacing 1990-01-01T00:00:00Z with 1984-09-18. Not all the people found have a dedicated entry on Wikipedia but the query finds records for sources. I found out that Rico Strong and I share a birthday. I was not familiar with his work, I promise.
<br>
I then moved on to my primary query,

<div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-sparql">SELECT ?person ?personLabel ?birthDate WHERE { <br>
  ?person wdt:P31 wd:Q5;  # Instance of human<br>
          wdt:P569 "1915-03-14T00:00:00Z"^^xsd:dateTime.  # Birthdate<br>
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }<br>
}<br>
LIMIT 100<br>
</code></div>

Now for a mildly interesting gematria finding. After noticing a few names, I found an entry where the personLabel was just the ID.
This wikidata entry for this is linked [here][wikidata]. I searched google for the Russian name listed Числов Александр Михайлович and found the [Russian wiki page][rwp] for the entry. After translating the page I found the anglicized name to be Aleksandr Mikhailovich Chistlov. I then went to the gematrinator website and plugged in the name.

Below is the Ordinal computation for the name
![Image][gemval]


# 313!
The Ordinal cipher is the most basic cipher where a = 1, b = 2, c= 3....z = 26.

So close to being 314. It made me think of my off by one birth record number EA 313 for someone who developed a love for pi.

[firstpost]: {% post_url 2013-08-16-pi-lovin %}
[charles]: https://en.wikipedia.org/wiki/Charles_Evans_Hughes_III
[wqs]: https://query.wikidata.org/
[wikidata]: https://www.wikidata.org/wiki/Q4516349
[rwp]: https://ru.wikipedia.org/wiki/%D0%A7%D0%B8%D1%81%D0%BB%D0%BE%D0%B2,_%D0%90%D0%BB%D0%B5%D0%BA%D1%81%D0%B0%D0%BD%D0%B4%D1%80_%D0%9C%D0%B8%D1%85%D0%B0%D0%B9%D0%BB%D0%BE%D0%B2%D0%B8%D1%87
[gemval]: {{ site.url }}/blog/images/313-Aleksandr_Mikhailovich_Chistlov.png