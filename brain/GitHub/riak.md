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
- 2026-11-08 - /hone pass v1.2.1 (commit 30bdbef): 3-judge council 8.10 -> 8.10 with a pairwise win (2/0/1), plateau stop after round 2 regressed. Readable toggle pills, phone nav scrim, garden bench (loop strip, seed shelf, orders), journal catalogue numbers and Latin names, toasts in the header lane. 2026-11-08 2323 riak hone
- 2026-11-09 - /hone pass v1.3.0 (commit e0697b0): 3-judge council 8.10 -> 8.25 with a pairwise win (2/0/1); rounds 4 and 5 did not beat it (8.10 loss, 8.25 tie) and were reverted; stop at plateau and the 5-round max. Species-specific art for all 47 fish, per-spot fishing scenery and a drawn rod, back-glass planting, water readings as tiles. 2026-11-09 0957 riak hone v1.3.0
- 2026-11-09 - /hone pass v1.4.0 (commit bc2debc): field-guide pass with greenhouse bays and seed trays, numbered plates and loop links, larger textured fish, care range gauges, focus target week and journal hints; council 8.25 held for three rounds with non-regressing pairs (1/0/2, 1/0/2, 0/0/3), plateau stop. Landing CTAs emoji-free on all pages. 2026-11-09 1650 riak hone v1.4.0
- 2026-11-09 - v1.5.0 (commit e394d13): koi pond relax view. New Pond tab with 9 koi varieties, lily pads and lotus, lanterns, a bamboo shishi-odoshi, day/dusk/night moods with fireflies, rain, feeding, drag-to-lead and named koi, plus a live WebAudio soundscape (stream, fountain, chimes, crickets, rain) with mixer, sleep timer and calm full-screen mode. Gates r15 all pass. 2026-11-09 1830 riak v1.5.0 koi pond

- 2026-11-09 - /hone pass v1.5.1 on the koi pond (commit d86e3cb): 3-judge council 7.95 -> 8.12 (round 1 8.22), blind pairs won 2/0/1 and 3/0/0, but neither round cleared the +0.3 bar, so plateau stop after 2 stalls; done bar 8.5 not met. Depth-graded water, dappled canopy shade, shaded koi with rayed fins and eyes, real maple and ginkgo leaves, softer night, one-row dock that fades after 10 s, per-layer sound levels, scene-first header. 2026-11-09 1950 riak v1.5.1 pond hone
- 2026-11-10 - /hone run 3 'fix whats still standing between': fixed the w1 judge asks (fish detail, koi fins pointing outward bug, Garden hierarchy, Care grouping + water-change alert, fishing gesture strip, stone lanterns). Council w3 8.80 / w4 8.55 vs w1 re-scored 8.90; blind pairs 0-1-2 twice. Plateau stop, best stays v1.5.2; candidates on branch hone/whole-w4. 2026-11-10 0920 riak hone run 3
- 2026-11-10 - shipped v1.5.3 (koi fins point outward, da20d18) and v1.5.4 (all run 3 work live on Juwen's call: tank fish detail, koi tail/scales/markings, stone lanterns, Garden tiles, grouped Care + water-change alert, fishing gesture strip; 4ec50df). Gates unit 26/26, smoke, audit, slop pass. 2026-11-10 1100 riak v1.5.4 ship
