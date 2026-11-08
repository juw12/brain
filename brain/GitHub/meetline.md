---
title: "meetline"
type: note
date: 2026-11-08
tags:
  - github
  - project/meetline
  - status/active
  - public
repo: "https://github.com/juw12/meetline"
visibility: public
updated: 2026-11-08
source: github-sync
claim: "Built Meetline: finds the fairest place for 2 to 8 people to meet, with a road route for each person"
role: author
evidence: [https://github.com/juw12/meetline]
publish: true
---

# meetline

> Meetline: find the fairest place for 2 to 8 people to meet. Venues are ranked by the longest road trip anyone makes, and each person gets a coloured route. OpenStreetMap + OSRM, no server.

- **Repo:** https://github.com/juw12/meetline (public)
- **Live:** https://juw12.github.io/meetline/
- **Landing page:** https://juw12.github.io/p/meetline/
- **Language:** JavaScript (Leaflet, plain HTML/CSS, no build step)
- **Topics:** geolocation, javascript, leaflet, meeting-point, openstreetmap
- **Started:** 2026-11-07 · **last push:** 2026-11-08

## How it works

- Add people by address search (Nominatim), current location, or a tap on the map.
- Finds the geographic centre, searches nearby cafes, restaurants, malls or parks (Overpass), then asks OSRM for real road times from everyone to each venue.
- Ranks venues by the longest trip (fairness first), then total time; draws a route per person.
- Plans are shared by link (state in the URL). No accounts, no server.

## Design

- Direction D "dispatch console": dark #0E1114 / #161A1F, amber accent #F2B233, Manrope + JetBrains Mono. No emoji, no purple.
- Won a 3-judge council bracket over three other directions; council-judged score 8.1.
- Hone 2 (2026-11-08): group-first phone layout, labeled travel modes (Car / moto, Bike, Walk), same-block venue merge, plain stats ("Everyone arrives within X", "X combined") with a 0-30 min axis, one primary button per state, grayscale basemap, How it works + privacy note. Kept round 1: 6/6 simulated users would use it (mean 6.33 vs 5.83), council pair 2-0-1 over baseline. Rounds 2-3 not kept (failed the pairwise and bots keep rule).

## Limits

- Car / moto, bike and walk routes only (no public transit); road times without live traffic.
- No live location sharing between phones; sharing is by link.
- Public OSM / OSRM services have fair-use limits.

See also: GitHub repos
