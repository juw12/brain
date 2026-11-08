---
title: "riak"
type: note
date: 2026-11-08
tags:
  - github
  - project/riak
  - status/active
  - public
repo: "https://github.com/juw12/riak"
visibility: public
updated: 2026-11-08
source: github-sync
claim: "Built Riak: a free, offline-first cozy aquarium web app (PWA) with real water care, fishing, breeding, a greenhouse and a coral reef lab"
role: author
evidence: [https://github.com/juw12/riak]
publish: true
---

# riak

> Riak - a cozy aquarium that lives in your browser ("riak" means ripple in Indonesian)

- **Repo:** https://github.com/juw12/riak (public, MIT)
- **Live:** https://juw12.github.io/riak/
- **Landing:** https://juw12.github.io/p/riak/
- **Language:** JavaScript (vanilla ES modules, canvas, service worker)
- **Started:** 2026-11-07 · **last push:** 2026-11-08

## What it is

A calm web aquarium you look after a few minutes a day. Real nitrogen-cycle water care (ammonia, nitrite, nitrate, test kits, water changes), fishing with a reel minigame in nine places, 47 species, breeding with mixed colours, aquascaping (16 plants, 8 hardscape pieces, 3 substrates, 3 tank sizes, a second tank and a reef room), a greenhouse for cuttings, a coral reef lab, daily care and orders, and a field journal. Read-only share links (#visit=) carry the tank inside the link. Free, no account, works offline, English and Bahasa Indonesia.

Built as a free answer to the iOS game "Fin & Fern: Cozy Aquarium", in the same idea family as [[GitHub/jeda]] (vs Sansa) and [[GitHub/teduh]] (vs Loftia).

## Quality

- 16/16 simulation unit tests plus a scan for purple hex values and emoji; smoke test with no console errors and no overflow at 390 and 1440 px; app audit A1-A8 pass; slop check 0 blockers.
- /design: "Field guide" direction (no purple, no emoji, green/earth palette).
- /hone: council-judged (3 judges) 7.35 -> 7.80; later rounds tied, so the loop stopped on a plateau below the 8.5 target. Weakest criteria: visual craft and polish (7 each). Log in the repo at docs/hone/refine_log.md.
- Not yet verified: long-term play balance over many days, and real phones (only emulated viewports were tested).

## Log

- 2026-11-08: shipped v3 (repo + Pages), portfolio card, landing page /p/riak/, profile README entry under Games.

See also: GitHub repos
- 2026-11-08 - Flick Fishing mechanics added (v1.1.0, commit 1c81e39): swipe-to-cast, crank reel, tension vs fish strength with drag, 5 baits + 5 lures, line upgrades, tournaments vs CPU with hot-seat, 12 quests, photo album with trophy cards, #duel= challenge links. 2026-11-08 1250 riak flick fishing
- 2026-11-08 - Depth pass v1.2.0 (commit 9b0a3d9), after Jeda: floating white cards with warm layered shadows, pill controls and floating nav, tank drawn as a glass box (perspective panes, receding floor, depth haze, fish floor shadows, rim, stand), fishing scenes with atmospheric perspective. 2026-11-08 1415 riak depth pass
