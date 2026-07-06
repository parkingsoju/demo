---
id: OQ-003
type: question
title: Should notes-web debounce saves?
status: unconfirmed
feature: FEA-003
files:
  - repo: notes-web
    path: app.js
tags:
  - notes
  - web
created: 2026-07-07T00:00:00.000Z
commits:
  - 'notes-web:cef5402'
---

app.js issues one PUT per keystroke (input event on title and body, no debounce). Fine against localhost in-memory api; decide before the fixture grows: debounce, blur-save, or leave as a deliberate perf gotcha for jarvis demos.
