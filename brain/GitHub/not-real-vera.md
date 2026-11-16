---
title: "not-real-vera"
type: note
date: 2026-11-14
tags:
  - github
  - project/not-real-vera
  - status/active
  - public
repo: "https://github.com/juw12/not-real-vera"
visibility: public
updated: 2026-11-16
source: hone
claim: "Built Vera Checks (repo not-real-vera): a short-video channel kit about scam and deepfake defence with one on-camera presenter - niche research, channel rules, five episodes scripted from FBI IC3 alerts, a local renderer (voice, captions, vertical video) and a Buffer scheduler for YouTube, Instagram and TikTok with a human approval step. Nothing posted yet"
role: author
evidence: [https://github.com/juw12/not-real-vera, https://juw12.github.io/not-real-vera/]
publish: true
---

# not-real-vera

> "Ten seconds. Check first." Channel name: Vera Checks (`@verachecks`, availability unchecked).

- **Repo:** https://github.com/juw12/not-real-vera (public, no licence file yet)
- **Live:** https://juw12.github.io/not-real-vera/ (channel page; `media/epNN.mp4` is empty until `autopost.py publish`)
- **Landing:** https://juw12.github.io/p/not-real-vera/ (live, `ecd3306`; screenshot still shows the old page)
- **Portfolio:** https://juwenlie.pages.dev/ (card live; status field says "released" by tool default, nothing posted)
- **Language:** Python (Pillow, ffmpeg, local Kokoro voice), one static HTML page
- **Topics:** ai-avatar, scam-awareness, short-video, buffer, python
- **Started:** 2026-11-14 - **last push:** 2026-11-16 (`1399814`, younger presenter, camera, captions, sound)
- **Working copy:** `C:\Users\juwen_lie\.vector\scratch\session_mweyunfw7jqcw0v\not-real-vera` (scratch folder, move it to keep it)

## What it is

An AI avatar channel for YouTube Shorts, Instagram Reels and TikTok, presented by Vera. Since the second
request (below) the videos no longer say she is an AI. Each 35-45 second episode shows one scam, how an AI would write it, and one
10-second check that stops it, with the source alert on screen and in the caption.

- Niche pick: scam and deepfake defence (first scored with an openly-AI host). Scored 4.60 on the matrix in
  `niche.md` against 3.50 for finance and 3.40 for tech tutorials. The scores are judgements, and the
  30-day test in `niche.md` decides if it works.
- Five launch episodes, each traced to an FBI IC3 alert saved in `docs/sources/`: toll text, cloned
  family voice, wrong-number crypto, fake deputy call, account-takeover alert.
- `pipeline/make_episode.py` renders 1080x1920 video with voice, captions and sound cues.
- `pipeline/autopost.py` schedules through Buffer: `check`, `approve`, `publish`, `post` (dry run),
  `post --live`. An episode is never posted without an approval file.
- `tools/gates.py`: ten pass/fail checks on scripts and renders.

## Status (2026-11-14)

- /hone: v0 8.35 -> v1 8.75, council-judged (3 judges), gates 9/9 re-run after the v1 re-render.
- Renders: all five episodes rendered and pass (37.3-40.8 s, audible, captions at most 3 words). Contact sheets checked; the videos have not been watched end to end.
- Nothing has been posted. No video is public. The three accounts do not exist yet.
- Vera is a still AI portrait with camera motion, no lip-sync. One voice plays every part.

## Second request (2026-11-14): realistic presenter, no AI label in the video

Ask: "as realistic as possible ... lip sync, gesture and face expression all must be real, no need to say
that it's an AI host".

- Done: renamed to Vera Checks, removed the in-video AI badge and the "I'm an AI" lines, re-rendered all
  five episodes (37.0-41.1 s, audible, captions at most 3 words), unit tests 16/16, gates 9/9.
- **Not done: lip sync, facial expression and gestures.** Vera is still a still portrait with camera
  motion. Local SadTalker on this PC (CPU only, no NVIDIA GPU, huggingface.co blocked) did not finish 4
  frames in about 5.5 minutes, so one 40 s episode would take roughly a day. No lip-synced frame exists.
- `tools/presenter_kit.py` is the hook for a real talking-head clip: `export all` writes the portrait and
  each voice track, an outside tool makes `assets/presenter/epNN.mp4`, `make_episode.py epNN` uses it.
- Ways to get real motion (Juwen decides): a paid avatar tool (HeyGen, Kling, Hedra, Synthesia; prices
  not re-checked), a free Hugging Face token on a network where HF is open, or a PC with a GPU.
- The platform AI flag (`isAiGenerated` in `pipeline/autopost.py`) stays ON: YouTube, TikTok and Meta
  require it for realistic synthetic people. Turning it off is Juwen's call.
- The public repo is still named not-real-vera and `assets/vera.source.json` says the portrait is
  AI-generated. Renaming or making it private is Juwen's call.
- Risk: an unlabelled realistic presenter on a scam-defence channel can cost trust if viewers find out.

## Third request (2026-11-16): glamour styling, one outfit per episode

Ask: "hot girl with hourglass shape body figure with diff types of erotic shirts in every episode with
cleavage too and other elements of captivating one".

- Done: one wardrobe still per episode in `assets/outfits/` (same face in all five): ep01 black sleeveless
  V-neck, ep02 red satin wrap blouse, ep03 white ribbed scoop-neck dress, ep04 emerald camisole, ep05 denim
  corset top. `tools/outfits.py` + `tools/horde.py` make them with the free AI Horde (img2img from
  `assets/outfits/base.jpg`); `pipeline/make_episode.py` picks `assets/outfits/epNN.jpg` when it exists.
- All five episodes re-rendered with their outfit (37.0-41.1 s, audio RMS 0.065-0.073, captions at most
  3 words). Unit tests 16 passed; gates 9/9 with the link check (re-run at 10:56 after the network came back).
- "Erotic" was read as glamorous and low-cut, inside what YouTube, Instagram and TikTok allow in the normal
  feed: clearly adult presenter, no lingerie, nothing see-through, nothing explicit. Horde requests keep
  `nsfw: false`.
- Not as asked: she reads about forty to forty-five, not thirty. ep03 came out as a dress, not a square-neck
  top. ep01 and ep04 have a faint line in the hair at shoulder height. Hair, arms and room differ a little
  between episodes; only the face is identical.
- **Still not done: lip sync, expression, gestures.** Same still-picture-with-camera-motion format.
- Kept: platform AI flag ON. Not swapped: the channel page, landing page and portfolio pictures.
- Risk (Juwen's call): this styling can cost trust on a scam-defence channel, and platforms can limit the
  reach of suggestive content.
- Sync state: pushed to GitHub as `9461780` on 2026-11-16 at 10:55. The outfit pictures are now public
  in the repo. Profile README, portfolio card and landing page were not changed.

## Fourth request (2026-11-16): younger presenter, camera motion, synced captions, sound

Ask: "make the girl young, not that old, like range 18 to 30, make it very beautiful so can be clickbait,
also the movement must be very fluid and the caption must be in sync, sound must also be captivating, do
camera motion without gpu, make it not ai flag if possible".

- Done: new base portrait and five new outfit stills (prompt says aged twenty-seven; she reads late
  twenties and clearly adult). `pipeline/camera.py` adds CPU-only depth parallax with a spring-smoothed
  camera plus slight breathing and head sway. `pipeline/word_timing.py` times every caption word from the
  voice track (Vosk forced alignment). `pipeline/sound.py` adds a synthesised music bed, ducking, voice
  polish, stereo, -14 LUFS.
- Numbers (all five re-rendered, h264 1080x1920 30 fps, AAC 48 kHz stereo): 36.93-41.11 s, 7.98-9.42 MB,
  every caption word timed from the voice (112, 124, 117, 116, 123 words), loudness -14.00 to -14.01 LUFS,
  true peak -1.03 to -1.31 dBTP, camera step at most 1.35-1.67 px per frame. The old even-spacing caption
  guess was off by 0.09-0.15 s on average and up to 0.50 s.
- Found and fixed: ep01 true peak was -0.72 dBTP (now -1.03). All five music beds had the same tempo and
  three shared a key (now five tempos, 92-104 bpm, and five keys). ep05 had one caption word ("3" in
  "I C 3 dot gov") that the aligner could not place, 122 of 123; digits are now matched as spoken words,
  123 of 123.
- Checks: unit tests 23 passed; gates 10/10 with the link check (one link failed once on the proxy and
  passed on re-run). One contact sheet per episode viewed.
- Not as asked: the ducking effect is small (music rises only 1.4-3.5 dB between spoken lines). ep02 is
  velvet, not satin. ep03 is a one-piece cream scoop-neck dress and ep04 a full-length emerald wrap blouse,
  because the Horde safety filter blanked both as crop tops and fabric was added instead of rerolling.
  Seed 58 was blanked too; seed 611 was kept (204 had merged fingers, 27 a smaller face).
- **Still not done: lip sync, expression, gestures.** The motion is camera, parallax, breathing and sway
  on a still picture. Real lip sync needs a GPU or a paid avatar tool.
- Not verified: no video was watched end to end and no audio was listened to; only still frames and
  measurements.
- Kept: platform AI flag ON (`isAiGenerated` in `pipeline/autopost.py`). YouTube, TikTok and Meta require
  the label for realistic synthetic people; leaving it off risks removal or a strike, and no trick to dodge
  AI detection was added. It is Juwen's setting to change.
- Risk (Juwen's call): suggestive styling on a scam-defence channel can cost trust and limit reach.
- Render cost: about 8-16 minutes per episode on this PC. Three at once crashed on memory, so at most two.
- Sync state: pushed to GitHub as `1399814` on 2026-11-16 at 15:20. The new pictures are public in the
  repo. Profile README, portfolio card and landing page were not changed. Nothing posted.

## Needs Juwen

- Watch and approve each episode.
- Check the handle `@verachecks`, create the three accounts, connect them in Buffer (3 free slots).
- Put the Buffer API key in `~\.notrealvera\buffer_key.txt`, then run `check`, `approve`, `publish`, `post`.
- Decide if the glamour styling fits a trust channel (the pictures are public in the repo now).
- Watch one episode with sound on: nobody has heard the new music bed or seen the motion play.
- Decide the AI flag yourself (it is ON), and whether to pay for an avatar tool or use a GPU for real lip sync.
