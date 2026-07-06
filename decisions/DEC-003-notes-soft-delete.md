---
id: DEC-003
type: decision
title: "Notes are soft-deleted, never removed from the store"
status: approved
feature: FEA-003
files:
  - repo: "notes-api"
    path: "server.js"
tags: ["notes"]
created: 2026-07-07
---

DELETE /notes/:id sets `deleted: true`; rows never leave the map. GET /notes hides deleted rows unless `?include_deleted=1`. Implemented in notes-api commit e5d7708 (carries trailer `Jarvis: DEC-003` — slice-5 git integration should pick it up as the first real hard link).
