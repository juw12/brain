---
title: "mise"
type: note
date: 2026-11-07
tags:
  - github
  - project/mise
  - status/active
  - public
repo: "https://github.com/juw12/mise"
visibility: public
updated: 2026-11-09
source: hone
claim: "Built Mise: a quiet kitchen game (home kitchen, or a small restaurant as chef, server or owner) with live-synthesised Web Audio ASMR, in plain HTML/JS"
role: author
evidence: [https://github.com/juw12/mise, https://juw12.github.io/mise/, https://juw12.github.io/p/mise/]
publish: true
---

# mise

> A cozy, ASMR-first cooking game: cook 8 recipes at home with no timer, or run a small restaurant as the chef, the server or the owner, in first or third person. Every sound is synthesised live with Web Audio. Sibling of [[GitHub/bilas|Bilas]].

- **Repo:** https://github.com/juw12/mise (public)
- **Play:** https://juw12.github.io/mise/ (also runs offline from index.html)
- **Landing:** https://juw12.github.io/p/mise/
- **Portfolio card:** https://juwenlie.pages.dev/ (Apps)
- **Stack:** plain HTML, CSS, JavaScript; Web Audio (no sample files); Playwright gates in tests/check.py, tests/nav_check.py, tests/audio_probe.py

## Log
- 2026-11-07: built and honed (game rubric 7.7 -> 8.55, three-model council, 14 gates pass); published to GitHub Pages.
- 2026-11-08: sound hone (4.45 -> 8.80): per-ingredient knife sounds, tool-specific stirring, heat-following sizzle, room reverb, Listen sampler.
- 2026-11-09: navigation hone (3.4 -> 9.88 peak, 9.7 final; 17 nav gates): Back button on every screen, Esc and browser/phone Back go one step up, confirm before losing progress (commits 23429f3, 0003740, 4244ce2, 3f5065c).
- 2026-11-09: synced: portfolio card (art juw12/portfolio c26df03, catalog juw12/projects 115999b), landing page https://juw12.github.io/p/mise/ (juw12.github.io d4e7ada), profile README Games entry (juw12/juw12 e85219d).
- 2026-11-09: continued: games hub juw12/game e55bb3a (Mise + Bilas cards), profile juw12/juw12 a9b1a87 ("All eight"), Vow portfolio card rebuilt to house style (juw12/portfolio 8881dbb, all 54 cards pass); nav gates now run in WebKit too (MISE_ENGINE, 17/17), new tests/device_emul.py (iPhone 13 WebKit + Pixel 7 Chromium, portrait + landscape, 28/28); mise c6bcdc5.
