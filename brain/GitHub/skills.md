---
title: "skills"
type: note
date: 2026-11-04
tags:
  - github
  - project/skills
  - status/active
  - public
repo: "https://github.com/juw12/skills"
visibility: public
updated: 2026-11-20
source: github-sync
claim: "Built skills: Agent skills I wrote for Claude Code, OpenCode, Codex and SkillMouse"
role: author
evidence: [https://github.com/juw12/skills]
publish: true
---

# skills

> Agent skills I wrote for Claude Code, OpenCode, Codex and SkillMouse: agents that verify instead of claiming (refine-loop, harness, heartbeat, Push Lab QA...)

- **Repo:** https://github.com/juw12/skills (public)
- **Language:** Python
- **Topics:** agent-skills, ai-agents, claude-code, opencode, skills
- **Started:** 2026-11-04 · **last push:** 2026-11-06

## From the README

**Agent skills I wrote for Claude Code, OpenCode, Codex and SkillMouse.** Plain `SKILL.md` files that work with any model.

The common thread: agents that **verify instead of claiming**. They run the checks, report honestly and stop when they should.

## Changes

- 2026-11-20: `/hone` holds every project to four versions: a Windows and a Mac download and an Android APK in a GitHub release, and for iPhone the live web app on the home screen. `platforms.py` is the gate and the README has to name all four ([d8552f3](https://github.com/juw12/skills/commit/d8552f3)). First reading of the profile: 4 of 92 projects have all four (Glow, Haru, Mint, Vitals); Windows 20, Mac 9, iPhone 46, Android 14. It checks that a version is published, not that it runs.
- 2026-11-20: `/hone` ships a finished project to every place it shows up: GitHub, the profile, the portfolio, Obsidian and Cairn, each as a run-queue item with its own gate (`ship.md`). Before a push `push_as.py` reads which account Cairn is set to push as and never switches it; repos stay under `juw12` unless the request names another owner. `featured.py` scores the profile's projects from facts (test files, releases and downloads, a live demo that answers, commits, stars, CI, Cairn's ranking note), orders the Featured cards and names swaps and pins ([a94ff8f](https://github.com/juw12/skills/commit/a94ff8f)). Not yet used in a real `/hone` run; creating a repo and inviting the pushing account are checked against a simulated GitHub only.

See also: GitHub repos
