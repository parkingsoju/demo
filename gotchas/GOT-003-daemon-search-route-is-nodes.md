---
id: GOT-003
type: gotcha
title: 'Daemon search route is /nodes?q=, not /search'
status: verified
feature: FEA-002
files:
  - repo: jarvis
    path: src/daemon/server.ts
tags:
  - jarvis
  - api
created: 2026-07-07T00:00:00.000Z
commits:
  - 'jarvis:fbbd23d'
  - 'jarvis:f2e95c2'
  - 'jarvis:073467c'
  - 'jarvis:cfd3ff2'
  - 'jarvis:6c8f733'
  - 'jarvis:bf098b7'
---

`GET /search` 404s — full-text search lives at `GET /nodes?q=<term>`. Tripped twice during slice-3/4 e2e. Suggestions (SUG-*) are excluded from `/nodes`, `/graph`, and `/related`; sessions are included.
