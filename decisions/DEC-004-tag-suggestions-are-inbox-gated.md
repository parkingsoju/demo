---
id: DEC-004
type: decision
title: Tag suggestions are inbox-gated — no auto-approve
status: approved
feature: FEA-002
created: 2026-07-11T00:00:00.000Z
tags:
  - inbox-gated
  - human-approval
  - commit-overlap
---

AI-suggested tags always go through the inbox for human approval, unlike
commit-overlap links which auto-approve above a confidence threshold. The
difference: overlap links carry a deterministic confidence score (file focus
+ hub damping), while tag quality has no comparable numeric signal — a wrong
tag silently pollutes search results. Rejecting a tag suggestion is a
permanent no-re-suggest for that item, mirroring the link-suggestion gate.
