---
id: DEC-002
type: decision
title: 'Pack targets the focused window first, not the most recent heartbeat'
status: approved
feature: FEA-002
files:
  - repo: jarvis
    path: src/daemon/server.ts
  - repo: jarvis
    path: src/core/pack.ts
tags:
  - jarvis
  - multi-window
created: 2026-07-07T00:00:00.000Z
commits:
  - 'jarvis:fbbd23d'
---

With multiple VS Code windows open, every window heartbeats every 10s, so "most recent push" is effectively random. `POST /pack` without an explicit `windowId` picks `byRecency.find(w => w.focused) ?? byRecency[0]`, and returns 409 when no window is registered. Found in slice-4 final review (fix f156a01). Extension tracks focus via `onDidChangeWindowState`.
