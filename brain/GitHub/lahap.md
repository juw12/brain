---
title: "lahap"
type: note
date: 2026-11-08
tags:
  - github
  - project/lahap
  - status/active
  - public
repo: "https://github.com/juw12/lahap"
visibility: public
updated: 2026-11-08
source: hone
claim: "Built Lahap: an offline-first food diary PWA you can search (have I eaten this, where, for how much), with Strava-style share cards and taste-matched buds"
role: author
evidence: [https://github.com/juw12/lahap, https://juw12.github.io/lahap/, https://juw12.github.io/p/lahap/]
publish: true
---

# lahap

> Lahap - a food diary you can search ("lahap" is Indonesian for eating with gusto)

- **Repo:** https://github.com/juw12/lahap (public, MIT)
- **Live:** https://juw12.github.io/lahap/ (add `?demo=1` for a sample fortnight)
- **Landing:** https://juw12.github.io/p/lahap/
- **Portfolio:** card on https://juwenlie.pages.dev/ (Apps)
- **Language:** JavaScript (vanilla, IndexedDB, service worker, canvas share cards)
- **Started:** 2026-11-07 · **last push:** 2026-11-08

## What it is

Log a meal fast (photo optional, dishes seen before prefill) whether you ate out, cooked at home or ordered in.
Search answers "have I eaten this?" with count, last time and place, average price and range, plate score and rating.
Insights: variety score (Simpson diversity), plate score by day, spend split, taste radar, cuisines, top places.
Share cards like Strava: Card / Receipt / Stats templates, Paper / Dark / Photo / Transparent backgrounds, Story 9:16 or Post 1:1.
Taste buds: match % from taste profiles, tag buds in meals (+10), plan a hangout by WhatsApp, "We went" (+25), bud levels.

Built to beat PlateDiary (private restaurant photo journal) and Mynu (home-cooking journal), in the same family as
[[GitHub/jeda]] (vs Sansa) and tally (share cards).

Honest limits: plate score is a rule of thumb, not nutrition advice; buds are sample profiles on this device only (no server yet).

## Quality

- 63/63 Playwright tests, slop_check 0 blockers / 0 warnings, app audit A1-A8 pass.
- /hone council (3 judges, frozen rubric): v0 7.85 -> r1 8.45 (kept) -> r3 shipped at 8.25 (same-session r1 re-score 8.20;
  r3 won 4 pairwise, lost 0). Plateau stop below the 8.5 target. r1 snapshot kept for rollback.

## Log

- 2026-11-08: /hone + full sync: repo, profile README (Promising), landing page, portfolio card. 2026-11-08 1138 lahap hone

## Next

- Phone diary hierarchy: tickets above the fold, demote Share week and the bud nudge.
- Buds onboarding: empty state and an "invite a real friend" step instead of the sample-profile caveat.
- Share-card personality: bolder brand mark, plate motif varies per dish.

See also: GitHub repos
