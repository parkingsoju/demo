---
id: FEA-003
type: feature
title: "Notes app"
status: implemented
tags: ["notes", "playground"]
created: 2026-07-07
---

Two-repo playground app: `notes-api` (zero-dep node http server, in-memory store, port 4900) + `notes-web` (vanilla JS client). Built as jarvis test fixture — every decision/gotcha here is true by construction. Soft-delete behavior: [[DEC-003]].
