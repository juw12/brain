---
title: "hoki"
type: note
date: 2026-11-07
tags:
  - github
  - project/hoki
  - status/active
  - public
repo: "https://github.com/juw12/hoki"
visibility: public
updated: 2026-11-08
source: github-sync
claim: "Built Hoki: a waving lucky cat (招财猫) for the phone home screen (PWA + Android widget) and the Windows desktop (WPF widget)"
role: author
evidence: [https://github.com/juw12/hoki]
publish: true
---

# hoki

> Hoki - a waving lucky cat (招财猫) for your home screen and desktop. Tap it for a luck boost.

- **Repo:** https://github.com/juw12/hoki (public)
- **Live:** https://juw12.github.io/hoki/
- **Landing page:** https://juw12.github.io/p/hoki/
- **Language:** JavaScript, PowerShell (WPF widget)
- **Topics:** pwa, lucky-cat, maneki-neko, desktop-widget, svg

## From the README

A waving lucky cat (招财猫) for your home screen and desktop. Tap it for a luck boost. Nothing else, on purpose.
Inspired by the "tap for merit" apps (电子木鱼) and by Sansa (산사), the same spark behind [[GitHub/jeda|Jeda]].

## Updates

- 2026-11-09: v3.1.1 /hone polish: soft contact shadow (no grey slab), curled tail visible front-on, satin ceramic, softer whiskers, toe beans; fortune first on phones. Council 8.55 -> 8.75, pairwise 3-0. - [commit](https://github.com/juw12/hoki/commit/d6ef937) · 2026-11-09 1938 hoki v3.1.1 hone polish
- 2026-11-08: v2.0.2 calm Jeda/Sansa-style redesign replaces the retro pixel art: soft flat-vector calico cat with an engraved 福 koban, moon-gate scene whose sky follows the time of day, two-column desktop layout; Windows widget draws the same cat. /hone council 5.2 -> 8.3 (best), shipped v4 (won head-to-head vs v2). New portfolio card and landing page. - [commit](https://github.com/juw12/hoki/commit/e80ea3f) · 2026-11-08 1306 hoki hone
- 2026-11-08: v2.2.1 /hone run 2: picture-book cat (parallel session's 5-step shading merged in), daily fortune slip, milestone toast under the cat (clear of the lanterns), quiet sound/buttons, warmer dark mode with a gold focus bar, simplified home-screen icon. Council: v5 8.0, v6 8.6 (best), v7 8.0 but won the pair vs v6 3-0, shipped v7 + merged cat. Gates 21/21, A1-A8. - [commit](https://github.com/juw12/hoki/commit/1967c39) · 2026-11-08 2115 hoki hone run 2 ship v2.2.1
- 2026-11-08: v2.3.0/v2.3.1: Android home-screen widget (waving cat, tap for luck) built + released by GitHub Actions ([APK](https://github.com/juw12/hoki/releases/latest/download/hoki-widget.apk)), Phone widget panel on the site; H11 polish: centred desktop composition, one-row buttons, two-tier temple, legible tap feedback. Gates 27/27, A1-A8. - [commit](https://github.com/juw12/hoki/commit/47acbb3) · 2026-11-08 2345 hoki android widget + h11 v2.3.1
- 2026-11-09: v2.4.0 council loop: tapered arm with a shoulder root, coin paw clear of the koban, softer palette + deeper scene, twilight gate in dark mode, gold silhouette focus ring, serif captions, quieter chrome, phone first screen fits 390x844; Android widget re-released (android-v2.4.0-4). Pair votes v14>v13, v15>v14, v16>v15 all 3-0; gates 27/27, A1-A8. - [commit](https://github.com/juw12/hoki/commit/e074cba) · 2026-11-09 0920 hoki council loop v2.4.0
- 2026-11-09: v2.5.0 the paw beckons front-to-back like a real maneki-neko (forearm leans in, hand folds toward you at the wrist) instead of swinging sideways; same motion on the web, desktop widget and Android (android-v2.5.0-5). Gates 27/27 + 2 new beckon checks. - [commit](https://github.com/juw12/hoki/commit/e809e4d)

See also: GitHub repos
- 2026-11-09: v3.0.0/v3.0.1 real 3D lucky cat: the flat SVG cat is replaced by a three.js model (beckoning wrist + shoulder joint, satin ceramic glaze, adaptive quality), Windows widget and Android widget play frames rendered from the same 3D model, icons rebuilt from it. Council: v19 8.3, v21 8.3 (C2 9), v21 beat v19 3-0; flat v16 still wins pairs under the old 'flat SVG' rubric, 3D kept per Juwen. Gates G1/G2/G3/G5 pass. APK release android-v3.0.1-7. Card b5a962b, landing 1e7dc92. - [v3.0.0](https://github.com/juw12/hoki/commit/6a9099e) · [v3.0.1](https://github.com/juw12/hoki/commit/fdd6995) · 2026-11-09 1139 hoki v3 real 3D cat
- 2026-11-09: v3.1.0 Juwen: 'cat face front, more real, interactive, kawaii, no pillow'. Hoki now faces you (straight-on camera), no cushion (soft contact shadow), big glossy kawaii eyes with sparkles + brown iris, whisker pads, bigger head, plush sheen; eyes/head follow the pointer, blinks, tap = hop + happy ^ ^ eyes + ear flick, stroking the head pets it, tail sways. Widget frames/icons re-rendered, desktop counter moved to a red pill. Gates v22 G1 0 failures, G2/G3/G5 pass; interaction test passed. Card 5521bfe, landing e3ceba8. - [commit](https://github.com/juw12/hoki/commit/ae86cc8) · 2026-11-09 1631 hoki v3.1.0 front-facing kawaii interactive
- 2026-11-09: v3.2.0 Juwen: 'make it an app instead of html only, widget not as responsive as the html'. New Windows app (Tauri 2, Hoki.exe ~4 MB, CI-built and attached to the latest release): full app window plus a transparent always-on-top desktop cat running the same live three.js cat (replaces the 13-frame PowerShell flipbook) - follows the desktop mouse, tap/pet/hop, drag, right-click size/sound/open/hide, shared count, single instance. Android app now bundles the web app offline (no live URL). install.ps1 installs Hoki.exe + Start menu shortcuts, falls back to the old widget. Gates v25 G1/G2/G3/G5 pass; tested locally (transparency, cursor follow, tap, menu, app window). - [commit](https://github.com/juw12/hoki/commit/8eb5b8a) · [single instance](https://github.com/juw12/hoki/commit/736ce58) · 2026-11-09 1720 hoki v3.2.0 Windows app and offline Android app
