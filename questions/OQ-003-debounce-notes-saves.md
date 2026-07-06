---
id: OQ-003
type: question
title: "Should notes-web debounce saves?"
status: unconfirmed
feature: FEA-003
files:
  - repo: "notes-web"
    path: "app.js"
tags: ["notes", "web"]
created: 2026-07-07
---

app.js issues one PUT per keystroke (input event on title and body, no debounce). Fine against localhost in-memory api; decide before the fixture grows: debounce, blur-save, or leave as a deliberate perf gotcha for jarvis demos.
