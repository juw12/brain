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
updated: 2026-11-16
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
- **Started:** 2026-11-13 · **last push:** 2026-11-16
- **Old addresses:** https://juw12.github.io/sumber/ and https://juw12.github.io/p/sumber/ redirect to the new pages (checked 2026-11-16); the GitHub repo URL redirects.

## What it is

A search page for questions where the source matters. The browser asks up to 23 public libraries directly (10 on every search, 13 more when the query calls for them);
there is no Telisik server, account, tracker or API key. Results are pooled and ranked with a formula
printed on the page, and each result can open the arithmetic behind its position.

- In the sources' own words: up to three sentences copied character for character from the top results.
- Before AI: one switch limits results to items dated up to 30 November 2022 (a date filter, not a detector).
- Lenses: All, Learn, Research, Build, Discuss re-weight the sources.
- Cite, search operators, bangs.
- In the browser: an install button where the browser offers one, address-bar search (OpenSearch), a place
  in the Android share sheet once installed. Tested in Chrome 157 and Firefox 150.0.2.
- Optional Stack Exchange key field in Settings (the key stays in the browser).
- Browser extension (optional, in `extension/`, Chrome, Edge and Firefox): Telisik as the new tab page,
  the address-bar keyword `tk`, right-click "Search Telisik" on selected text, and a toolbar button
  (Alt+Shift+K). One permission (`contextMenus`), no site access. Loaded by hand from the repo; not in
  the Chrome Web Store or addons.mozilla.org.

The niche: web results crowded with pages written to rank and sell (Bevendorff et al., ECIR 2024) and
answer engines whose citations often do not check out (Liu, Zhang, Liang 2023; Tow Center / CJR, March 2025).
Telisik only asks places with no shop window and prints only what a source wrote.

## Quality

State on 2026-11-16 (app commit `bfed69d`; the page itself is unchanged since `1ce489d`).

