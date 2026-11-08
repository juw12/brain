---
title: "trunnion-topopt"
type: note
date: 2026-11-08
tags:
  - github
  - project/trunnion-topopt
  - status/active
  - public
repo: "https://github.com/juw12/trunnion-topopt"
visibility: public
updated: 2026-11-08
source: hone
claim: "Topology-optimised the A-axis trunnion upright of a 5-axis FDM printer for every tilt direction and belt pull; the v4 design cuts worst-case compliance from 6.8 to 2.0 N mm and belt-pull axle tilt from 28 to 4.6 arcmin, prints without supports, and is checked by fine-mesh FE"
role: author
evidence: [https://github.com/juw12/trunnion-topopt, https://juw12.github.io/trunnion-topopt/]
publish: true
---

# trunnion-topopt

> Topology optimisation of the A-axis trunnion upright for a 5-axis 3D printer. Instead of one vertical load, the optimiser sees the worst case over the whole tilt envelope plus the overhung belt-pull case, with a 45 degree self-supporting constraint, then every candidate is re-checked on a finer FE mesh.

- **Repo:** https://github.com/juw12/trunnion-topopt (public, MIT)
- **Results page:** https://juw12.github.io/trunnion-topopt/ (3D viewer of six designs, metrics, checks, STL/STEP downloads)
- **Landing:** https://juw12.github.io/p/trunnion-topopt/
- **Stack:** Python (NumPy/SciPy) 3D SIMP + FE, CadQuery STEP export, three.js viewer
- **Recommended part (v4 Tilt gate):** 143.5 cm3 / 179 g PA-CF; worst-case compliance 1.96 N mm; axle tilt 4.56 arcmin under 100 N belt pull (target 5); seat deflection worst 25 um; peak von Mises 2.0 MPa; 0 % unsupported overhang; one solid body.
- **Baselines:** single-load TO (v0) 6.83 N mm / 28.3 arcmin; conventional webbed part (R0) 6.28 N mm / 70.2 arcmin.
- **Limits:** linear-elastic, isotropic material model; printed anisotropy, fatigue and the real printer's belt load are not measured.

## Log
- 2026-11-08: built and honed (v0 to v4, 6 gates pass on v4, results UI by /design bracket, slop_check clean); published repo `efad34b`, Pages results site, landing page `801209a`, profile Engineering entry `750e016`, portfolio card (art `46a98e5`, catalog `3c24e3e`).

See also: GitHub repos
