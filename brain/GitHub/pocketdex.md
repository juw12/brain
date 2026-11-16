---
title: "pocketdex"
type: note
date: 2026-11-08
tags:
  - github
  - project/pocketdex
  - status/active
  - public
repo: "https://github.com/juw12/pocketdex"
visibility: public
updated: 2026-11-08
source: github-sync
claim: "Built PocketDex: an offline pixel-sprite Pokédex PWA with daily habits, a focus timer, a Field Dex camera and a three.js meadow"
role: author
evidence: [https://github.com/juw12/pocketdex]
publish: true
---

# pocketdex

> PocketDex - a calm pixel-sprite Pokédex you use every day: habits, focus timer, Field Dex camera and a quiet 3D meadow.

- **Repo:** https://github.com/juw12/pocketdex (public, MIT code; unofficial fan project)
- **Live:** https://juw12.github.io/pocketdex/
- **Landing page:** https://juw12.github.io/p/pocketdex/
- **Language:** JavaScript (vanilla, no build), three.js r160, Python (data build + Playwright tests)
- **Topics:** pokedex, pixel-art, habit-tracker, pomodoro, threejs, pwa, offline-first, vanilla-js

## From the README

A calm, pixel-sprite Pokédex that you also use every day, with a small 3D meadow where the Pokémon you catch come to rest.
All 1025 Pokémon, sprites and fonts are bundled; no account, progress stays in the browser. Styled after [[GitHub/jeda|Jeda]]
(warm paper, soft cards, serif titles, floating pill tab bar) and the Sansa idea of "a quiet place you visit, not a game you win".

## Updates

- 2026-11-08: first public release after a Jeda/Sansa restyle and /hone run. Council 6.6 (field-guide baseline) -> 8.38 (v1, best);
  shipped v3 (blind pair tie with v1, plus objective fixes). e2e 159/159, design gates pass (no emoji, no purple).
  Portfolio card, landing page and profile entry added. - [commit](https://github.com/juw12/pocketdex/commit/e08a646) · 2026-11-08 1209 pocketdex hone
- 2026-11-08: Today gets one clear Next step strip; meadow gains clouds, butterflies, pond ripples and idle hops. e2e 159/159. - [commit](https://github.com/juw12/pocketdex/commit/229d874) · 2026-11-08 1950 pocketdex next step meadow
- 2026-11-08: Focus becomes a partner vs wild battle; floating focus widget on every page and a pop-out timer; fixed Pause (stacked listeners). - [commit](https://github.com/juw12/pocketdex/commit/a1a2523) · 2026-11-08 2046 pocketdex focus battle widget
- 2026-11-08: phone focus widget: floating mini player (Picture-in-Picture) with the live battle animation, keep-screen-on, lock-screen notice. - [commit](https://github.com/juw12/pocketdex/commit/2504bed) · 2026-11-08 2207 pocketdex phone focus widget
- 2026-11-09: /hone rounds v4-v9. Kept v7 (154aefe, docs 8451cf9): desktop tabs move into the top bar, one dark primary per screen (Focus: Pause + End early, tools as text links; Dex: Mark as caught + Focus to catch), single-accent battle bars, honest XP note, partner strip on Training, calmer encounter copy, warmer Poison/Psychic hues. Per-view council mean 7.47 -> 7.83, blind pairs 3/3. v8 and v9 rejected; stopped on plateau. Not 10/10: Habits phone (~7.2) and the signature moment (C6) remain weakest. - [commit](https://github.com/juw12/pocketdex/commit/154aefe) · 2026-11-09 1050 pocketdex hone v4-v9
- 2026-11-09: Desktop buddy for Windows (commit 4e044c0). Your partner Pokemon now lives on the taskbar with a transparent background. It walks on window tops, rides along when you move a window, falls when the window closes, and you can drag or throw it. Focus battles are synced from the web app (Trainer > Desktop buddy), with a timer bubble and caught/fled endings. See 2026-11-09 1220 pocketdex desktop buddy.
- 2026-11-09: PocketDex became an app (commit a906c4a, not pushed yet because of the proxy). PocketDex.exe for Windows uses pywebview and WebView2, works offline with its own save, opens as a single instance, and has the desktop buddy built in (--buddy). The site is now an installable PWA with icons and shortcuts. Partner feelings: moods with pixel emotes, petting and friendship hearts, catch and level-up scenes, buddy emotes. See 2026-11-09 1850 pocketdex app and feelings.
## 2026-11-09 - PocketDex 1.1.0 (Windows app, feelings)
- PocketDex.exe: own window, built-in desktop buddy, single instance, Start menu + Desktop shortcuts on first run, update banner from version.json. Download: https://juw12.github.io/pocketdex/downloads/PocketDex-Windows.zip (22 MB)
- Partner feelings: moods with pixel emotes, petting and friendship hearts, catch and level-up scenes; reduced-motion safe
- Landing page and catalog card updated (Windows download, feelings, buddy)
- Tests: e2e 159/159, feel 29/29, focus 21/21, phone 13/13, buddy 18/18, update 10/10, app exe 11/11
- Taskbar pin is manual on Windows 11 (right-click > Pin to taskbar)
- Git through the office proxy works with NTLM: `-c http.proxy=http://:@proxy8.intra:80 -c http.proxyAuthMethod=ntlm`

## 2026-11-13 - iPhone widget (with Haru and Cozy Island)
- Trainer > iPhone widget pairs a private code; PocketDex sends a small snapshot to ntfy.sh and a free Scriptable widget shows it next to Haru and Cozy Island. Setup: https://juw12.github.io/pocketdex/widget/
- PR 1 merged (`f0726772`); e2e 158/159 (old sprite failure); live relay read-back OK. Windows zip not rebuilt. Not tested on a real iPhone.
- See 2026-11-13 1038 profile-regroup hone.

See also: GitHub repos
