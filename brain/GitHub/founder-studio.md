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
- **Started:** 2026-11-07 · **last push:** 2026-11-07

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
