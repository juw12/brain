---
title: "buddy"
type: note
date: 2026-11-04
tags:
  - github
  - project/buddy
  - status/active
  - public
repo: "https://github.com/juw12/buddy"
visibility: public
updated: 2026-11-17
source: github-sync
claim: "Built buddy: Walks new engineers through clunky work software (PLM, SRM, ERP), click by click, or…"
role: author
evidence: [https://github.com/juw12/buddy]
publish: true
---

# buddy

> Walks new engineers through clunky work software (PLM, SRM, ERP), click by click, or clicks for them. No guides to write; can run fully on local models. Windows + Mac (Lite).

- **Repo:** https://github.com/juw12/buddy (public)
- **Live:** https://juw12.github.io/buddy/
- **Language:** Python
- **Topics:** ai-assistant, desktop-assistant, desktop-pet, macos, python, screen-reader, windows
- **Started:** 2026-11-04 · **last push:** 2026-11-05

## From the README

> **Works out of the box:** Buddy starts on a free cloud brain, so there's no account, key or model download. For unlimited, private answers, add a local brain with [Ollama](https://ollama.com). The free brain's source is in [cloud/brain](cloud/brain).
>
> **On a Mac?** [Buddy Lite for Mac](mac/README.md) points and answers (hold Control+Option+Space). One line in Terminal installs it: `curl -fsSL https://juw12.github.io/buddy/mac-install.sh | bash`. Clicking and typing for you, the Pips pet and key sounds are Windows-only for now.
>
> **Tried it?** [Tell us how it went](https://github.com/juw12/buddy/issues/new?template=feedback.yml). It takes a minute.

Buddy is the app. It owns the tray…

## Updates

- 2026-11-10: Buddy 1.2.0 voice dictation (hone vs Wispr Flow and Handy). Ctrl+Alt+D types what you say into any app, offline: Whisper base.en + Silero voice detection for English (4.9% word errors clean and noisy vs 37% / 87% for the Windows recognizer), SenseVoice for Chinese (0-1.5% character errors), no made-up text on silence, My words jargon list, filler cleanup, spoken corrections, history. [PR #10](https://github.com/juw12/buddy/pull/10), landing page [PR #11](https://github.com/juw12/buddy/pull/11), [release v1.2.0](https://github.com/juw12/buddy/releases/tag/v1.2.0). Council 4.0 -> 9.2. Log: 2026-11-10 1105 buddy hone
- 2026-11-10: Buddy voice round 2 (hone; branch `voice-r2`, draft PR https://github.com/juw12/buddy/pull/14, 14 commits, CI green; not merged, 1.3.0 not released). A 15-entry language picker with an engine per language: on the same FLEURS clips Indonesian went from 95.7% to 29.1% WER, Malay 94.2% to 28.1%, Japanese 80.7% to 22.1% CER, Korean 75.6% to 13.8%, Thai 99.8% to 19.2%, Vietnamese 99.7% to 26.2%; English, Mandarin, German, Spanish and French are unchanged. Long dictation is decoded in parts while the key is held, My words makes 0 wrong replacements in the safety check instead of 56, the model unpacks in one pass with a percentage, and the release zip is made by a tool that refuses personal data. Council score 5.0 to 8.25 (rubric v2, 3 judges). Held back by one gate: latency on a calm PC was never measured, the PC stayed 87-100% busy.

- 2026-11-11: Buddy 1.3.0 released (https://github.com/juw12/buddy/releases/tag/v1.3.0, PR #14 merged): voice input in 15 language choices, long dictation decoded while the key is held, My words leaves names alone. Busy-PC timing: 1.5 s vs 18.4 s for the 1.2.0 path. Landing page PR https://github.com/juw12/buddy/pull/15. Log: 2026-11-10 2228 buddy hone r2 voice
- 2026-11-11: Buddy 1.3.1 released (https://github.com/juw12/buddy/releases/tag/v1.3.1, PR #16): points at the right control when it answers in another language. Live free-brain test: 13 of 13 tours end on the item asked about, 9 of 13 with 1.3.0. Log: 2026-11-10 2228 buddy hone r2 voice
- 2026-11-11: Buddy 1.3.2 released (https://github.com/juw12/buddy/releases/tag/v1.3.2; PRs #17-#22). Buddy for Mac is no longer English-only: a Voice language menu (16 locales, 14 languages), answers in the language you ask in and reads them with a Mac voice for that language (NLLanguageRecognizer; the older tagger read Indonesian as Turkish in CI), and menu-bar points snap to on-screen text. Windows: the Focus tab summary uses the full width and says 1/5 stars. Release plumbing fixed: the Mac app's version now equals its release (1.3.2; at 1.2.0 it would have offered itself as an update forever) and the Mac publish job refuses a zip whose version differs from the tag; the one-line installer check runs on macos-15 (macos-14 is gone) and no longer fires on tag pushes before the Mac zip exists. Mac voice languages verified by CI self-tests on Apple Silicon and Intel, not by speaking to a real Mac.
- 2026-11-14: Talk mode, a real-time spoken conversation (hone vs Jev; branch `talk-mode`, [PR #23](https://github.com/juw12/buddy/pull/23), CI green; **not merged, not released**, version stays 1.3.2). Ctrl+Alt+T: Buddy listens without a key, decides when you are done from the words at each pause (waits 0.3 s after a full sentence, 0.7 s when unsure, 1.6 s when you trail off), starts speaking on the first sentence while the rest is still being written, and stops when you talk over it. On 48 synthetic clips it answers finished sentences 100% of the time and holds 70.8% of unfinished ones (balanced 85.4%, fixed 0.7 s pause 66.7%). Barge-in in simulation: stop requested within 0.2 s, 0 false stops in 24 min. Held back by one gate: a turn decision takes 0.87 s (p95) with Whisper on a PC at about 90% CPU, target 0.3 s. Jev was not run, its figures are the vendor's. Not tried with a real person, microphone or loudspeaker. Council 4.0 -> 7.62, 7 of 8 gates. Log: 2026-11-14 1833 buddy hone talk mode

- 2026-11-16: **Talk mode, round 2** (PR 23, commit `e536a9f`, **still not merged**). Sharper rules for when a sentence is finished, and 48 new test clips the rules had never met: right on 87.5% of them (87.8% on all 96; a fixed 0.7 s pause gets 66.7%). It is **not faster than Jev**: one decision takes 0.55 s typically and 1.34 s for the slowest 1 in 20 at 88% CPU, target 0.3 s, and when that wait is counted a well-chosen fixed pause does better (72% against 66%). Three faster speech engines were tried and dropped. The landing page has a new talk mode vs Jev table that shows the slower row too; it goes live only when the PR merges. Council 7.62 -> 6.72, 7 of 8 gates. Log: 2026-11-16 1035 buddy hone talk mode round 2

- 2026-11-16: **Talk mode, round 3** (PR 23, commit `b0e364a`, **still not merged**). The speech read now starts 0.1 s into a pause and Buddy keeps above-normal priority for the whole conversation. With recognition time counted it now beats the best fixed pause on 144 clips (82.6% against 73.6%; round 2 was 66.3% against 72.2%), but not on the newest 48 alone (73.6% against 75.7%), and it is one run. It is **still not faster than Jev**: one decision takes 0.42 s typically and 1.51 s for the slowest 1 in 20 at about 90% CPU, target 0.3 s. Voice stop measured on the real sound device (0.2 s typical, one 3.3 s stall). 6 of 72 turns were never answered because a read stalled; cause not found. Council 6.72 -> 7.67 (2 judges), 7 of 8 gates. Log: 2026-11-16 1552 buddy hone talk mode round 3

- 2026-11-16: **Talk mode, round 4** (PR 23, commits `6cdab6d` and `e19c620`, **still not merged**). A fourth kind of sentence ending ("leaning", waits 0.9 s) and a fourth clip list: 192 clips, two full runs. With recognition time counted Buddy is right on 89.8% and 89.2% against 73.3% for the best fixed pause, ahead on every list in both runs, so last round's single run is now repeated. A priority bug was fixed (it dropped back to normal when the first of two holders left). The cause of the multi-second stalls was found: the laptop's firmware slows the processor to 18 to 71% for seconds at a time; Buddy cannot fix that. It is **still not faster than Jev**: one decision takes 0.39 s typically, 1.36 s and 0.66 s for the slowest 1 in 20 in the two runs, target 0.3 s; 8 to 9 of 96 finished turns were never answered. The hotkey path is now run by three tests with fakes, not yet seen in the installed app. Council 7.15 (round 3 scored again the new way) -> 7.6, 3 judges, 7 of 8 gates; blind pair 3 to 0 for round 4. Log: 2026-11-16 1832 buddy hone talk mode round 4

- 2026-11-17: **Talk mode merged** (PR 23, squash commit `aa01a60` on main, on Juwen's word). Tests and the Pages build are green on main, and the talk mode vs Jev table is live on https://juw12.github.io/buddy/ (the live page is identical to `docs/index.html`). Gate G4 is still not met, so it is **still not faster than Jev**. No new release was made: the installed Buddy is still 1.3.2 and does not have talk mode yet.

- 2026-11-17: **Buddy 1.4.0 released** (https://github.com/juw12/buddy/releases/tag/v1.4.0, PR 24, squash commit `5262f9a`). Talk mode is now in the Windows download and goes to users through auto-update (on by default; checks every 3 hours, installs when idle, self-test and roll back). Live `latest.json` says 1.4.0 for Windows and Mac. Checked: built app self-test passed; the updater code offered 1.4.0 to 1.3.2, downloaded it, the SHA-256 matched and the download passed its self-test, all in a scratch folder. **Not checked**: a real installed 1.3.2 swapping itself, and talk mode in the installed app with a real microphone. Still not faster than Jev (G4). Log: 2026-11-17 0903 buddy 1.4.0 release

- 2026-11-17: **Thinking fast and slow, and Buddy 1.5.0 released** (https://github.com/juw12/buddy/releases/tag/v1.5.0, PR 25 squash commit `ef13ae1`, PR 26 squash commit `9dd009c`). After Kahneman: System 1 does a plain one-step command at once with no screenshot and no brain (close, minimize, maximize or switch to a named window, open an app or site); anything less plain goes to the brain. The surer it must be, the more a mistake would cost (0.80 to switch, 0.95 to close). It picks up habits from what the brain did, and "no" within 30 s counts against them. On 94 held-out requests it did 43 of 49 one-step commands fast and none wrong; one decision takes 0.011 ms, a real window action 0.014 s, against 3.35 s for the free brain just to reply. Jev was **not run here**; its fast model is much broader and its confidence is trained, and the README table says so. Buddy is narrower, but it has both minds, the handoff, the bars and the learning on the PC. Live `latest.json` says 1.5.0; the built app and the downloaded update both passed the self-test. **Not checked**: a fast command in the installed 1.5.0 (typed or by microphone), a real 1.4.0 swapping itself, requests written by other people, habit confidence in real use. Council 1.8 -> 7.8 (3 judges), 7 of 7 gates. Log: 2026-11-17 1342 buddy fast and slow

See also: GitHub repos
