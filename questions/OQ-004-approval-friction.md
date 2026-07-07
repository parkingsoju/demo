---
id: OQ-004
type: question
title: How to cut inbox approval friction without dropping the approval gate?
status: unconfirmed
tags:
  - jarvis
  - inbox
  - design
created: 2026-07-07T00:00:00.000Z
commits:
  - 'jarvis:cb5d811'
  - 'jarvis:d61be9d'
---

Graph starves if approving is expensive; but auto-writing is Second Brain's bloat failure mode — the gate stays. Candidate cuts: better suggestion quality (slice 7 overlap matcher, biggest lever — first batch was 9/11 same-file noise), batch approve/reject in inbox.html, auto-approve rules for high-confidence classes (trailer links already bypass the inbox: explicit signal = trusted, fuzzy = queued), per-source trust levels. Raised by John 2026-07-07 after comparing jarvis vs BIZBOX.SECOND.BRAIN truth models.
