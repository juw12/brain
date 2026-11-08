---
title: "gate"
type: note
date: 2026-11-06
tags:
  - github
  - project/gate
  - status/active
  - public
repo: "https://github.com/juw12/gate"
visibility: public
updated: 2026-11-08
source: github-sync
claim: "Built gate: a merge gate for AI-agent code (v0.5.0, 61 tests on Linux, macOS and Windows)"
role: author
evidence: [https://github.com/juw12/gate, https://github.com/juw12/gate/releases/tag/v0.5.0]
publish: true
---

# gate

> A merge gate for AI-agent-generated code: many parallel agent sessions go in, a small number of tested, risk-tiered, provenance-tagged commits come out.

- **Repo:** https://github.com/juw12/gate (public)
- **Live:** https://juw12.github.io/gate/
- **Landing page:** https://juw12.github.io/p/gate/
- **Release:** v0.5.0 (`gate audit` provenance report, trailer spec, SECURITY.md)
- **Language:** Python, one file, standard library only
- **Topics:** ai-agents, audit, code-review, developer-tools, git, merge-queue, monorepo, provenance, python

## What it does

Lanes (path-partitioned queues), batched merges with `git merge-tree`, targeted test suites cached by tree,
bisection on failure, post-merge `gate verify` with automatic revert, risk tiers with a named approver, secret
blocking, crash-safe compare-and-swap publishing, and `gate audit`, which rebuilds a provenance report from the
target's own history. The recorded demo: 26 agent sessions, 19 merged, 6 rejected, 1 sent back, broken code
never on main.

## Changes

- 2026-11-08: site redesigned through /design (ledger direction won the council bracket; slop_check 0/0; AA contrast; no overflow at 390/1440 px), design.md added, fonts self-hosted. PR https://github.com/juw12/gate/pull/3. Portfolio card art and profile line updated.
- 2026-11-07: v0.5.0 released (https://github.com/juw12/gate/releases/tag/v0.5.0): `gate audit`, docs/provenance.md, SECURITY.md, 61 tests, CI green on 3 OS.

See also: GitHub repos
