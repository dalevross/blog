---
layout: post
title: Oh Hah Pi Day!
date: 2024-11-11 2:01 -0500
tags:
- Wikipedia Query
- Pi
- Pi Day
- 1915
description: Querying Wikipedia like a bawse!
comments: true
image: ogpi.png
twitter-image: ogpi.png
published: true
---

I've always been a fan of numbers for as long as I can remember. Later in my life I developed an obsession for pi
as chronicled in [my first blog post.][firstpost]. I also, due to my affinity for numbers found gematria appealing (more on this later).

Last night I happened upon the wikipedia page of [Charles Evans Hughes III][charles] and noticed he was born on March 14, 1915 (3/14/15). This of course made me smile! What a find for a pi lover. I was then curious about who else was born on this day. After a failed google search, I decided to ask Chat GPT how to do this. After a few rounds of prompts I was given the following sample code for the 

<div class="contain-inline-size rounded-md border-[0.5px] border-token-border-medium relative bg-token-sidebar-surface-primary dark:bg-gray-950"><div class="flex items-center text-token-text-secondary px-4 py-2 text-xs font-sans justify-between rounded-t-md h-9 bg-token-sidebar-surface-primary dark:bg-token-main-surface-secondary select-none">sparql</div><div class="sticky top-9 md:top-[5.75rem]"><div class="absolute bottom-0 right-2 flex h-9 items-center"><div class="flex items-center rounded bg-token-sidebar-surface-primary px-2 font-sans text-xs text-token-text-secondary dark:bg-token-main-surface-secondary"><span class="" data-state="closed"><button class="flex gap-1 items-center select-none py-1"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="icon-sm"><path fill-rule="evenodd" clip-rule="evenodd" d="M7 5C7 3.34315 8.34315 2 10 2H19C20.6569 2 22 3.34315 22 5V14C22 15.6569 20.6569 17 19 17H17V19C17 20.6569 15.6569 22 14 22H5C3.34315 22 2 20.6569 2 19V10C2 8.34315 3.34315 7 5 7H7V5ZM9 7H14C15.6569 7 17 8.34315 17 10V15H19C19.5523 15 20 14.5523 20 14V5C20 4.44772 19.5523 4 19 4H10C9.44772 4 9 4.44772 9 5V7ZM5 9C4.44772 9 4 9.44772 4 10V19C4 19.5523 4.44772 20 5 20H14C14.5523 20 15 19.5523 15 19V10C15 9.44772 14.5523 9 14 9H5Z" fill="currentColor"></path></svg>Copy code</button></span></div></div></div><div class="overflow-y-auto p-4" dir="ltr"><code class="!whitespace-pre hljs language-sparql">SELECT ?person ?personLabel ?birthDate WHERE {
  ?person wdt:P31 wd:Q5;  # Instance of human
          wdt:P569 "1990-01-01T00:00:00Z"^^xsd:dateTime.  # Birthdate
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
LIMIT 100
</code></div></div>
<style>
    -webkit-text-size-adjust: 100%;
    -webkit-tap-highlight-color: transparent;
    tab-size: 4;
    --main-surface-background: hsla(0,0%,100%,.95);
    --message-surface: hsla(0,0%,91%,.5);
    --composer-surface: var(--message-surface);
    --dot-color: var(--black);
    --text-primary: var(--gray-950);
    --text-secondary: #5d5d5d;
    --text-tertiary: var(--gray-400);
    --text-quaternary: var(--gray-300);
    --tag-blue: #08f;
    --tag-blue-light: #0af;
    --text-error: #f93a37;
    --text-danger: var(--red-500);
    --text-placeholder: rgba(0,0,0,.7);
    --surface-error: 249 58 55;
    --border-xlight: rgb(0 0 0/5%);
    --border-light: rgba(0,0,0,.1);
    --border-medium: rgba(0,0,0,.15);
    --border-heavy: rgba(0,0,0,.2);
    --border-xheavy: rgba(0,0,0,.25);
    --hint-text: #08f;
    --hint-bg: #b3dbff;
    --border-sharp: rgb(0 0 0/5%);
    --icon-secondary: #676767;
    --main-surface-primary: var(--white);
    --main-surface-primary-inverse: var(--gray-800);
    --main-surface-secondary: var(--gray-50);
    --main-surface-tertiary: var(--gray-100);
    --sidebar-surface-primary: var(--gray-50);
    --sidebar-surface-secondary: var(--gray-100);
    --sidebar-surface-tertiary: var(--gray-200);
    --sidebar-title-primary: rgba(40,40,40,.5);
    --sidebar-body-primary: #0d0d0d;
    --sidebar-icon: #7d7d7d;
    --link: #2964aa;
    --link-hover: #749ac8;
    --selection: #007aff;
    --sidebar-surface-floating-lightness: 1;
    --sidebar-surface-floating-alpha: .8;
    --sidebar-surface-pinned-lightness: .99;
    --sidebar-surface-pinned-alpha: 1;
    --spring-fast-duration: 667ms;
    --spring-fast: linear(0,.01942 1.83%,.07956 4.02%,.47488 13.851%,.65981 19.572%,.79653 25.733%,.84834 29.083%,.89048 32.693%,.9246 36.734%,.95081 41.254%,.97012 46.425%,.98361 52.535%,.99665 68.277%,.99988);
    --spring-common-duration: 667ms;
    --spring-common: linear(0,.00506 1.18%,.02044 2.46%,.08322 5.391%,.46561 17.652%,.63901 24.342%,.76663 31.093%,.85981 38.454%,.89862 42.934%,.92965 47.845%,.95366 53.305%,.97154 59.516%,.99189 74.867%,.9991);
    --spring-slow-bounce-duration: 1167ms;
    --spring-slow-bounce: linear(0,.00172 .51%,.00682 1.03%,.02721 2.12%,.06135 3.29%,.11043 4.58%,.21945 6.911%,.59552 14.171%,.70414 16.612%,.79359 18.962%,.86872 21.362%,.92924 23.822%,.97589 26.373%,1.01 29.083%,1.0264 31.043%,1.03767 33.133%,1.04411 35.404%,1.04597 37.944%,1.04058 42.454%,1.01119 55.646%,1.00137 63.716%,.99791 74.127%,.99988);
    --spring-bounce-duration: 833ms;
    --spring-bounce: linear(0,.00541 1.29%,.02175 2.68%,.04923 4.19%,.08852 5.861%,.17388 8.851%,.48317 18.732%,.57693 22.162%,.65685 25.503%,.72432 28.793%,.78235 32.163%,.83182 35.664%,.87356 39.354%,.91132 43.714%,.94105 48.455%,.96361 53.705%,.97991 59.676%,.9903 66.247%,.99664 74.237%,.99968 84.358%,1.00048);
    --spring-fast-bounce-duration: 1s;
    --spring-fast-bounce: linear(0,.00683 1.14%,.02731 2.35%,.11137 5.091%,.59413 15.612%,.78996 20.792%,.92396 25.953%,.97109 28.653%,1.00624 31.503%,1.03801 36.154%,1.0477 41.684%,1.00242 68.787%,.99921);
    --easing-common: linear(0,0,.0001,.0002,.0003,.0005,.0007,.001,.0013,.0016,.002,.0024,.0029,.0033,.0039,.0044,.005,.0057,.0063,.007,.0079,.0086,.0094,.0103,.0112,.0121,.0132 1.84%,.0153,.0175,.0201,.0226,.0253,.0283,.0313,.0345,.038,.0416,.0454,.0493,.0535,.0576,.0621,.0667,.0714,.0764,.0816 5.04%,.0897,.098 5.62%,.1071,.1165,.1263 6.56%,.137,.1481 7.25%,.1601 7.62%,.1706 7.94%,.1819 8.28%,.194,.2068 9.02%,.2331 9.79%,.2898 11.44%,.3151 12.18%,.3412 12.95%,.3533,.365 13.66%,.3786,.3918,.4045,.4167,.4288,.4405,.452,.4631 16.72%,.4759,.4884,.5005,.5124,.5242,.5354,.5467,.5576,.5686,.5791,.5894,.5995,.6094,.6194,.6289,.6385,.6477,.6569,.6659 24.45%,.6702,.6747,.6789,.6833,.6877,.6919,.696,.7002,.7043,.7084,.7125,.7165,.7205,.7244,.7283,.7321,.7358,.7396,.7433,.7471,.7507,.7544,.7579,.7615,.7649,.7685,.7718,.7752,.7786,.782,.7853,.7885,.7918,.7951,.7982,.8013,.8043,.8075,.8104,.8135,.8165,.8195,.8224,.8253,.8281,.8309,.8336,.8365,.8391,.8419,.8446,.8472,.8499,.8524,.855,.8575,.8599,.8625 37.27%,.8651,.8678,.8703,.8729,.8754,.8779,.8803,.8827,.8851,.8875,.8898,.892,.8942,.8965,.8987,.9009,.903,.9051,.9071,.9092,.9112,.9132,.9151,.9171,.919,.9209,.9227,.9245,.9262,.928,.9297,.9314,.9331,.9347,.9364,.9379,.9395,.941,.9425,.944,.9454,.9469,.9483,.9497,.951,.9524,.9537,.955,.9562,.9574,.9586,.9599,.961,.9622,.9633,.9644,.9655,.9665,.9676,.9686,.9696,.9705,.9715,.9724,.9733,.9742,.975,.9758,.9766,.9774,.9782,.9789,.9796,.9804,.9811,.9817,.9824,.9831,.9837,.9843,.9849,.9855,.986,.9866,.9871,.9877,.9882,.9887,.9892,.9896 70.56%,.9905 71.67%,.9914 72.82%,.9922,.9929 75.2%,.9936 76.43%,.9942 77.71%,.9948 79.03%,.9954 80.39%,.9959 81.81%,.9963 83.28%,.9968 84.82%,.9972 86.41%,.9975 88.07%,.9979 89.81%,.9982 91.64%,.9984 93.56%,.9987 95.58%,.9989 97.72%,.9991);
    --sidebar-inline-padding: 1rem;
    --sidebar-mask: linear-gradient(90deg,#000,#000 84%,transparent 89%,transparent);
    --white: #fff;
    --black: #000;
    --gray-50: #f9f9f9;
    --gray-100: #ececec;
    --gray-200: #e3e3e3;
    --gray-300: #cdcdcd;
    --gray-400: #b4b4b4;
    --gray-500: #9b9b9b;
    --gray-600: #676767;
    --gray-700: #424242;
    --gray-750: #2f2f2f;
    --gray-800: #212121;
    --gray-900: #171717;
    --gray-950: #0d0d0d;
    --red-500: #ef4444;
    --red-700: #b91c1c;
    --brand-purple: #ab68ff;
    color-scheme: light;
    --composer-footer_height: var(--composer-bar_footer-current-height,32px);
    --composer-bar_height: var(--composer-bar_current-height,52px);
    --composer-bar_width: var(--composer-bar_current-width,768px);
    --mask-fill: linear-gradient(180deg,#fff 0%,#fff);
    --mask-erase: linear-gradient(180deg,#000 0%,#000);
    --tw-prose-body: var(--text-primary);
    --tw-prose-headings: var(--text-primary);
    --tw-prose-lead: var(--text-primary);
    --tw-prose-links: var(--text-primary);
    --tw-prose-bold: var(--text-primary);
    --tw-prose-counters: var(--text-primary);
    --tw-prose-bullets: var(--text-primary);
    --tw-prose-hr: var(--border-xheavy);
    --tw-prose-quotes: var(--text-primary);
    --tw-prose-quote-borders: #e5e7eb;
    --tw-prose-captions: var(--text-secondary);
    --tw-prose-code: var(--text-primary);
    --tw-prose-pre-code: #e5e7eb;
    --tw-prose-pre-bg: #1f2937;
    --tw-prose-th-borders: #d1d5db;
    --tw-prose-td-borders: #e5e7eb;
    --tw-prose-invert-body: var(--text-primary);
    --tw-prose-invert-headings: var(--text-primary);
    --tw-prose-invert-lead: var(--text-primary);
    --tw-prose-invert-links: var(--text-primary);
    --tw-prose-invert-bold: var(--text-primary);
    --tw-prose-invert-counters: var(--text-primary);
    --tw-prose-invert-bullets: var(--text-primary);
    --tw-prose-invert-hr: var(--border-xheavy);
    --tw-prose-invert-quotes: var(--text-primary);
    --tw-prose-invert-quote-borders: #374151;
    --tw-prose-invert-captions: var(--text-secondary);
    --tw-prose-invert-code: var(--text-primary);
    --tw-prose-invert-pre-code: #d1d5db;
    --tw-prose-invert-pre-bg: rgba(0,0,0,.5);
    --tw-prose-invert-th-borders: #4b5563;
    --tw-prose-invert-td-borders: #374151;
    overflow-wrap: break-word;
    font-feature-settings: normal;
    font-variation-settings: normal;
    font-family: ui-monospace,SFMono-Regular,SF Mono,Menlo,Consolas,Liberation Mono,monospace!important;
    color: currentColor;
    font-size: .875em;
    font-weight: 400;
    line-height: 1.7142857;
    border: 0 solid #e3e3e3;
    box-sizing: border-box;
    --tw-border-spacing-x: 0;
    --tw-border-spacing-y: 0;
    --tw-translate-x: 0;
    --tw-translate-y: 0;
    --tw-rotate: 0;
    --tw-skew-x: 0;
    --tw-skew-y: 0;
    --tw-scale-x: 1;
    --tw-scale-y: 1;
    --tw-pan-x: ;
    --tw-pan-y: ;
    --tw-pinch-zoom: ;
    --tw-scroll-snap-strictness: proximity;
    --tw-gradient-from-position: ;
    --tw-gradient-via-position: ;
    --tw-gradient-to-position: ;
    --tw-ordinal: ;
    --tw-slashed-zero: ;
    --tw-numeric-figure: ;
    --tw-numeric-spacing: ;
    --tw-numeric-fraction: ;
    --tw-ring-inset: ;
    --tw-ring-offset-width: 0px;
    --tw-ring-offset-color: #fff;
    --tw-ring-color: rgba(69,89,164,.5);
    --tw-ring-offset-shadow: 0 0 #0000;
    --tw-ring-shadow: 0 0 #0000;
    --tw-shadow: 0 0 #0000;
    --tw-shadow-colored: 0 0 #0000;
    --tw-blur: ;
    --tw-brightness: ;
    --tw-contrast: ;
    --tw-grayscale: ;
    --tw-hue-rotate: ;
    --tw-invert: ;
    --tw-saturate: ;
    --tw-sepia: ;
    --tw-drop-shadow: ;
    --tw-backdrop-blur: ;
    --tw-backdrop-brightness: ;
    --tw-backdrop-contrast: ;
    --tw-backdrop-grayscale: ;
    --tw-backdrop-hue-rotate: ;
    --tw-backdrop-invert: ;
    --tw-backdrop-opacity: ;
    --tw-backdrop-saturate: ;
    --tw-backdrop-sepia: ;
    --tw-contain-layout: ;
    --tw-contain-paint: ;
    --tw-contain-style: ;
    scrollbar-color: var(--main-surface-tertiary) transparent;
    position: relative;
    border-radius: .375rem;
    border-width: .5px;
    border-color: var(--border-medium);
    background-color: var(--sidebar-surface-primary);
    --tw-contain-size: inline-size;
    contain: var(--tw-contain-size) var(--tw-contain-layout) var(--tw-contain-paint) var(--tw-contain-style);
</style>

[firstpost]: {% post_url 2013-08-16-pi-lovin %}
[charles]: https://en.wikipedia.org/wiki/Charles_Evans_Hughes_III


