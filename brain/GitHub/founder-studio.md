---
title: "founder-studio"
type: note
date: 2026-11-08
tags:
  - github
  - project/founder-studio
  - status/active
  - public
repo: "https://github.com/juw12/founder-studio"
visibility: public
updated: 2026-11-08
source: github-sync
claim: "Built Founder Studio: a local 3D buyer-panel simulator for pre-launch ideas where every number is computed by open scripts, with a full in-browser demo"
role: author
evidence: [https://github.com/juw12/founder-studio, https://juw12.github.io/founder-studio/]
publish: true
---

# founder-studio

> Founder Studio: pressure-test a pre-launch business idea with a simulated buyer panel in a 3D studio. Pricing, unit economics and the verdict come from open scripts, not from the model's guess.

- **Repo:** https://github.com/juw12/founder-studio (public, MIT)
- **Live demo:** https://juw12.github.io/founder-studio/ (runs entirely in the browser)
- **Landing page:** https://juw12.github.io/p/founder-studio/
- **Portfolio card:** https://juwenlie.pages.dev/
- **Stack:** Python standard library server (`server.py`), three.js r160 front end, plain JS/HTML/CSS; optional OpenAI-compatible or Anthropic API for live panels
- **Started:** 2026-11-07 · **last push:** 2026-11-08

## How the online demo works

- `scripts/build_pages.py` builds `docs/` (GitHub Pages on `main:/docs`).
- `js/browser-backend.js` loads Pyodide 0.27.7 and runs the real `server.py` plus the skill scripts in the browser, so the demo uses the same code as the local app (no separate mock).
- Example verdict from the demo project: "Incomplete: no official panel; $4.76 per cup, 73% contribution" (computed by `compile.py`).

## Checks (2026-11-08)

- `check_demo.py` local + live, desktop and phone: PASS, 0 console errors, verdict computes.
- `test_api.py`: 0 failures.
- Landing page gates: DNA 1/1, gates 1/1, slop_check 0 blockers.

## Limits

- Synthetic respondents are not representative and not validated against real buyers (README "Known limits").
- First demo load downloads Pyodide (tens of MB), so it is slow on a weak connection.

## Log

- 2026-11-08: live demo, portfolio card, landing page, profile README entry 2026-11-08 0320 founder-studio live demo card landing
- 2026-11-08: review loop (reviewer bots critique and auto-fix the pitch, same buyers judge) + Graphite design pass 2026-11-08 0950 founder-studio hone

- 2026-11-08: hone s5 calm UI pass shipped (`e99f165`): single stats strip, flat feed, no symbol glyphs, prices to 2 decimals. Council 8.07 to 8.55, pair tie. Substack post ready in juw12/portfolio#31 (needs login).

## 2026-11-08 readable arena (hone, session J)
- Commit 7505061 on top of the calm pass e99f165: buyer roster (hover/click), idle queue preview in two rows with a QUEUE sign, steeper camera with tidy BUY/PASS piles, amber thinking ring, "decided so far" HUD.
- Council mean 7.98 on the merged tree (best round 8.33); target 8.5 not met. All gates A1-A8 pass.

## 2026-11-08 paper theme + interactive square (hone v2)
- Commits 8ac7871, 2ab09ba, Pages 71566ba: Cairn/Jeda paper theme with self-hosted fonts, warmer 3D square (paving, trees, benches, bunting, varied buyers), camera views, hover + click-to-inspect, after-run buyer spotlight.
- Rubric v2 (style gates S1-S4 + A1-A8) all pass; council 8.5 (target 8.5). 2026-11-08 2247 founder-studio hone

## 2026-11-09 queue round
- v2-r4 (0b4632c, Pages 8898802): sunflower BUY/PASS piles, phone arena controls row, clearer deal errors. Council 8.5.
- v2-r5 (c9133d4, Pages 587cb25 + c4af5e4): latest-decision line under the square on phones with an "All buyers" jump, inspector below the square on phones, bigger signs/labels on phones, 3D hover ring + selection pin, guided setup steps with Next, warmer light. Council 8.8 / 8.6 = 8.7, all gates pass.
- Portfolio card regenerated light (juw12/portfolio 16ee62a, catalog 69b5136); landing shot refreshed (juw12.github.io e491c31).
- Next: compact buyer-state strip on phones, walking state in the legend, collapse "How it works" after the first run, pitch preview in setup. 2026-11-09 1034 founder-studio queue round

## 2026-11-09 queue round 2 (plateau)
- v2-r7..r10 built and judged: label clash fix, thinking dot, walking state, tappable phone buyer tiles (32 px, initials), earlier decisions in the phone ticker, newest-decision ring in 3D.
- Scores 8.7 / 8.7 / 8.6 / 8.7 against best 8.8 (v2-r6); pair vote r6 1, r10 0, tie 2. Not shipped; live demo stays v2-r6 (9eba9a4).
- Work kept on branch hone/v2-r7-r10 for later reuse.
- Next: change the lever. Richer 3D scene detail, provenance labels on every number, a one-line mode hint by Quick sim / AI buyers / Replay. 2026-11-09 1251 founder-studio plateau

- 2026-11-09: hone v2-r11 scored 8.95 (new best, up from 8.8): richer 3D plaza with stone curb, fountain, neighbour stalls, string lights, crates and sacks; speed readout. Commits 5b4f3d4 + Pages b695c34, push pending (office proxy down). r12 (8.9) parked on hone/v2-r12.
- 2026-11-09: v2-r11 (8.95) pushed and live-checked. r12 (8.9) and r13 (8.4, phone bottom-sheet feed) parked on hone/v2-r12 and hone/v2-r13; loop stopped at plateau. Next: Founder Studio inside Cairn once the Cairn session finishes.
- 2026-11-09: fair re-test of r13 (phone bottom-sheet feed) with an extra tapped-state screenshot: pair vote r11 2 / r13 0 / tie 1. r11 stays live; queue done. Next: Founder Studio inside Cairn once the Cairn session ends.
- 2026-11-09: now runs inside Cairn on the Founder Studio page ([cairn PR #26](https://github.com/juw12/cairn/pull/26)); development continues in Cairn `docs/founder/`. Finished runs save to the brain as notes. 2026-11-09 2300 founder studio in cairn
- 2026-11-09: inside Cairn, three live steps now guide a first run and **write your own** opens setup ([cairn PR #27](https://github.com/juw12/cairn/pull/27)). 2026-11-09 2340 founder studio steps
- 2026-11-10: inside Cairn the studio now drops its own brand, the page lists saved panels and suggests the next test ([cairn PR #29](https://github.com/juw12/cairn/pull/29)); phone sheet ported ([cairn PR #28](https://github.com/juw12/cairn/pull/28)). 2026-11-10 1050 founder studio page hone
- 2026-11-10: inside Cairn the studio now uses Cairn's fields, buttons and tabs and follows its light or dark theme; opened on its own it looks as before ([cairn PR #33](https://github.com/juw12/cairn/pull/33)). 2026-11-10 2253 cairn sidebar vibe overview founder look
