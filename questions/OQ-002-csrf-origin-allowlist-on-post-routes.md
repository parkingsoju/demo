---
id: OQ-002
type: question
title: Should daemon POST routes get a CSRF Origin allowlist?
status: unconfirmed
feature: FEA-002
files:
  - repo: jarvis
    path: src/daemon/server.ts
tags:
  - jarvis
  - security
created: 2026-07-07T00:00:00.000Z
commits:
  - 'jarvis:fbbd23d'
  - 'jarvis:f2e95c2'
  - 'jarvis:073467c'
  - 'jarvis:cfd3ff2'
  - 'jarvis:6c8f733'
  - 'jarvis:bf098b7'
  - 'jarvis:a721a0d'
  - 'jarvis:3f1e9fe'
  - 'jarvis:aa92e28'
  - 'jarvis:20eabc7'
  - 'jarvis:2b7122d'
---

Daemon binds 127.0.0.1 only, but a malicious web page could still POST cross-origin to `/inbox/:id/approve` or `/pack` (localhost CSRF). Slice-4 final review triaged as DEFER. Decide before exposing any state-mutating route beyond approve/reject — candidate fix: allowlist `Origin`/`Sec-Fetch-Site` on POST.
