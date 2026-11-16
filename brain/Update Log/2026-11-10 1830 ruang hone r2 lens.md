---
date: 2026-11-10
project: ruang
tags: [update-log, ruang, hone, photo-3d]
publish: true
---

# ruang v1.3.0: lens read from the photo (/hone round 2)

Asked: "continue /hone then update github".

## Shipped
- Lens from EXIF: the 35 mm-equivalent focal length (FocalLengthIn35mmFilm) sets the field of view, computed on the
  frame diagonal so 4:3, 16:9 and portrait photos all work. Photos without EXIF show "assuming 26 mm" plus a
  0.5x / 1x / 2x picker; the lens source is always shown (7 languages).
- Why: with the ceiling height known, the far-wall width does not depend on the lens, but depth does: a 0.5x photo read
  as 1x came out 2.00x too deep (unit test).
- Android emulator test now taps "Add photos" and records whether the system picker opens.
- Release v1.3.0 (Windows exe + installer, signed APK) via the gated CI.

## Verified
- Local gates ALL PASS: G1 unit 65/65 (14 new), G2 e2e all, G3 slop 0 blockers, G4 i18n 100 %, G6 390 px, 0 console errors.
- The first test run caught a wrong claim of mine (lens changes width); fixed the test to the correct quantity (depth).
- Council (3 judges): blind pairwise r2 beats r1 3-0; score 7.2 vs same-format r1 baseline 6.9 (r2 artifact had a
  screenshot, which lifted C5 visual from 5 to 7; C1 stayed 7).

## Next (judge asks)
- Depth anchor from a known reference (door height, floor tile) instead of the 0.4 m camera assumption.
- Genre-specific geometry per render style.
