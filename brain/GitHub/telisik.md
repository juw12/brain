---
title: "telisik"
type: note
date: 2026-11-14
tags:
  - github
  - project/telisik
  - status/active
  - public
repo: "https://github.com/juw12/telisik"
visibility: public
updated: 2026-11-14
source: hone
aliases: [sumber, Sumber]
claim: "Built Telisik (first released as Sumber): a browser-only search page that sends one query to up to 23 public libraries (Wikipedia, Stack Exchange, Hacker News, GitHub, OpenAlex, Europe PMC, Internet Archive, Open Library and fifteen more), ranks the pooled results with a BM25-based formula shown on the page, and prints only text copied from the sources"
role: author
evidence: [https://github.com/juw12/telisik, https://juw12.github.io/telisik/, https://juw12.github.io/p/telisik/]
publish: true
---

# telisik

> Telisik - search the sources. Nothing generated, nothing sponsored. ("telisik" is Indonesian for "to look into closely"; the project was called Sumber until 2026-11-14)

- **Repo:** https://github.com/juw12/telisik (public, MIT)
- **Live:** https://juw12.github.io/telisik/ · how it works and the head-to-head table: https://juw12.github.io/telisik/about.html#compare
- **Landing:** https://juw12.github.io/p/telisik/
- **Portfolio:** card on https://juwenlie.pages.dev/ (Apps)
- **Language:** JavaScript (vanilla ES modules, no build step, no dependencies, PWA)
- **Topics:** federated-search, no-ai, privacy, pwa, search-engine, vanilla-js
- **Started:** 2026-11-13 · **last push:** 2026-11-14
- **Old addresses:** https://juw12.github.io/sumber/ and https://juw12.github.io/p/sumber/ now return 404; the GitHub repo URL redirects.

## What it is

A search page for questions where the source matters. The browser asks up to 23 public libraries directly (10 on every search, 13 more when the query calls for them);
there is no Telisik server, account, tracker or API key. Results are pooled and ranked with a formula
printed on the page, and each result can open the arithmetic behind its position.

- In the sources' own words: up to three sentences copied character for character from the top results.
- Before AI: one switch limits results to items dated up to 30 November 2022 (a date filter, not a detector).
- Lenses: All, Learn, Research, Build, Discuss re-weight the sources.
- Cite, search operators, bangs, OpenSearch (can be set as a browser's search engine), installable.

The niche: web results crowded with pages written to rank and sell (Bevendorff et al., ECIR 2024) and
answer engines whose citations often do not check out (Liu, Zhang, Liang 2023; Tow Center / CJR, March 2025).
Telisik only asks places with no shop window and prints only what a source wrote.

## Quality

- node tests 139/139, functional 58/58, visual gates 378/378 (320 to 1440 px, light and dark; run on system
  Chrome because the bundled Chromium failed to start), live 3/3 on the deployed URL (53 results, 9 of 10
  sources answered in 5.3 s; Stack Overflow was rate limited for the test IP).
- Old labelled set (n = 72, weights were fitted on it): MRR 0.777 to 0.836, right page first 74% to 79%,
  top 3 78% to 86%, top 10 88% to 92%. Cost: "theory of plate tectonics" fell from position 1 to 5.
- Blind set written after that tuning (n = 64: 31 named things, 33 plain descriptions). Tuned half
  (n = 32): MRR 0.493 to 0.555, first 41% to 50%. Held-out half (n = 32, run once): MRR 0.724, first 63%,
  top 3 81%, top 10 88%. All 64: MRR 0.639, first 56%, top 10 78%.
- Head to head on the held-out half, first 10 results (`tools/compare.mjs`): Telisik MRR 0.720, Wikipedia
  search alone 0.514, Hacker News alone 0.229, Mwmbl 0.135, Wiby 0.073, GitHub alone 0.000.
- Where it loses: plain descriptions. Held-out n = 12: Wikipedia alone first 67% and MRR 0.787, Telisik 50%
  and 0.656. Whole set n = 33: Wikipedia alone MRR 0.578, Telisik 0.538.
- Where it wins: named things, whole set n = 31: Telisik first 68%, best single source 35%.

## Honest limits

- Not the best search engine overall. It is the best I could find for one narrow job: free, no account, ads
  or tracking, one query across 23 public libraries, verbatim quotes only, ranking arithmetic on show.
- The test favours Telisik by construction: every right answer is a page inside a library it searches
  (mostly Wikipedia). The sets were written by an AI assistant and 32 held-out queries is a small sample.
- Google, Bing, ChatGPT and Perplexity were not measured: their terms forbid automated queries.
  Marginalia, Stract and DuckDuckGo's API did not answer; Wiby answered 133 of 136.
- Ranking is lexical. Questions that share no words with the page still miss: "how do airplanes stay in
  the air", "tallest mountain on earth", "largest planet in the solar system", "general rise in prices over
  time", "the smallest unit of life", "building blocks of proteins"; "why is the sky blue" lands at 39.
  Fixing these needs a meaning model, which is not shipped.
- No news wire (GDELT unreachable), government sources are UK and US only.
- Free API quotas are per visitor IP (Stack Exchange about 300 a day, GitHub about 10 a minute).
- Income today is 0. Two hooks exist in `js/config.js` (support link, one labelled footer sponsor line);
  both are empty and need a payment account in Juwen's own name.
- The name got a web check only, not trademark clearance: nine small GitHub repos, a dance programme and
  an old TV programme use the word.

## Updates

- 2026-11-14: first release, hone pass and full sync - [commit](https://github.com/juw12/telisik/commit/9995114) · 2026-11-14 1020 sumber hone
- 2026-11-14: limits pass - 8 to 20 sources, measured ranking, saved copies, quota notes, Hacker News dedupe fix - [commit](https://github.com/juw12/telisik/commit/41fb9c2) · 2026-11-14 1339 sumber limits
- 2026-11-14: quality pass and rename to Telisik - 23 sources, blind test set, head-to-head table, new URLs - [commit](https://github.com/juw12/telisik/commit/a8db7c7) · 2026-11-14 1751 telisik quality rename
