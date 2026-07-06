---
id: DEC-001
type: decision
title: "No per-day appointment list in Schedule V3"
status: approved
feature: FEA-001
files:
  - repo: "V3-BMD-APP"
    path: "lib/features/clinic_schedule/clinic_schedule_page.dart"
  - repo: "V3-BMD-APP"
    path: "lib/features/clinic_schedule/data/clinic_schedule_api.dart"
tags: ["scheduling"]
created: 2026-07-05
---

Schedule V3 renders the calendar from the by-month endpoint only; there is no separate per-day appointment list view. Day detail stays minimal (counts/markers on the month grid) instead of a second list screen backed by `GetByDay`.

Consequence: the by-day endpoint is off the primary render path, so its quirks ([[GOT-001]] — hidden status filter, null-facility scope widening) don't hit the main calendar. Any future feature that adds a day drill-down re-enters that territory and must re-check GOT-001 first.
