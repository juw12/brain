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
updated: 2026-11-19
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

- 2026-11-21: A repo's Look tab opens with **Versions**: Windows, Mac, iPhone and Android, each with the file to download or "not published", read from the releases, the README's download links and the repo's web manifest; an app's folder in a repo of many apps shows its own four, build 93 ([PR #83](https://github.com/juw12/cairn/pull/83)). Same rules as the /hone gate. From the MacBook Pro. 2026-11-21 1040 cairn versions on the repo page and hone four versions
- 2026-11-21: Nothing left open on the conversation between computers ([PR #82](https://github.com/juw12/cairn/pull/82), Python only). The MCP bundle's smoke test takes the tools from the code and must find exactly those, so the tool count in the publish workflow no longer has to be raised by hand; the live sync looks every 5 s for ten minutes after a message left or arrived; `recall.py handoffs` fetches before it lists, so an assistant is current while Cairn is closed; the desktop app's part is one function with tests that run on any system.
- 2026-11-21: Messages between computers leave at once, a phone takes part, and the order holds when clocks do not, build 90 ([PR #79](https://github.com/juw12/cairn/pull/79)). `git config cairn.sync` in the brain's repository (`auto`, set by the desktop app while automatic sync is on, or a sync command of your own) lets `cairn handoff` and the app push a message the moment it is written and fetch before reading; while the app is open `livesync.py` asks the remote every 20 s and tells the open pages which notes arrived. A phone and the web app go by a name kept in the browser and pick up, finish and close. **Close for everyone** from any device. A message carries its time in UTC (`sent`) and the message it follows (`after`). `cairn mcp` has `handoffs`, `handoff_send`, `handoff_answer`; the memory skill looks at the start of a chat. Three workspace tests that failed on a Mac pass (Ctrl+click is the right mouse button there). Log: 2026-11-21 1000 cairn handoffs between computers
- 2026-11-21: Your computers leave messages for each other, build 87 ([PR #75](https://github.com/juw12/cairn/pull/75)). Today has a block **Between computers**: what waits for this computer, what it is waiting for, what is between the others, with Picked up, Done and an answer box. `cairn handoff` (send, show, pickup, reply, done) does the same from a terminal. Every message is its own file in `handoffs/`, written once, so two computers never write the same file. Made on the MacBook Pro.
- 2026-11-19: Version history inside the app: every build with its date and what changed, from `docs/versions.json` (15 builds back to 5 Nov), opened from the sidebar foot, Settings or the command palette; `CHANGELOG.md` is generated from it and a test fails when the build number moves without an entry ([PR #50](https://github.com/juw12/cairn/pull/50))
- 2026-11-19: Journal is one period bar (any number of days) with a day-by-day Recap, automatic mood and no reviews to write; Proof recap is one line per item ([PR #48](https://github.com/juw12/cairn/pull/48)). Session notes name their computer and Vibe has a device switch (all computers combined, or one alone); a computer's first pass imports its whole OpenCode history ([PR #49](https://github.com/juw12/cairn/pull/49)). 2026-11-19 1427 cairn journal recap and device switch
- 2026-11-19: Every remaining page is blocks that fold and arrange, each with a Dashboard and a Recap (Today, Board, Ideas, Decisions, Journal, Chat, Autopilot, Map, Canvas list, Notes, Code inbox); a big-map pan is no longer redrawn mid-slide ([PR #47](https://github.com/juw12/cairn/pull/47))
- 2026-11-18: Vibe shows a session only while it works: a finished OpenCode turn ends it at once, deleted or 4 h silent sessions are closed, no more "waiting for you" or "quiet"; live cards merged into the Live recap rows, OpenBot has its own group, every Vibe section folds; Projects, People and Proof are blocks you can fold and arrange, each with a Dashboard and a Recap; sidebar is 5 entries (Autopilot inside Chat, Journal inside Build, Notes and Code inbox under Tools) and closes on a click outside ([PR #46](https://github.com/juw12/cairn/pull/46))
- 2026-11-17: Phone map no longer lags on a big brain, a Telegram bot reports Cairn's status daily, UI tidy ([PR #43](https://github.com/juw12/cairn/pull/43)): unlinked notes hidden above 1,000 notes with a "Show all" chip, pan and pinch by CSS transform (phone emulation, 2,780 notes: open 13.2 s -> 2.2 s, pan frame 183 -> 17 ms); `cairn telegram setup <token>` + Worker `cairn-telegram` (daily report, `/status`); `cairn vibe check` runs in the folder it is called from. Open: bot token from @BotFather, so no real daily message seen yet.
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