- Extension, robot checks, measured 2026-11-16 with `tools/extension_e2e.py`: 28/28 in bundled Chromium
  148.0.7778.96, in Chrome 157.0.8103.78 and in Edge 157.0.4341.46; 25/25 in Firefox 150.0.2
  (Playwright's build; no system Firefox is installed). node tests 160/160.
- Extension, real keyboard and mouse, measured 2026-11-16 with `tools/extension_real_input.py` (Ctrl+T,
  `tk` typed in the address bar, the real right-click menu, Alt+Shift+K, the real toolbar button): Chrome
  157.0.8103.78 25/25, Edge 157.0.4341.46 25/25, Firefox 150.0.2 (Playwright's build) 24/26. The two
  Firefox misses: the bubble takes no typing until one click in its box; the bubble says so in Firefox.
- Not tested: the Firefox that Mozilla releases, the live site behind the extension with real input, an
  extension installed from a store.
- The numbers below are from `1ce489d`, before the extension was added.

- node tests 146/146. Functional 67/67 in Chrome 157.0.8103.78 and 67/67 in Firefox 150.0.2. Full run with
  the visual matrix 445/445 at `d932892` on Chrome 157 (not re-run after two small follow-up commits that
  touched the manifest, a test and the README). Live 6/6 on the deployed URL: 64 results from 10 of 10
  sources in 4.0 s, no CSP violation, service worker active, Chrome itself reports no installability or
  manifest errors, page opens offline.
- Set 1 (seen, used for tuning, n = 72): MRR 0.824, right page first 78% (56 of 72), top 3 85%, top 10 92%.
  One first place lost against the round before (0.836, 57 of 72): "treaty of westphalia" fell from 1 to 5.
- Set 2 (seen, n = 64): MRR 0.639 to 0.697, first 56% to 64% (36 to 41 of 64), top 3 67% to 73%,
  top 10 78% to 81%.
- Set 3 (n = 50, written and first scored 2026-11-16, the only unseen number): MRR 0.586, first 50%
  (25 of 50), top 3 62%, top 10 72%. GitHub refused 3 and failed 1 of the 50. Asked again the same day with
  every source answering (now seen): MRR 0.616, first 52%, top 3 66%, top 10 76%.
- Head to head on set 3 as first scored, first 10 results (`tools/compare.mjs`): Telisik first 50%, MRR
  0.579; Wikipedia search alone 36%, 0.468; Mwmbl 14%, 0.174; Hacker News 6%, 0.073; GitHub 0.
- Where it loses: plain descriptions (n = 33). Wikipedia alone: first 42%, top 3 70%, top 10 82%, MRR 0.573.
  Telisik: 42%, 52%, 67%, 0.498.
- Where it wins: named things (n = 17). Telisik first 65%, top 3 82%, MRR 0.735; best single source
  (Mwmbl) 35%, 53%, 0.433.
- Two ranking experiments were dropped because they did not beat the shipped formula (the second tried 17
  settings over 186 questions: first place 114 to 124 against 122 shipped). `js/rank.js` is unchanged.

## Honest limits

- Not the best search engine overall. It is the best I could find for one narrow job: free, no account, ads
  or tracking, one query across 23 public libraries, verbatim quotes only, ranking arithmetic on show.
- It is a page plus an extension, not a browser. Chromium and Firefox are what it runs in, so it cannot
  beat them; it installs from them and plugs into their new tab page, address bar, right-click menu,
  toolbar and share sheet. On a real new tab the cursor starts in the address bar in Chrome, Edge and
  Firefox (measured). Each browser asks once whether to keep the new tab page.
- The test favours Telisik by construction: every right answer is a page inside a library it searches
  (mostly Wikipedia). The sets were written by an AI assistant and 50 unseen queries is a small sample.
- Google, Bing, ChatGPT and Perplexity were not measured: their terms forbid automated queries.
  Marginalia (502), Stract (404) and DuckDuckGo's instant-answer interface (timeout) did not answer on
  2026-11-16 from the network this ran on.
- Ranking is lexical. Questions that share no words with the page still miss: "how do airplanes stay in
  the air", "tallest mountain on earth", "largest planet in the solar system", "general rise in prices over
  time", "the smallest unit of life", "building blocks of proteins". New in set 3: "the planet closest to
  the sun" has Mercury at 32 and "deepest part of the ocean" has the Mariana Trench at 12.
  Fixing these needs a meaning model, which is not shipped.
- No news wire: GDELT answered 429 on 2026-11-16 and was not added. Government sources are UK and US only.
- Free API quotas are per visitor IP (Stack Exchange about 300 a day, GitHub about 10 a minute). The key
  field in Settings raises the Stack Exchange quota (about 10,000 a day per Stack Exchange's documentation);
  each user has to register a key himself, none is shipped.
- The extension is not in the Chrome Web Store or addons.mozilla.org: both need a developer account in
  Juwen's own name (Chrome's has a one-time registration fee, Firefox needs Mozilla signing). The zips are
  built by `tools/pack_extension.py` into `dist/`. In Firefox it loads as a temporary add-on that
  disappears when Firefox closes. The GitHub token field was left out on purpose.
- Income today is 0. Two hooks exist in `js/config.js` (support link, one labelled footer sponsor line);
  both are empty and need a payment account in Juwen's own name.
- The name got a web check only, not trademark clearance: nine small GitHub repos, a dance programme and
  an old TV programme use the word.

## Updates

- 2026-11-14: first release, hone pass and full sync - [commit](https://github.com/juw12/telisik/commit/9995114) · 2026-11-14 1020 sumber hone
- 2026-11-14: limits pass - 8 to 20 sources, measured ranking, saved copies, quota notes, Hacker News dedupe fix - [commit](https://github.com/juw12/telisik/commit/41fb9c2) · 2026-11-14 1339 sumber limits
- 2026-11-14: quality pass and rename to Telisik - 23 sources, blind test set, head-to-head table, new URLs - [commit](https://github.com/juw12/telisik/commit/a8db7c7) · 2026-11-14 1751 telisik quality rename
- 2026-11-16: leftovers and browser integration - install, address-bar search, share target, Stack Exchange key, third question set, GitHub follow-up fault shown - [commit](https://github.com/juw12/telisik/commit/d932892) · [commit](https://github.com/juw12/telisik/commit/6d6ed0a) · [commit](https://github.com/juw12/telisik/commit/1ce489d) · 2026-11-16 1109 telisik leftovers browser
- 2026-11-16: browser extension - new tab page, address-bar keyword `tk`, right-click search, toolbar button - [commit](https://github.com/juw12/telisik/commit/858db79) · 2026-11-16 1313 telisik browser extension
- 2026-11-16: extension tested with real keyboard and mouse - Chrome 25/25, Edge 25/25, Playwright Firefox 24/26, Firefox bubble hint, Edge robot run - [commit](https://github.com/juw12/telisik/commit/bfed69d) · 2026-11-16 1731 telisik real input tests
