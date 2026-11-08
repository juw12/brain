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
claim: "Built Lahap: an offline-first food diary PWA you can search, with on-device food cut-outs (U-2-Net in the browser), nutrition estimates against a quiz-set goal, a Lab that turns typed/spoken/scanned ingredients into recipes, and Strava-style share cards"
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
- **Language:** JavaScript (vanilla, IndexedDB, service worker, canvas share cards, onnxruntime-web U-2-Net, tesseract.js, Web Speech)
- **Started:** 2026-11-07 · **last push:** 2026-11-08

## What it is

Log a meal fast (photo optional, dishes seen before prefill) whether you ate out, cooked at home or ordered in.
Search answers "have I eaten this?" with count, last time and place, average price and range, plate score and rating.
Insights: variety score (Simpson diversity), plate score by day, spend split, taste radar, cuisines, top places.
Share cards like Strava: Card / Receipt / Stats templates, Paper / Dark / Photo / Transparent backgrounds, Story 9:16 or Post 1:1.
Taste buds: match % from taste profiles, tag buds in meals (+10), plan a hangout by WhatsApp, "We went" (+25), bud levels.
Food-only photos (on-device cut-out), nutrition estimate + tips, Today bar vs goal, Lab recipes from typed / spoken /
scanned ingredients, and a 5-step goal quiz (Mifflin-St Jeor).

Built to beat PlateDiary (private restaurant photo journal) and Mynu (home-cooking journal), in the same family as
[[GitHub/jeda]] (vs Sansa) and tally (share cards).

Honest limits: nutrition is an estimate from typical portions, not medical advice; no dish recognition from photos;
food the exact tint of the plate can still be trimmed with it; buds are sample profiles on this device only (no server yet).

## Quality

- 134/134 Playwright tests (real cut-out + OCR runs), slop_check 0 blockers / 0 warnings, app audit A1-A8 pass.
- /hone council (3 judges, frozen rubric): v0 7.85 -> r1 8.45 (kept) -> r3 shipped at 8.25 (same-session r1 re-score 8.20;
  r3 won 4 pairwise, lost 0). Plateau stop below the 8.5 target. r1 snapshot kept for rollback.

## Log

- 2026-11-08: /hone + full sync: repo, profile README (Promising), landing page, portfolio card. 2026-11-08 1138 lahap hone
- 2026-11-08: queue follow-ups shipped (`7a883e4`): phone diary meals-first, buds invite step + no fake 0% match, share-card plate logo + per-dish plates. 2026-11-08 1157 lahap queue

- 2026-11-08: food-only photos, nutrition tips, Lab recipes, goal quiz (`7439c92`) + download progress (`025b11d`); landing, portfolio card and profile synced. 2026-11-08 2200 lahap photo nutrition lab quiz
- 2026-11-08: plate trim keeps white sides - learns the plate tint from its rim (`376e031`, sw lahap-v5). 2026-11-08 2240 lahap white sides
- 2026-11-08: Bahasa list scanning with the Indonesian OCR model (`b1faa09`, sw lahap-v6); landing copy `2b1c82a`. 2026-11-08 2300 lahap bahasa ocr

## Next

- Real-phone check: Add to Home Screen, camera photo, cut-out speed, voice in Bahasa, share-sheet PNG (needs Juwen's phone).
- Teach the Lab parser Indonesian spices and staples (serai, lengkuas, daun salam, terasi, kemiri).

See also: GitHub repos
