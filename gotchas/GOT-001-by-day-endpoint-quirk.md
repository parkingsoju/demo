---
id: GOT-001
type: gotcha
title: "By-day endpoint silently filters and widens scope"
status: unconfirmed
feature: FEA-001
files:
  - repo: "V1-SCHEDULING-API"
    path: "SCHEDULING-SERVICE.APPLICATION/Features/Appointments/Appointment/Queries/GetByDay"
tags: ["scheduling"]
created: 2026-07-05
---

Three things bite in `GetByDay/QueryHandler.cs`:

1. **Status filter is invisible to callers** — only `Scheduled` and `Completed` appointments return. Cancelled and no-show rows exist in the table but never appear, so "show me the doctor's day" is actually "show me the non-cancelled day". Any UI counting slots from this endpoint undercounts.
2. **Null facility code widens scope** — `Beacon3FacilityCode == null` skips the facility filter entirely and returns the doctor's appointments across ALL facilities. Omitting the param does not mean "default facility"; it means "everything".
3. **Catch-all maps server errors to 400** — the handler wraps everything in try/catch and returns `BadRequestResponse` with the exception message, so a db outage looks like a client mistake.

Also pending: `TODO(auth)` in QueryDTO.cs — `BizboxDoctorId` comes from a query param, not JWT (BE-003), so any caller can read any doctor's day. Relates to [[DEC-001]].
