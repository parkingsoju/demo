---
id: FEA-002
type: feature
title: Claude context packs + session import inbox
status: implemented
files:
  - repo: jarvis
    path: src/core/pack.ts
  - repo: jarvis
    path: src/core/importSession.ts
  - repo: jarvis
    path: public/inbox.html
tags:
  - jarvis
  - phase-3
created: 2026-07-07T00:00:00.000Z
commits:
  - 'jarvis:be6788d'
  - 'jarvis:f2e95c2'
  - 'jarvis:5389bfb'
  - 'jarvis:65069a2'
  - 'jarvis:3fcd97b'
  - 'jarvis:390ec96'
  - 'jarvis:68f9e8a'
  - 'jarvis:a0f82fd'
  - 'jarvis:2b7122d'
---

Jarvis slice 4 (jarvis.md Phase 3): `POST /pack` builds compact Claude context from the focused VS Code window + graph items + git log; `jarvis import` parses the trailing ```jarvis-export``` YAML block into a session node plus inbox suggestions; approve/reject in `inbox.html` promotes suggestions to real items with provenance. No LLM inside Jarvis — Claude output is not truth by default. Shipped 2026-07-06, merged f156a01. See [[DEC-002]], [[GOT-002]], [[GOT-003]], [[OQ-002]].
