---
title: "mlbb-blame"
type: note
date: 2026-11-11
tags:
  - github
  - project/mlbb-blame
  - status/active
  - public
repo: "https://github.com/juw12/mlbb-blame"
visibility: public
updated: 2026-11-12
source: hone
claim: "Built Who Threw?: a Mobile Legends match analyzer that gives each player a role-aware 0-10 score from the end-screen stats, splits blame (loss) or credit (win) into shares that add up to 100%, explains each verdict in numbers, and shares a result image to the squad chat"
role: author
evidence: [https://github.com/juw12/mlbb-blame, https://juw12.github.io/mlbb-blame/, https://juw12.github.io/p/mlbb-blame/]
publish: true
---

# mlbb-blame

> Who Threw? - settle who threw (or carried) your Mobile Legends match with numbers

- **Repo:** https://github.com/juw12/mlbb-blame (public, MIT)
- **Live:** https://juw12.github.io/mlbb-blame/
- **Landing:** https://juw12.github.io/p/mlbb-blame/
- **Portfolio:** card "Who Threw?" (Apps)

## What it does
- Fill from a screenshot or pasted text: copy the text out of the end-of-match screenshot (Live Text / Google Lens) and tap Paste from clipboard, or let the app read the image (Tesseract.js, on the phone). Hero-name list splits collapsed OCR spacing; filled cards are highlighted for checking.
- Role-aware scoring: each stat (gold, hero damage, damage taken, turret damage, kill participation, deaths, KDA) as a share of the team total vs what that role usually gets.
- Blame share in a loss proportional to (10 - score)^2, credit share in a win to score^2; displayed shares always add up to exactly 100%.
- Role-aware KDA target (2.5 Roam/EXP, 3 others), visible actual-vs-expected numbers per stat, warnings for blank stats or fewer than 5 players.
- Confidence call with named thresholds (Clear 1+ pt, Fairly clear 0.4-1, Close under 0.4); close calls name the runner-up and tag cards within the margin; the chip also flags missing players or blank stats. Per-player reasons, result image (Web Share) and text summary, squad history with delete/undo and JSON export/import.
- Explains the call: "Why X and not Y" names both players and the two stats that separate them, in points ("Darren vs Kai: 11 vs 6 deaths -0.7 pts for Darren"); a Holds up / Could flip check swings the called player's deaths by 3 and gold, hero damage, damage taken and turret damage by 10%, one at a time; every card has a seven-bar stat strip and a "How 4.0 adds up" breakdown with the raw numbers.
- Phone use: one-tap share (image pre-drawn after analysis, with lane-colour stripes, a THREW / CARRIED stamp and the data caveat; text-only fallback), roster memory (hero and role per name, Last squad, Forget saved players), history form bars with trend and per-match scores, leaderboard stacked into cards on small screens, and an offline service worker with manifest and icons (installable; the screenshot reader is about 7 MB after first use).
- Limits: role baselines are the app's own estimates, not official Moonton data; end-screen stats miss rotations, vision, objectives and the draft.

## Log
- 2026-11-11: built and shipped via /hone (v0 -> v1, self-judged 5.6 -> 8.4, gates 3/5 -> 5/5, e2e 13/13). Repo, Pages, landing page, portfolio card and profile entry created.
- 2026-11-11 (round 2): v2-v3 via /hone with the 3-judge council back online. Council v1 8.95 (the earlier 8.4 was self-judged); pairwise v2 beat v1 3-0 and v3 beat v2 3-0, while single-run absolute scores drifted 8.75 -> 8.60 as judges raised the bar. Added screenshot/paste import, lane colours and Threw/Carried stamps, role-aware KDA, data warnings, heroes in share outputs. Gates 5/5, e2e 26/26, node tests incl. parser. Repo 95470ba, landing 5d32e9a.
- 2026-11-11 (round 3): v4 via /hone. Close calls name the runner-up and tag near-tied cards, data warnings folded into the verdict chip, "How is this decided?" link with thresholds, share-image preview with wrapped Why line, 2/11/3 quick K/D/A entry. Council single score 9.1 (v3 8.60); pairwise v4 beat v3 3-0. Gates 5/5, e2e 31/31, node tests pass. Repo 097f0f9, landing bb1ef8e, profile 6e29acf, portfolio card bee6f11.
- 2026-11-11 (round 4): v5 via /hone. "Why X and not Y" deciders, Holds up / Could flip sensitivity check, per-card "How 4.0 adds up" maths, one-tap phone share, roster memory, history form bars, offline service worker with manifest and icons. Council single score 9.1 (v4 9.1, no absolute gain); pairwise v5 beat v4 3-0. Gates 5/5, e2e 44/44, offline 7/7. Repo 4407f26.
- 2026-11-11 (round 5): v6 via /hone. Sensitivity check also swings gold, hero damage, damage taken and turret damage by 10%; seven-bar stat strip on every card; deciders name both players; data caveat in the copied text and on the share image; share image with lane-colour stripes and a THREW / CARRIED stamp; text-only share fallback; leaderboard as cards on phones; "Read a screenshot" / "Paste copied stats" buttons above the form; Clear all undo; "Tried" stamp renamed "Best effort". Council 9.3 (v5 9.1); pairwise v6 beat v5 3-0. Gates 5/5, e2e 56/56, offline 7/7. Stopped at the 5-round limit (also two rounds under the 0.3 minimum gain). Repo 858775e, landing 165227a, profile 2fbf72b, portfolio card 2a010b1.
- 2026-11-12 (round 6-7): v7 and v8 via /hone. v7: import review flags numbers that look like a dropped or added digit; clipboard offer bar ("Fill them in" / "Not now", never prompts); the stat strip moved inside "How X adds up", open only on the called player; the sensitivity check also moves the runner-up; deciders say whose favour the points are in; "How is this calculated?" opens with a five-step worked example; share image with one stat strip per player; last Victory/Defeat remembered. Council 9.3 (v6 9.3, gain 0.0); gates 5/5, e2e 76/76, offline 7/7; repo 873667d. v8: 12 px minimum text; the what-if check also moves kills and assists by 1 to 3 (never below 0) for the called player and the runner-up; "Holds up / Could flip" is its own coloured box; an estimates note under the verdict and in "How is this calculated?"; "How is this calculated?" opens on a three-sentence summary with five closed fold-outs; the screenshot reader is warmed up early (never on metered or data-saver connections, only with a service worker); touch targets at least 44 px on touch screens; a column the whole squad left blank is left out of the score for everyone; share image style Detailed (1080x1560) or Compact (1080x1080), remembered; auto-advance declined. Council 9.0 single run (v7 9.3); pairwise v8 beat v7 3-0 in both orders, kept on the pairwise. Gates 5/5, e2e 89/89, offline 7/7, node tests pass. Stopped on plateau (gains 0.0, then -0.3). Repo ddb00ad, landing 0dcd82f, profile 72e3d3f, portfolio card fbe5ac0.
