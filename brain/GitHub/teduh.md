---
title: "teduh"
type: note
date: 2026-11-08
tags:
  - github
  - project/teduh
  - status/active
  - public
repo: "https://github.com/juw12/teduh"
visibility: public
updated: 2026-11-08
source: github-sync
claim: "Built Teduh: a free, offline-first 3D solarpunk sky-village life sim in the browser (PWA)"
role: author
evidence: [https://github.com/juw12/teduh]
publish: true
---

# teduh

> Teduh - a calm sky village you build with sun, wind and friends

- **Repo:** https://github.com/juw12/teduh (public)
- **Live:** https://juw12.github.io/teduh/
- **Landing:** https://juw12.github.io/p/teduh/
- **Language:** JavaScript (three.js)
- **Topics:** game, life-sim, solarpunk, cozy-game, threejs, pwa, offline-first, webrtc, indonesia, browser-game
- **Started:** 2026-11-07 · **last push:** 2026-11-08

## What it is

Free cozy life sim on floating islands: farm, fish, craft, run the island on solar and wind, decorate the house, help villagers, and build the sky village together with friends over peer-to-peer (WebRTC). No account, no shop, no ads; installs as an app and keeps working offline. English and Bahasa Indonesia.

Built as a free answer to Loftia (paid, Steam/console, account and shop). Same idea family as [[GitHub/jeda]] (inspired by Sansa).

## Quality

- 63/63 automated tests (Playwright, real browser).
- /design: "Field guide" direction (Fraunces + Figtree, green/earth palette, no purple, no emoji).
- /hone: council-judged 6.85 -> 7.55 (kept v1); later rounds tied or lost the pairwise check, so the loop stopped on a plateau below the 8.5 target. Log in the repo at docs/hone_log.md.
- Not yet verified: together mode across two separate browsers on an outside network.

See also: GitHub repos


## v1.2.0 (2026-11-08): guide, character creator, realistic people
- How to play guide (5 illustrated steps) before the first game; skippable, reopenable from the title and Settings.
- Character creator with live 3D turntable: 14 choices (build, 5 heights, 3 face shapes, 8 skin tones, eyes, 10 hairstyles incl. hijab, hair colour, facial hair, 5 tops, 4 bottoms, cloth and shoe colours) plus 6 starting looks.
- New procedural person (`js/character.js`): tapered limbs, deltoids, fingers, iris/pupil eyes with blinking lids, strand-textured hair, batik and sarong cloth. NPCs re-dressed (Sari hijab and sarong, Bayu jacket and beard, Lin batik).
- Look saved with the island, sanitised on load and when friends arrive (`js/look.js`).
- /hone v2 council: 4.4 -> 7.7 -> 7.8 (shipped) -> 7.5 (reverted). Target 8.5 not reached; stopped on a two-round plateau. Remaining asks: closer facial detail, hair at close range, guide art in the game's 3D style.
- Tests 83/83. Commit cc47e49. Landing page 57ea8e1.


## v1.3.0 (2026-11-08): clean UI polish, in-game guide pictures, face detail
- HUD and panels: translucent glass cards, labelled camera controls (Turn/Zoom), goal progress bar, gear Settings icon, scroll fade only when a panel actually scrolls.
- Item icons (`js/icons.js`, tinted per item), Bag grouped by kind with what each item grows into, sells for or is used for; Workbench recipe cards with All/Ready filter, need chips (check or "have N") and energy cost.
- How to play guide now uses real renders of the game world (5 WebP, 15-17 KB each, cached offline), re-rendered by `tests/guide_shots.py`.
- Faces: single-bridge nose, cheek blush, arched brows, cupid's-bow lips.
- /hone round 3 council: 7.42 (baseline, fixed instrument) -> 7.85 -> 8.0 (kept, pair 3-0) -> 8.0 / 7.85 (reverted). Target 8.5 not reached; stopped on a two-round plateau.
- Tests 86/86 (adds rendered emoji check, workbench WCAG AA contrast, guide picture check). Play-together verified across two browsers 5/5.
- Commit f6ad5c5, landing 40e22d9. Live verified v1.3.0, no console errors.
