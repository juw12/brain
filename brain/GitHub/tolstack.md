---
title: "tolstack"
type: note
date: 2026-11-12
tags:
  - github
  - project/tolstack
  - status/active
  - public
repo: "https://github.com/juw12/tolstack"
visibility: public
updated: 2026-11-13
source: hone
claim: "Built tolstack: a 1-D tolerance stack-up tool that reads a STEP assembly and 2D PDF drawings, ranks the part chains between two faces, finds tolerances on the drawings and writes worst case, RSS, Cp/Cpk and Monte Carlo results to an Excel report with live formulas; Streamlit app plus CLI, reads real project hand-over folders (zip/7z, up to 2 GB uploads), 106 tests, Excel formulas checked against the Python results in real Excel"
role: author
evidence: [https://github.com/juw12/tolstack, https://juw12.github.io/p/tolstack/]
publish: true
---

# tolstack

> Tolerance stack-ups from 3D and 2D, straight to Excel

- **Repo:** https://github.com/juw12/tolstack (public, MIT, version 0.5.0)
- **Landing page:** https://juw12.github.io/p/tolstack/
- **Run it:** `pip install -e ".[app]"`, then `python -m tolstack demo tolstack_demo --run` or `streamlit run app.py`

## What it is

Pick a gap or step between two faces of a STEP assembly. tolstack finds the chain of parts in between (real face
outlines, ranked candidate chains, closure checked against the 3D), reads each tolerance from the matching 2D PDF
(or the general-tolerance table), and writes nominal, worst case, RSS, Cp/Cpk, ppm, yield and Monte Carlo to Excel.
Inputs are yellow cells; everything else is a formula. Sheets for 2D evidence, assumptions and sign-off.

Started from the ZIRIS Rising-button tolerance analysis (2026-11-12), generalised so others can use it.

## Limits

1-D only (no angles). GD&T callouts are read from the drawing text and listed; one enters the stack only when
you add it as a row at ± t/2, and the GD&T font mapping is untested on real drawings. The STEP unit check only warns.
Contacts are planar faces normal to the axis. 2D lookup needs a text layer or Tesseract. Results are an engineering estimate, not a replacement for measured data (FAI/CPK).
Read the real ZIRIS hand-over STEP (66.5 MB, 504 parts, 5,848 Z faces, 436 MB peak memory); a full stack-up on it is not yet checked against the manual analysis. Native Creo files are converted only on a PC with a licensed Creo of the same or newer release (installed Creo 2.0 is license-blocked and cannot open the Creo 5.0 files). AICC is capped at 1 CPU / 1 Gi (default tier): STEP files above ~110 MB must be run locally.

## Log

- 2026-11-12: /hone run, rubric tolstack-r1 frozen, council of 3 judges: v0 7.2 -> r1 8.1 -> r2 9.0 (done score 8.5
  reached after round 2). Published to GitHub, landing page added, profile entry added; portfolio card hidden
  (no live site). Python 3.10 CI fix (cadquery-ocp 7.x import). See 2026-11-12 1938 tolstack hone.
- 2026-11-13: v0.3.0 (STEP unit check, sensitivity table, GD&T callouts as rows, portable configs, Docker).
  72 tests, ruff and mypy clean, CI green after a Linux path fix. Installed locally at `E:\Projects\tolstack`,
  landing page rebuilt, deployed to the company AICC platform (internal, SSO).
  See 2026-11-13 0934 tolstack v0.3.0 AICC deploy.
- 2026-11-13: v0.4.0 (upload a folder or a zip, general tolerance read from each part's 2D drawing before the
  app table, live 3D view that highlights the picked parts and faces). 95 tests, CI green. `E:\Projects\tolstack`
  updated and restarted. AICC production runs v0.4.0; AICC staging has the commit but its pod stays Pending
  (not scheduled, already so before this deploy). Landing page still describes v0.3.0.
  See 2026-11-13 1315 tolstack v0.4.0 AICC deploy.
- 2026-11-13: v0.5.0 (upload limit 200 MB -> 2 GB, 7z support, hand-over folder scan: STEP inside zip/7z, duplicates dropped, newest full assembly first, Creo files counted and explained, sibling `17 ... 2D` drawing folder paired automatically, STEP read once per file). Surveyed the 44 `16 ... 3D` hand-over folders. 106 tests, CI green. Landing page updated to v0.5. See 2026-11-13 1430 tolstack v0.5.0 handover folders.
- 2026-11-13: v0.6.0 (Creo assemblies listed and exported to STEP with the installed Creo, license refusal and newer-release files reported plainly; memory guard and upload limit sized from the container limit; AICC redeployed at its maximum 1 CPU / 1 Gi with request = limit). Creo export blocked here by the PTC license (EXCLUDE list) and by release (Creo 2.0 vs 5.0 files). See 2026-11-13 1540 tolstack v0.6.0 Creo and AICC max.
