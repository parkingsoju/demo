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
---

Daemon binds 127.0.0.1 only, but a malicious web page could still POST cross-origin to `/inbox/:id/approve` or `/pack` (localhost CSRF). Slice-4 final review triaged as DEFER. Decide before exposing any state-mutating route beyond approve/reject — candidate fix: allowlist `Origin`/`Sec-Fetch-Site` on POST.
