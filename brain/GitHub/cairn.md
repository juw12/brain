---
title: "cairn"
type: note
date: 2026-11-05
tags:
  - github
  - project/cairn
  - status/active
  - public
repo: "https://github.com/juw12/cairn"
visibility: public
updated: 2026-11-11
source: github-sync
claim: "Built cairn: A second brain that lives inside your repo"
role: author
evidence: [https://github.com/juw12/cairn]
publish: true
---

# cairn

> A second brain that lives inside your repo: capture, brainstorm, decide and ship as plain Markdown next to your code. Ideas wall, task board, decision log, a daily voice log (works offline, on the device) with a 12-month journal, AI context pack. Zero dependencies.

- **Repo:** https://github.com/juw12/cairn (public)
- **Live:** https://juw12.github.io/cairn/
- **Language:** Python
- **Topics:** adr, cairn-brain, git, journal, kanban, local-first, markdown, mcp, model-context-protocol, notes, obsidian, pwa, second-brain, speech-recognition, voice-notes, zero-dependencies
- **Started:** 2026-11-05 · **last push:** 2026-11-09

## Changes

- 2026-11-11: Chat from anywhere: when the phone can't reach the PC, Chat goes through the private repo `juw12/cairn-relay` (phone writes `requests/`, the desktop app answers in `threads/`); `cairn relay setup` creates it and keeps the token DPAPI-sealed ([92b7020](https://github.com/juw12/cairn/commit/92b7020)). Log: 2026-11-12 0047 cairn chat from anywhere relay
- 2026-11-11: Live sessions show a progress bar, time left and a Light/Medium/Heavy effort rating with its reasons, on each Vibe card and in the overview lanes; `cairn vibe log --progress N` lets an agent report its own percent ([1d43870](https://github.com/juw12/cairn/commit/1d43870)).
- 2026-11-11: Chat page talks to the PEGAAi OpenCode models from the PC or a paired phone, with a Glow tab ([22a76c0](https://github.com/juw12/cairn/commit/22a76c0)); phones pair by QR code and both screens update live ([dd8c2d8](https://github.com/juw12/cairn/commit/dd8c2d8)).
- 2026-11-10: Sidebar cut from 17 entries to 8 with tabs inside each ([PR #30](https://github.com/juw12/cairn/pull/30)); the Vibe page has a live overview band of every status that can be clicked to filter ([PR #32](https://github.com/juw12/cairn/pull/32)); Founder Studio wears Cairn's controls and follows its theme ([PR #33](https://github.com/juw12/cairn/pull/33)); the local server still answers when a git check stalls ([PR #34](https://github.com/juw12/cairn/pull/34)). Log: 2026-11-10 2253 cairn sidebar vibe overview founder look
- 2026-11-10: Projects tab ranks every repo (cairn included) by solid and promising, with a why and a next step per card; database blocks and a / menu in notes ([PR #31](https://github.com/juw12/cairn/pull/31)). Log: 2026-11-10 1815 cairn hone
- 2026-11-09: Founder Studio page shows three live steps (idea, run, save) with a write-your-own link ([PR #27](https://github.com/juw12/cairn/pull/27)). Log: 2026-11-09 2340 founder studio steps
- 2026-11-09: Founder Studio page inside Cairn ([PR #26](https://github.com/juw12/cairn/pull/26)): the 3D buyer panel runs in the browser on `#/founder`, results show as a strip and Save to brain files a `founder-studio` note. Studio code now lives in `docs/founder/`. Log: 2026-11-09 2300 founder studio in cairn
- 2026-11-09: Log button in thumb reach on phones ([PR #24](https://github.com/juw12/cairn/pull/24), Juwen's call): it floats bottom-right, tucks away while you scroll down and comes back when you scroll up or reach the end; desktop keeps it in the top bar. Log: 2026-11-09 1900 cairn log button thumb reach
- 2026-11-09: Autopilot took over from the old Precedent Agent; worker heartbeat fix ([PR #23](https://github.com/juw12/cairn/pull/23)): one worker per machine even during 45-minute rounds. 289 tests. Log: 2026-11-09 1750 precedent agent retired, cairn autopilot live
- 2026-11-09: Vibe queue round 7 ([PR #22](https://github.com/juw12/cairn/pull/22), blind pair 3-0): tap a figure to read what it means (phones have no tooltips), empty Feedback/Skills fold to one line on phones, a "Chart" button in the pinned day header after a jump, 44px phone day headers. Log: 2026-11-09 1720 cairn vibe queue 7
- 2026-11-09: Vibe queue round 6 ([PR #21](https://github.com/juw12/cairn/pull/21), council 8.7 -> ~9.3, every step won its blind pair 3-0): detected sessions say "code changed" ("shipped" only when you end one as shipped), chart bars jump to their day, open day headers stay pinned, per-day outcome tooltips, dimmed "Logged by hand 0" chip, empty tiles all read the same. Log: 2026-11-09 1642 cairn vibe queue 6
- 2026-11-09: Precedent and Autopilot moved into Cairn ([PR #19](https://github.com/juw12/cairn/pull/19), fix [PR #20](https://github.com/juw12/cairn/pull/20)): `cairn precedent brief` drafts a Definition of Done from past requests, hidden asks and lessons; `#queue`/`#auto`/`#needs-me` tasks; one background worker runs opencode rounds until a goal is done and takes the next `#auto` item; Autopilot view, API and MCP tools. 287 tests. Log: 2026-11-09 1155 cairn autopilot
- 2026-11-09: MCP server merged ([PR #17](https://github.com/juw12/cairn/pull/17)): `cairn mcp` lets Claude, Cursor, Copilot or OpenCode search, read and update the brain (config per assistant on the Context page); file cache, non-blocking map layout and paged Notes keep a 2,000-note vault fast. Log: 2026-11-09 0920 cairn mcp and scale
- 2026-11-09: Vibe page round 5 ([PR #18](https://github.com/juw12/cairn/pull/18)): Log button moved into the top bar (no longer floats over the page), honest header counts, clock vs summed time, chart splits no git, older days fold by default at scale, start–end rows. Council flat at 8.7 (pairwise 3–0 every round). Log: 2026-11-09 1135 cairn vibe ten
- 2026-11-08: voice log round 4 merged ([PR #16](https://github.com/juw12/cairn/pull/16)): monthly review, weekly/monthly reviews offered when due, days that read alike, 30d/90d/All for On your mind, AudioWorklet capture, persistent live region, WCAG AA contrast and focus rings. Log: 2026-11-08 2330 cairn voice log 4
- 2026-11-08: Vibe queue merged ([PR #15](https://github.com/juw12/cairn/pull/15)): outcome chips filter the session list (and act as the legend), days fold, "–" figures say why they're empty, and the desktop app records OpenCode sessions itself with a single-writer claim so the app, a startup watcher and a terminal never write together. Log: 2026-11-08 2345 cairn vibe queue
- 2026-11-08: Vibe page at scale ([PR #14](https://github.com/juw12/cairn/pull/14), council 4.0 -> 8.8): time vibing is clock time (parallel agents count once), commit evidence from git for OpenCode sessions, day-grouped history with outcome dots and Show all, unclosed @media CSS bug fixed. Log: 2026-11-08 2200 cairn vibe scale hone
- 2026-11-08: voice log round 3 merged ([PR #13](https://github.com/juw12/cairn/pull/13)): offline voice on the device (Vosk models per language, Chrome on-device engine, automatic takeover), spoken recall of any day, voice search, fuzzy wake word and search, 12-month heatmap, focus trap, mood-chip layout fix. Log: 2026-11-08 2030 cairn hone
- 2026-11-10: Founder Studio page honed ([PR #28](https://github.com/juw12/cairn/pull/28) phone sheet, [PR #29](https://github.com/juw12/cairn/pull/29)): one title, saved panels on the page, a next step after each run; council 6.95 -> 7.65. Log: 2026-11-10 1050 founder studio page hone

## From the README

**Your project's thinking is scattered.** Ideas sit in Notion, tasks in GitHub Issues, decisions
in Slack threads, TODOs in code comments, and the "why" lives in someone's head. Obsidian and
Notion are great at notes, but neither knows anything about your repo.

Cairn puts one calm place **inside the project**, built around how project work actually moves:

See also: GitHub repos
