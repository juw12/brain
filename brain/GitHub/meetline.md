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
updated: 2026-11-09
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
- **Started:** 2026-11-07 · **last push:** 2026-11-09

## How it works

- Add people by address search (Nominatim), current location, or a tap on the map.
- Finds the geographic centre, searches nearby cafes, restaurants, malls or parks (Overpass), then asks OSRM for real road times from everyone to each venue.
- Ranks venues by the longest trip (fairness first), then total time; draws a route per person.
- Plans are shared by link (state in the URL). No accounts, no server.

## Design

- Direction D "dispatch console": dark #0E1114 / #161A1F, amber accent #F2B233, Manrope + JetBrains Mono. No emoji, no purple.
- Won a 3-judge council bracket over three other directions; council-judged score 8.1.
- Hone 2 (2026-11-08): group-first phone layout, labeled travel modes (Car / moto, Bike, Walk), same-block venue merge, plain stats ("Everyone arrives within X", "X combined") with a 0-30 min axis, one primary button per state, grayscale basemap, How it works + privacy note. Kept round 1: 6/6 simulated users would use it (mean 6.33 vs 5.83), council pair 2-0-1 over baseline. Rounds 2-3 not kept (failed the pairwise and bots keep rule).
- Hone 4 (2026-11-08): Barlow Semi Condensed display face, result-first phone layout, initials on arrival dots, dimmed minor pins, "Midpoint only", collapsible How it works, share-link privacy note, higher-contrast muted grey, "First to last arrival" copy. Council 7.7 -> 7.8; simulated users 6/6 would use it (6.17). Rounds with a labelled fair zone scored 8.0 with judges but lower with simulated users, so they were not shipped. See 2026-11-08 2300 meetline hone 4.
- Hone 5 (2026-11-09): meeting plan in the Meet at panel (pick a time, each person gets a leave-by clock time), arrival bars that all end at the venue, per-person Bus/train link to Google Maps transit, visible Add button, desktop "Fair zone · similar trip times" label, higher-contrast muted text. Council won pairwise 2-0-1 over Hone 4; simulated users 14/18 would use it (5.94) vs 12/18 (5.89). See 2026-11-09 1040 meetline hone 5.
- Hone 6 (2026-11-09): live group - end-to-end encrypted (AES-GCM) location sharing between phones via an invite link, relayed through ntfy.sh (key only in the URL fragment); positions update on 50 m moves or a 60 s heartbeat, venues re-rank live, stale people marked "Seen x min ago". Transit as a 4th travel mode with real timetable trips from Transitous (line + walk + route on map), road estimate fallback where no feed exists. "Open in Google Maps" now opens the place page (photos, reviews, traffic). Tests: live relay 19/19 mocked, 17/17 against real ntfy.sh. Honest scores: council tied Hone 5 in every round (7.8, visually equal); simulated users 6.00 vs 5.94 (flat). Shipped for the functional gains. See 2026-11-09 1240 meetline hone 6.

## Venue details

- Venue facts (2026-11-08): opening hours from OSM show "Open now · until 22:00" / "Closed · opens tomorrow 08:00"; Meet at panel adds cuisine, takeaway, outdoor seating, wheelchair access and website when tagged. Unparsed hours are shown raw, never guessed.

## Limits

- Live sharing relays through the public ntfy.sh service (encrypted, but rate-limited and best effort) and stops when a phone's browser tab is closed or suspended; no background tracking.
- Transit times depend on Transitous coverage (none for Batam yet, so an estimate plus a note is shown) and always depart now.
- Car / moto times have no live traffic.
- Photos and reviews are on the Google place page, not inside the app. Venue details depend on OSM tags.
- Public OSM / OSRM / Transitous services have fair-use limits.

See also: GitHub repos
