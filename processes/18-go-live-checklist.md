# 18. Go-Live Checklist

> Pre-launch 7-gate checklist (website, LPs, tracking, CRM, comms, staff, reporting) leading to Launch Ecosystem.

```mermaid
flowchart TD

subgraph LAUNCH_BLOCK["18. Go-Live Checklist"]
direction TB

GO_LIVE[Pre-Launch Review]

GO_LIVE --> GL1{Website Ready?}
GL1 -->|No| WEBSITE_STAGE
GL1 -->|Yes| GL2

GL2{Landing Pages Ready?}
GL2 -->|No| CREATE_LPS
GL2 -->|Yes| GL3

GL3{Tracking Verified?}
GL3 -->|No| TRACK_VERIFY
GL3 -->|Yes| GL4

GL4{CRM + Automations Tested?}
GL4 -->|No| CRM_REVIEW
GL4 -->|Yes| GL5

GL5{Phone / Email / Forms Tested?}
GL5 -->|No| QA_COMMS[Fix Communications Routing]
GL5 -->|Yes| GL6

QA_COMMS --> GL5

GL6{Staff Trained + Available?}
GL6 -->|No| RECRUIT
GL6 -->|Yes| GL7

GL7{Reporting Ready?}
GL7 -->|No| REPORT_DASHBOARD
GL7 -->|Yes| LAUNCH

LAUNCH([Launch Ecosystem])

end
```

## Purpose

Pre-launch 7-gate checklist (website, LPs, tracking, CRM, comms, staff, reporting) leading to Launch Ecosystem.

## Where it sits in the ecosystem

- **Upstream:** See [Full Ecosystem](../full-ecosystem.md) and [Index](../README.md)
- **Downstream:** Edges defined in the master diagram — this stage's exit points link to the next stage (e.g., Tracking → CRM → Intent).

## Key Gates / Decisions

_Decision diamonds ({ }) are gates that branch the flow. Rectangles are actions / states._

## Related

- [⬅ Index](../README.md)
- [Full Ecosystem Diagram](../full-ecosystem.md)

---
*Extracted from [`full-ecosystem.md`](../full-ecosystem.md) — source of truth. Edit the source and regenerate to update.*
