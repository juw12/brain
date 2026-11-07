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

## Limits

- Driving routes only (no public transit).
- No live location sharing between phones; sharing is by link.
- Public OSM / OSRM services have fair-use limits.

See also: GitHub repos
