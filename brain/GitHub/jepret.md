---
title: "jepret"
type: note
date: 2026-11-10
tags:
  - github
  - project/jepret
  - status/active
  - public
  - photography
repo: "https://github.com/juw12/jepret"
visibility: public
updated: 2026-11-10
source: hone
claim: "Built Jepret: a free, browser-only app that turns an SD card of photos into Adobe Stock and Shutterstock upload CSVs - culls blurry and burst-duplicate shots, groups scenes, builds titles and keywords. Photos never leave the computer."
role: author
evidence: [https://github.com/juw12/jepret, https://juw12.github.io/jepret/, https://juw12.github.io/p/jepret/, https://github.com/juw12/jepret/releases/tag/v1.1.0]
publish: true
---

# jepret

> Kamera nganggur? SD card in, stock upload files out. Free, open source (MIT), no install, no upload.

- **Repo:** https://github.com/juw12/jepret (public, MIT)
- **Live app:** https://juw12.github.io/jepret/ (demo: `?demo=1`)
- **Language:** vanilla JS, no dependencies; EN / ID, light / dark
- **What it does:** blur cull (Laplacian on sharpest tiles, batch-relative bar), burst duplicates (dHash <= 6 bits AND within 60 s), flags < 4 MP, scenes by 10-min gap, keywords from your 3-5 words + dictionary + location packs, Adobe Stock + Shutterstock CSV, copy keepers to a folder, weekly shot list.
- **Left out on purpose:** AI (CLIP) tagging - Hugging Face blocked on the corporate network, could not be verified.

## Measured

- test.html 28/28 pass (headless Edge, real-time).
- Demo batch: 3 keepers, 1 duplicate per scene, 2 blurry, 1 too-small rejected; CSVs valid.
- Pitch /hone council: v0 6.05 -> **v1 8.3** (kept) -> v2 8.2 -> v3 8.3 (plateau).

## Business verdict (/founder)

- Paid version: **Not yet** - panel 3/20 buy (15% < 25%), acceptable price Rp 14.8k-50.1k/month vs planned Rp 59k. Board: strongest as free + open source. So it shipped free.

## v1.1 - it's an app now (2026-11-10)

- **Windows:** portable `Jepret.exe` (Tauri 2 + WebView2, 3.2 MB, unsigned) built by GitHub Actions on every push and attached to release v1.1.0: https://github.com/juw12/jepret/releases/latest/download/Jepret.exe. Smoke-tested locally: window opens and renders the app.
- **Phone / any computer:** installable offline web app (PWA): `sw.js` cache-first app shell, manifest with PNG + maskable icons, "Install app" button in the top bar.
- **Landing page:** https://juw12.github.io/p/jepret/ (Gabarito, editorial / diag / brutal / center, camera + SD card emblem; gates D 1/1, G 1/1).
- **Profile README:** Building > Solid: usable today (27), plus `.github/landing.json` synced.
- Network gotcha: GitHub calls hang when the local proxy `pxw.exe` (localhost:3128, startup entry OA_PROXY) dies; restart it.

## v1.2 - no SD card needed (2026-11-10)

- a6400 -> phone over Wi-Fi (Imaging Edge Mobile / Creators' App) is now a first-class path: **Choose photos** picker (gallery multi-select), folder picker hidden on touch phones.
- **Gotcha found:** the Sony apps send **2M** copies by default (about 2 MP) - below Adobe Stock's 4 MP minimum. Set transfer size to **Original**. Jepret now shows a tip on the start screen and a warning when most of a batch looks like 2M copies.
- **Bug fixed:** scenes/bursts used the file date; phone transfers reset it, so a whole day collapsed into one scene. Now reads EXIF DateTimeOriginal (falls back to DateTime, then file date).
- Tests: 37/37 (9 new) run in V8 via mini-racer because headless Edge hung on this machine; EXIF reader also checked on a Pillow JPEG with JFIF + EXIF.
- Commit 32f97a4; landing page, gallery blurb and profile README (b304489) say "photos in" now.

## Open (app)

- Folder writes (`showDirectoryPicker`) inside WebView2 not tested yet; CSV download is the fallback.
- Phone path not tried with a real a6400 transfer yet (EXIF layout of Sony Original copies assumed standard).
- No native Android APK / Play Store; Android Chrome ignores folder picking, so phone users pick files.

## v1.3 (2026-11-10): checked on real a6400 files

- Tested with 10 real ILCE-6400 JPEGs (Wikimedia Commons, EXIF intact) plus strongly and mildly blurred copies, 30 files, in Chrome through **Choose photos**.
- Found and fixed: mildly soft copies could be kept (the blur bar came from the batch median, which drops when many shots are soft). The bar now uses the 75th percentile.
- Found and fixed: the duplicate hash came from a point-sampled 9x8 canvas, so a softer copy of the same frame could hash differently. It is now box-averaged from the 800 px analysis copy.
- Found and fixed: CSV titles ended in "in " when no location was picked.
- Scenes with no keepers collapse to one line; a plain note says blur is judged on a small copy (click to keep).
- Result: 9/9 sharp originals kept, 18/18 blurred copies rejected, 3.6 MP crop flagged, 9 scenes by EXIF date; 2M copies trigger the transfer-size warning. 42/42 unit tests.
- Commits 71ff6b3, c977e82; portfolio card text updated (projects 7df2246).

## v1.4 (2026-11-10): exe folder save + handheld bursts

- **Windows exe driven end to end** (WebView2 over CDP): 30 real files gave 9 keepers / 21 rejected / 9 scenes; **Copy keepers + CSV to a folder** wrote 9 JPGs (byte-identical to the originals) + `adobe_stock.csv` + `shutterstock.csv`. Windows asks twice: *Save changes*, then *Allow* (default button is Cancel / Don't Allow), so the app now shows that hint when saving and a clear message if saving fails.
- **Found and fixed: burst duplicates missed under handheld drift.** On real a6400 frames a 2 % shift pushed the 9x8 dHash past 6 bits in 7/10 photos, 3 % in 10/10, so near-identical burst frames were all kept. Added an aligned check: 32x24 grayscale copies, normalised correlation over shifts of about 9 % sideways / 8 % up-down, duplicate at >= 0.85 within the 60 s burst window. Simulated bursts (drift, 1-2 deg tilt, +-1/3-2/3 EV) all scored >= 0.88; different photos <= 0.37.
- Burst E2E (3 real scenes x 3 frames, same EXIF time): 3 keepers, 6 duplicates. Real set and demo unchanged (9/21/9 and 3/5/2). 49/49 unit tests.
- Plainer labels: "Subject type (Adobe Stock list)" and "Someone's face can be recognised (no model release, so these go in as editorial)" (EN + ID).
- Export now has one main action where the browser can write a folder (Copy keepers + CSV to a folder), single CSV downloads as the fallback (commit 100a0cc).
- Council: v3 scored 8.7 (3 judges), pairwise v3 beat v2 3-0. Commits 51c57f0, 100a0cc.

## 2026-11-10 evening: auto words, upload path, earn offline (commits 758dd23, 5e39ada)

- **Fill in the words for me:** on-device CLIP ViT-B/32 (8-bit, ~90 MB once, cached) via onnxruntime-web. Model + 118-word list built by GitHub Actions (`clip-model.yml`, `tools/build_clip.py`) because Hugging Face is blocked on the office network. Optional auto-run after every load. AI words are marked "AI guess, check it"; other guesses are one-tap chips.
- **Words inside the photos:** every saved/shared keeper gets XMP (dc:title/description/subject) + IPTC-IIM (UTF-8) blocks; EXIF and image data untouched. Stock sites fill title/keywords on upload.
- **Upload path:** phone = share sheet (10 per tap); PC = `tools/upload_stock.py` (Shutterstock FTPS, Adobe SFTP when enabled, `--watch`, upload log). Submit / rights stay with Juwen.
- **Client proofs:** watermarked 2000 px previews with his name.
- **Earn offline section (EN/ID):** product photos, GoFood menus, wisuda, small events, kos listings (kos rate = assumption), a6400 settings, WhatsApp message per gig.
- Checks: 65/65 unit tests; local features E2E 17/17; live Pages run on the real a6400 set: words for 8/8 scenes. First live pass 5/8 fully right (pepper plant -> "monstera", robber fly and moths -> "dragonfly"); after adding a wildlife/macro vocabulary (keyword expansion) and the runner-up rule (extra word needs >= 30 % of the top word): 8/8 main subjects right, 7/8 fully right ("gecko" extra on a lizard), 12+ keywords per scene.

- Council (rubric jepret-app-v1, 3 judges) on v4: 8.7 (C1 8, C2 9, C3 9, C4 9; judges 8.4-9.2); pairwise v4 beat v3 3-0, so v4 is kept. Open fixes: real card burst, physical phone run, real upload credentials (all need Juwen); keyword tag chips done 2026-11-11 (commit 25ffca4).

## Open

- Blur is judged on an 800 px copy: slight missed focus visible only at 100 % is not caught.
- Burst check is tested on simulated bursts from real frames, not a real burst off the card; zoom changes of ~10 % between frames are not treated as duplicates.
- Shutterstock CSV columns follow the common community format, not an official spec.
- Differentiation vs Xpiks (also free) is thin; bet = no-install browser flow + Indonesia shot list.
- AI words are a first guess (CLIP zero-shot); species-level names are not reliable.
- `tools/upload_stock.py` real uploads untested (no contributor credentials); Adobe SFTP needs Adobe to enable it.

Related: E:\StockAutopilot (Python kit, same job, offline).
