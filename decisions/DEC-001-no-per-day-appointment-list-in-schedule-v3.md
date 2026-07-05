---
id: DEC-001
type: decision
title: "No per-day appointment list in Schedule V3"
status: approved
feature: FEA-001
files:
  - repo: "V3-BMD-APP"
    path: "src/features/schedule/CalendarV3.tsx"
  - repo: "V3-BMD-APP"
    path: "src/api/scheduleApi.ts"
tags: ["scheduling"]
created: 2026-07-05
---

Schedule V3 renders from the by-month endpoint only; no separate per-day appointment list view. Related gotcha: [[GOT-001]]. PLACEHOLDER BODY - refine wording by editing this file.