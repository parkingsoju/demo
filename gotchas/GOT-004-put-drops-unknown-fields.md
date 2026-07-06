---
id: GOT-004
type: gotcha
title: 'PUT /notes/:id silently drops unknown fields'
status: verified
feature: FEA-003
files:
  - repo: notes-api
    path: server.js
tags:
  - notes
  - api
created: 2026-07-07T00:00:00.000Z
commits:
  - 'notes-api:ec3353a'
---

Update handler whitelists `title` and `body` only; any other field in the payload is ignored without error or warning — response echoes the note without it. Clients sending extra fields get 200 and think they saved. Verified by smoke test 2026-07-07.
