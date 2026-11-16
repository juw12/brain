---
title: "ruang"
type: note
date: 2026-11-10
tags:
  - github
  - project/ruang
  - status/active
  - public
repo: "https://github.com/juw12/ruang"
visibility: public
updated: 2026-11-10
source: github-sync
claim: "Built Ruang: room photos to a priced 3D plan in the browser - 7 render styles, drag-to-arrange, country renovation templates, local-currency estimate, architect checks with one-tap fixes"
role: author
evidence: [https://github.com/juw12/ruang]
publish: true
---

# ruang

> Ruang - photograph your room, plan it like an architect (Windows app, installable phone app, web)

- **Repo:** https://github.com/juw12/ruang (public)
- **Live:** https://juw12.github.io/ruang/ · landing: https://juw12.github.io/p/ruang/
- **Windows app:** https://github.com/juw12/ruang/releases/latest
- **Language:** JavaScript (vanilla ES modules, three.js r160, no build step)
- **Topics:** threejs, interior-design, room-planner, 3d, renovation, architecture, webgl, i18n, photogrammetry, cost-estimation
- **Started:** 2026-11-10

## What it does

- Region + language first (24 regions, 7 UI languages); currency, units, climate tips and sun clock follow the region.
- One photo per wall -> 3D room (corner taps + door/window marks, multi-photo wall fusion); sample room for a quick look.
- 7 render looks (realistic, miniature, pixel, cartoon, clay, blueprint, sketch); drag furniture, walk mode.
- Renovate from country templates, a sentence, or a reference photo (palette match); rent-safe mode.
- Low-high estimate in local currency with editable line items; budget optimiser ("best look for my money").
- Architect: walking-space heatmap + bottleneck, door swing, direct-sun hours through real openings, light; every catch has a one-tap fix and its cost. Auto-arrange, fit-through-door, culture lens (feng shui / vastu).
- Share link, GLB/PNG/CSV export; photos never leave the device.

## Notes

- Prices are planning ranges, not quotes. AI auto-detect path is unverified (model host blocked on the work network).
- Depth from a single photo is estimated: sample reads 4.55 m vs 4.2 m true depth, so the app shows a hint to check one measurement.

## Updates

- 2026-11-10: v1 built and honed (gates 54/54 + e2e, council baseline 7.4, round 1 kept 3-0), repo + Pages, profile, portfolio card, landing page · 2026-11-10 1325 ruang hone
- 2026-11-10: v1.1.0 installable app: Windows exe (Tauri 2, CI-built, smoke 11/11 in real WebView2) + offline PWA for Android/iPhone/desktop · [[Update Log/2026-11-10 1620 ruang app]]
- 2026-11-10: v1.2.0 signed Android APK (emulator smoke pass) + Windows NSIS installer (install/uninstall test pass) · [[Update Log/2026-11-10 1710 ruang android apk + installer]]
- 2026-11-10: v1.3.0 /hone r2: lens from photo EXIF + 0.5x/1x/2x picker (depth was 2x off for ultra-wide shots), 65/65 unit, council pairwise 3-0 · [[Update Log/2026-11-10 1830 ruang hone r2 lens]]
