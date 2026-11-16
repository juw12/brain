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
updated: 2026-11-09
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

## Landing page v2 (2026-11-09): a storyboard you can play
- https://juw12.github.io/p/teduh/ rebuilt by hand as "A day on Teduh": 8 numbered storyboard shots (slug lines, clock, camera notes, dashed camera-move arrows), every frame a real in-game render from `tests/storyboard_shots.py`.
- Playable on the page: tap tree, bush, scrap and rock in the frames; plant, water and harvest basil; craft plank, rope, wire, solar panel and planter; cross to Market Isle and sell to Sari; give materials to the sky bridge, wind tower and reef dock. 11 real goals (1-10 and 12 of 19) with the game's own yields, recipes, prices and rewards; waits sped up and labelled.
- Sticky goal card mirrors the game HUD (goal, pips, bag, credits, clock); progress saved in localStorage; English or Bahasa Indonesia goal text.
- Shot 08 energy chart runs the game's real daylight and energy formulas (panels, turbines, batteries, lamps) and says when the lamps would go dark.
- Call sheet section for the full game, How it's built, FAQ. Gates 1/1 pass, slop check 0 blockers (1 heuristic warning), Playwright play-through 11/11 goals, 0 console errors, no overflow at 1280 and 390.
- Site commit 23ff1b1, teduh commit 6ada565 (storyboard_shots.py).
- Round 2 (site 7580084): messages moved into the goal card, featured hero frame. Council 8.5.
- Round 3 (site 36a0461 + b929512): goal card docked in the sticky header (it takes the nav's place while you play, so nothing covers the page), wrap tally became a clapperboard slate, one hero CTA (play here; full game secondary). Council 8.8 (judges 8.67-9.0), up from 8.7 / 8.5. Play-through 11/11, 0 errors, no overflow.
- Left open from the judges: game goal numbers read out of order on the page (3, 4, 8) because they match the game's own numbering; hero frame has a flat sky.

## 2026-11-09 storyboard rounds 4-6 ("how to make it 10/10")
- R4 kept and live (site c6662ed): hero/shot 01 re-rendered at 07:12 so the sky reads blue (the game sky is a flat colour lerped by time of day; 06:30 sat mid-lerp grey), goal chips carry "Goal N" badges with a pop on completion, cut notes explain goal 8 on shot 3 and skipped goal 11, "Start the day" moved into the shot-1 card, "05 Craft" label. Council 8.83 (8.5-9.0) vs 8.8 best: within judge noise.
- R5 8.5 and R6 8.67 were not kept (keep-best). Saved candidate with verified fixes: HUD "Goal 3 - 2/11 done here", goal stays visible while the note shows, "+N more" bag chip, measured header height for anchors, chart axis label and legend, mobile hero shows the game frame under the headline, one-row mobile HUD.
- teduh commit a9eca3b: storyboard_shots.py renders g1 at clock 0 (07:12).
- Judges' remaining asks: unmistakable "this page is playable" cue above the fold, mobile HUD goal text truncation, a replay payoff after the wrap (energy challenges), one consistent clock in shot 08.

## v1.4.0 (2026-11-09): Clean skies, answering "does this beat Loftia?"
- Honest verdict: Teduh beats Loftia on access (free, browser and phone, offline, no account, no shop, no servers). Loftia still wins on scale, art, content and its shared world.
- Added small versions of Loftia's two defining systems. 8 smog heaps on 4 islands recycle into scrap, stone, fiber and sometimes wire, and the sky haze lifts as you clear them. A fully cleaned island blooms and pays 40 coins. A hen, goat and turtle trapped in heaps move to Home Isle and leave daily gifts.
- Journal has a new Clean skies tab (sky clarity, per-island progress, animal status). There are 3 new goals (22 total). Older saves keep their goal and never get a heap buried under something they built.
- Fixed h() flattening: the Island stats tab had been printing "[object HTMLElement]".
- Tests 103/103 (was 78). Commit 4da429d. Landing cb6b45d: "of 22" plus a Clean skies call-sheet row. Live verified: game sw teduh-v1.4.0, landing storyboard 11/11 goals.

## 1.5.0 Far Skies (2026-11-09)

Goal: beat Loftia on content scale (Juwen: "beat loftia in scale art content", variants allowed, no label).

- New `js/farskies.js` expands the data from a fixed seed: skyway project on Grove opens 40 far islands in 8 biomes.
- Counts vs Loftia (fan wikis, Nov 2026): crops 64 vs 50, fish 30 vs 28, animals 123 vs 115 pets, recipes 1,070 vs 736, villagers 33 vs 30 NPCs, islands 44 vs 3 districts.
- Most of the extra is variants: 3 cultivars per crop, two-ingredient dish pairings, 12 species x 10 colourings, biome islands, generated villagers.
- Art pass: ACES tone mapping, gradient sky dome with deep-blue night, cloud sea, instanced grass, night fireflies, per-biome palettes, distance culling of far islands.
- Cookstove search box (1,050 stove recipes), Journal Clean skies shows Far Skies bars, 25 goals (q_skyway, q_far, q_dishes).
- Tests 116/116 (13 new). Commit 0680a33; landing 9016ef3; live storyboard 11/11.
- Honest gap: Loftia is a shared MMO world with hand-made art; Teduh wins on counts, not on art quality.
