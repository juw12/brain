---
title: "titip"
type: note
date: 2026-11-17
tags:
  - github
  - project/titip
  - status/active
  - public
repo: "https://github.com/juw12/titip"
visibility: public
updated: 2026-11-20
source: github-sync
claim: "Built titip: Outlook inbox, reply and compose from a paired phone, served by your own PC, plus a Gmail autopilot with code-enforced limits"
role: author
evidence: [https://github.com/juw12/titip]
publish: true
---

# titip

> Read, answer and write your Outlook mail from your phone, served by your own PC. Autopilot answers the safe Gmail on its own and keeps the rest for you. Watch and steer it from any network through a relay that only holds ciphertext.

- **Repo:** https://github.com/juw12/titip (public)
- **Live:** https://juw12.github.io/titip/ (demo on invented mail) · landing page https://juw12.github.io/p/titip/
- **Language:** Python
- **Topics:** email, gmail, local-first, outlook, pwa, python, self-hosted, windows
- **Started:** 2026-11-17 · **last push:** 2026-11-20

## Changes

- 2026-11-20: Autopilot answered a new mail by itself, nobody pressing Send (11:35). A thank-you the mailbox sent to itself through the Gmail relay, in a script outside the app around Titip's own Autopilot and Gmail code, real model; the thread has 2 messages and is in Sent. Run 10 in the log ([PR #17](https://github.com/juw12/titip/pull/17), [#18](https://github.com/juw12/titip/pull/18), `25ebb90`), no change to the app. Still to see: the first mail from another person, answered by the running app. See 2026-11-20 1047 reachpilot connect bluesky and push account.
- 2026-11-20: Autopilot tried dry, no code change: the real rules and the real model on four invented mails, with a mailbox that sends nothing. A thank-you was answered by itself and handed to the mailbox, a question about free office use and a request to meet were kept for me, and one mail the model did not answer about was set to be read again. An answer sent on its own through Gmail is still to be seen: it needs one mail from another person. 2026-11-20 1047 reachpilot connect bluesky and push account
- 2026-11-20: The first answer left through Gmail, versions 0.8.1 to 0.8.3 ([PR #13](https://github.com/juw12/titip/pull/13), [#14](https://github.com/juw12/titip/pull/14), [#15](https://github.com/juw12/titip/pull/15), [#16](https://github.com/juw12/titip/pull/16), [342313e](https://github.com/juw12/titip/commit/342313e)): a mail that could not be judged is read again, three looks in all, before it is kept; the sender is read from the last message, and from its Show details when Gmail shows a name only; the check before Send reads the reply form's own recipient, so an answer can leave, and only to the sender. Unit tests 215 -> 229. The 20 kept mails were gone through: 1 answered, 9 left unanswered by choice, 10 cleared. Open: an answer Autopilot sends on its own has not been seen. Log: 2026-11-20 1008 titip first gmail answer
- 2026-11-18: Outlook's layout, names as you type, the phone says why, versions 0.6.0 to 0.8.0 ([PR #9](https://github.com/juw12/titip/pull/9), [#10](https://github.com/juw12/titip/pull/10), [#11](https://github.com/juw12/titip/pull/11), [#12](https://github.com/juw12/titip/pull/12), [6d46e2e](https://github.com/juw12/titip/commit/6d46e2e)). Logs: 2026-11-18 0929 titip outlook look, 2026-11-18 1020 titip chips address book, 2026-11-18 1324 titip says why and cairn look
- 2026-11-17: iPhone Home Screen icon, version 0.5.1 ([PR #8](https://github.com/juw12/titip/pull/8), [0daee1a](https://github.com/juw12/titip/commit/0daee1a)): an icon on the iPhone Home Screen has its own storage and never had the key, so it showed the demo. A new page without a manifest (`home.html`) holds the key in its address for five minutes; the icon made from it keeps that address and opens Mail and Autopilot from any network. An iPhone that scans the code lands on that page. Unit tests 173 -> 174, browser steps 81 -> 104. Open: not tried on a real iPhone. Log: 2026-11-17 2135 titip home screen
- 2026-11-17: Work mail from any network and self-update, versions 0.3.0 to 0.4.2 ([PR #2](https://github.com/juw12/titip/pull/2), [#3](https://github.com/juw12/titip/pull/3), [#5](https://github.com/juw12/titip/pull/5), [#6](https://github.com/juw12/titip/pull/6), [91a5ddc](https://github.com/juw12/titip/commit/91a5ddc)): Mail tab on the phone (Inbox, Sent, Drafts, reply, new mail) through the sealed relay, off by default; Titip moves itself to the newest `main` and goes back if the new copy does not start; folder counts kept 5 minutes after Titip was found to be the cause of Outlook "Not responding". Unit tests 99 -> 170, browser steps 73. Open: real phone on mobile data, a real send through the relay, company rules for work mail outside the network. Log: 2026-11-17 2038 titip hone
- 2026-11-17: Autopilot for Gmail and any-network view ([PR #1](https://github.com/juw12/titip/pull/1), [d1c68d0](https://github.com/juw12/titip/commit/d1c68d0)), version 0.2.0: answers short, safe mail, keeps money, contract, code and papers mail with a draft, 8 answers a day at most, phone page through an AES-256-GCM relay that holds only ciphertext. Unit tests 44 -> 99, end-to-end steps 55. Open: real phone on mobile data, one full unattended answer. Log: 2026-11-17 1742 titip hone
- 2026-11-17: First version and /hone ([15ad79e](https://github.com/juw12/titip/commit/15ad79e), [cb86588](https://github.com/juw12/titip/commit/cb86588), [bc08956](https://github.com/juw12/titip/commit/bc08956)): Inbox, Sent and Drafts from classic Outlook on a paired phone, reply, forward and new mail with a 5-second Undo, QR pairing. Score 7.75 -> 8.75 (3 judges). Reads keep trying while Outlook is busy and the app stays at normal priority ([803b678](https://github.com/juw12/titip/commit/803b678)). Open: never tried on the real phone, no real send yet, Windows Firewall may block the phone. Log: 2026-11-17 1537 titip hone
