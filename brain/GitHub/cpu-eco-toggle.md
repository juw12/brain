---
title: "cpu-eco-toggle"
type: note
date: 2026-11-12
tags:
  - github
  - project/cpu-eco-toggle
  - status/active
  - public
repo: "https://github.com/juw12/cpu-eco-toggle"
visibility: public
updated: 2026-11-16
source: hone
claim: "Built CPU Eco Toggle: a Windows tray guard (PowerShell 5.1 + WinForms, no admin rights) that keeps windowless background jobs such as AI agents, builds, local LLMs and Python at BelowNormal priority all the time, moves them onto 5 of 8 cores with one click, restores every process's original priority and cores on exit, and restarts Vector after a crash or after its window has been frozen for 3 minutes"
role: author
evidence: [https://github.com/juw12/cpu-eco-toggle, https://juw12.github.io/p/cpu-eco-toggle/, https://juw12.github.io/cpu-eco-toggle/]
publish: true
---

# cpu-eco-toggle

> CPU Eco Toggle - one click gives a pinned CPU room to breathe

- **Repo:** https://github.com/juw12/cpu-eco-toggle (public, MIT)
- **Landing page:** https://juw12.github.io/p/cpu-eco-toggle/
- **Demo page:** https://juw12.github.io/cpu-eco-toggle/ (a labelled HTML illustration of the tray menu, tooltip and notification using the app's own strings; not a running copy)
- **Local copy:** `E:\Projects\cpu-eco-toggle`

## What it is

A Windows tray icon (green = ON, grey = OFF). ON moves windowless background processes (opencode, cargo, rustc,
ollama, llama-server, python, pythonw and headless msedge; never anything Vector started, never a process with a
visible window) onto cores 3-7 (mask 0xF8, 5 of 8) at BelowNormal priority and re-applies that every 30 s so new
jobs are caught. OFF puts every changed process back to its original priority and cores, including child processes
that inherited the limit. A second launch toggles the running copy, so a pinned taskbar shortcut works as an on/off
button. Right-click: status, trim background memory, exit.

## Measured

- On this PC (8 cores): OFF -> 0 processes limited, ON -> 35 processes limited. Nothing was stopped.
- Why it was built: the PC was at 100% CPU and 97% RAM from background jobs. The limit leaves about 3/8 of the CPU
  for interactive work; total CPU stayed high (about 92% average) because Vector and the apps in use were the rest.

## Limits

- Windows only (Windows PowerShell 5.1 and WinForms).
- Only the process names listed above; affinity and priority last until a process restarts.
- The tray icon can hide behind the tray arrow; drag it onto the taskbar. Pinning the Start-menu shortcut is manual.

## Next

- [ ] Configurable process list and core mask (now fixed in the script)
- Portfolio card: https://juwenlie.pages.dev/ (catalog `e1efeca`, card art `06ed06e`, 2026-11-12)
- Landing page: https://juw12.github.io/p/cpu-eco-toggle/ (live 2026-11-12, juw12.github.io `0968e5a`; gates 1/1, DNA 1/1 incl. fonts)

## Hone 2026-11-12

- Repo published (`41452a9`, demo page `4cd66d9`, GitHub Pages from /docs), topics and homepage set.
- Profile README entry under "Tools and agent skills" (`45082ac`); profile `.github/landing.json` synced (`494588c`).
- Landing page built and published (`0968e5a`); hero CTAs relabelled to "Get it on GitHub" / "See the demo" and the generic "try it in the browser" FAQ line dropped, because the demo is an illustration.
- Portfolio card added (category Software, links to the landing page): art `06ed06e`, catalog `e1efeca`, house-style check 62/62; sync-cards workflow triggered once.

## Hone 2026-11-16

- Always-on guard (`9276d78`): background jobs stay at BelowNormal priority whether the switch is ON or OFF; new processes are picked up every 30 s. Low-memory warning in the log and tray.
- Crash restart (`bfb6f2b`): Vector is started again after a crash and a list of open tasks (`E:\Projects\cpu-eco-toggle\VectorResume.txt`) opens. Limits: 3 restarts per hour, waits for 6 GB of free virtual memory.
- Frozen restart (`d2d128b`): a Vector window that Windows reports as not responding for 3 minutes is ended and restarted (`$restartVectorWhenFrozenMinutes`, 0 = never). Tested with stand-in processes only, not with a real frozen Vector.
- Not built: pressing Retry inside a Vector chat. Vector retries a dropped connection itself and offers no setting, CLI or API for it.
- Docs `8d87e70` (README, demo page). GitHub description changed from "One-click Windows tray switch that frees CPU by moving background jobs (agents, builds, LLMs) to fewer cores at lower priority - nothing gets stopped." to "Windows tray guard: background jobs (agents, builds, LLMs) run at lower priority and, with one click, on fewer cores. Restarts Vector after a crash or freeze."
- Landing page `769e21d` (gates 1/1, DNA 1/1 incl. fonts), profile README `e51e345`, portfolio catalog `494db00` (sync run succeeded, card text live on https://juwenlie.pages.dev/).
- Open: the frozen check only sees a window Windows reports as not responding; a stuck chat inside a responsive window is not caught. A second pagefile on D: was skipped (needs admin).
