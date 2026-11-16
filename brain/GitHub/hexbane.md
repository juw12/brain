---
title: "hexbane"
type: note
date: 2026-11-10
tags:
  - github
  - project/hexbane
  - status/active
  - public
  - ai-security
repo: "https://github.com/juw12/hexbane"
visibility: public
updated: 2026-11-10
source: hone
claim: "Built Hexbane: scans AI agent skills, MCP servers and tool lists for prompt injection, hidden or disguised text, secret theft and risky commands before they load, then gates tool calls and chat at run time."
role: author
evidence: [https://github.com/juw12/hexbane, https://juw12.github.io/hexbane/, https://juw12.github.io/p/hexbane/, https://github.com/juw12/hexbane/releases/tag/v0.2.1]
publish: true
---

# hexbane

> Breaks the hex before your AI agent falls for it. Three gates: **load gate** (scan skills / MCP configs / tool manifests / scripts, rug-pull pinning with `hexbane lock`), **call gate** (tool-call and tool-output checks), **chat gate** (the ScopeGuard engine: keeps an assistant on its mission).

- **Repo:** https://github.com/juw12/hexbane (public, release v0.2.2).
- **Live app:** https://juw12.github.io/hexbane/ (browser scanner, same rules.json as the CLI)
- **Landing page:** https://juw12.github.io/p/hexbane/
- **Language:** Python (stdlib) + vanilla JS
- **Ships as:** web app, `hexbane` CLI (JSON / Markdown / SARIF, `hexbane fix [--write]`), GitHub Action (`juw12/hexbane@v0.2.2`)
- **Compat:** rule prefix HB (was GD), `HEXBANE_*` env (`SCOPEGUARD_*` still accepted), `.hexbaneignore`.

## Measured (docs/EVALUATION.md, v0.2.1)

- Disguised-text corpus (65 samples: base64, hex, homoglyphs, zero-width, leetspeak, spacing...): files flagged 53 -> 65/65; rules kept 72 -> 116/123 (v0.2.1 squeeze pass reads letters typed one space apart).
- Held-out set 15/16 exact (11/11 malicious flagged, 0/5 false alarms); tuning 31/31; Invariant Labs PoCs 3/3.
- anthropics/skills 268 PASS / 4 REVIEW / 1 FAIL; MCP reference servers 386 PASS / 2 REVIEW (unchanged from v0.1).
- Browser = Python on all 6 corpora (headless parity test).
- /hone council: v1 9.5 -> v2 9.25 -> **v3 9.85** (3 judges; blind pairwise prefers v3 over v1). Not 10.

## Open weaknesses (from the judges)

- No third-party malicious corpus yet; words broken across lines keep only 10/14 rules.
- Chat gate: about 1 in 5 clever off-topic requests get through (needs numbers in EVALUATION).
- Docs that quote attacks still get flagged (5/273 in anthropics/skills).
- No WCAG AA audit of small dark text; no SRI hashes on browser scripts.

## Lineage

- Built from ScopeGuard (code in juw12/steward `apps/playground`, untouched).
