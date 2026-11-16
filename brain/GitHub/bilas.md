---
title: "bilas"
type: note
date: 2026-11-08
tags:
  - github
  - project/bilas
  - status/active
  - public
repo: "https://github.com/juw12/bilas"
visibility: public
updated: 2026-11-08
source: hone
claim: "Built Bilas: a quiet first-person 3D coin laundry with synthesized ASMR and touch gestures, on web, PWA, Android and iOS"
role: author
evidence: [https://github.com/juw12/bilas, https://juw12.github.io/bilas/]
publish: true
---

# bilas

> A calm, first-person 3D coin laundromat: feed the changer, wash, tumble dry, hang by the window and fold. No score, no timer pressure; every sound is synthesized live with Web Audio. Sibling of [[GitHub/jeda|Jeda]].

- **Repo:** https://github.com/juw12/bilas (public, MIT)
- **Play:** https://juw12.github.io/bilas/
- **Android APK:** https://github.com/juw12/bilas/releases/tag/android (signed, built by GitHub Actions with Capacitor)
- **iOS app:** https://github.com/juw12/bilas/releases/tag/ios (unsigned IPA for AltStore/Sideloadly, built on a GitHub macOS runner and opened in the iOS Simulator)
- **Landing:** https://juw12.github.io/p/bilas/
- **Stack:** three.js (bundled), Web Audio, plain JS, PWA (manifest + service worker), Capacitor 8 for Android + iOS
- **Languages:** English / Bahasa Indonesia

## Log
- 2026-11-08: built and honed (council 8.1 -> 8.22, gates G1-G7 pass); judge-agreed fixes (cloth drape shader, folded thickness, felt lint, machine dials, layered skyline); made installable on desktop/iPhone (PWA) and Android (signed APK); published repo `3f11cb1`, profile Games entry `7ebd96d`, landing page, portfolio card.
- 2026-11-08 (later): gestures (drag shirts from the basket into the drum, hold the bottle over the drawer to pour); native iOS build + simulator check + IPA release; iPhone audio (plays through the silent switch, resumes after calls); phone hint no longer blocks drags; Android emulator CI now reaches the room. Commits `fa1582c`, `ecf033e`. See 2026-11-08 1300 bilas gestures ios.
- 2026-11-08 (night): hone r5-r6 shipped `90d8c2d` (live, sw bilas-v4): on-object step labels, printed-receipt ending with its own printer sound, clearcoat enamel + contact shadows, cloth fold shading/peg folds/backlight on the line, green cutting mat, quiet 'wait' mark. Council 7.92 -> 8.12, won both blind pairwise 3-0, plateau stop (under the +0.3 keep bar). See 2026-11-08 2245 bilas hone r5 r6.
- 2026-11-09: hone r8-r10 shipped (live `000aa0c`, sw bilas-v8): fold z-fight fix, fold-ribbon wrinkles, step sound; parallax window city, wind billow on line shirts, neutral-grey wrinkle relief, in-scene ghost-finger drag cue; glazed wall tiles with grout/chips/grime, one-line phone hint. Council r8 8.35, r9 8.45, r10 8.45; each beat the previous build pairwise (3-0, 3-0, 2-0-1). Plateau at 8.45. See 2026-11-09 1225 bilas hone r8 r10.

- 2026-11-09 (evening): hone r11 (council 9.0, runs 8.75/9.25, beat r10 3-0): drum cloth streaming, turnable program dial (washer 30/40/60/90 °C, dryer 40/55/70/extra, cycle 0.85-1.3x), enamel HUD plates, daytime city depth, rolled fold edges, phone station labels fit (CHANGE/GANTI). Merged parallel-session PRs #2-#5 without overwriting: one dial (r11 labelled detents) + PR #4 hand-pulled drawer and LCD program preview; PR #5 enamel/brass signage layered over r11 plates; one day haze band. Live `65f92a1`, sw bilas-v13. See 2026-11-09 2227 bilas hone r11 and merges.

See also: GitHub repos
