# 15. Staffing Capacity & Operations

> Workload/SLA/quality monitoring, hiring-need trigger, client approval gate, recruit/prioritize and coaching/replace loops.

```mermaid
flowchart TD

subgraph STAFFING_BLOCK["15. Staffing Capacity & Operations"]
direction TB

STAFF_MONITOR[Monitor Workload]

STAFF_MONITOR --> VOLUME_CHECK{Lead / Call Volume Within Capacity?}

VOLUME_CHECK -->|Yes| SLA_MONITOR[Monitor SLA & Quality]
VOLUME_CHECK -->|No| HIRING_NEED[Additional Staffing Needed]

HIRING_NEED --> STAFF_COST[Estimate Staff Cost]
STAFF_COST --> CLIENT_APPROVAL{Client Approves Additional Staff?}

CLIENT_APPROVAL -->|Yes| RECRUIT[Recruit / Vet / Train]
CLIENT_APPROVAL -->|No| PRIORITIZE[Prioritize Leads / Adjust Coverage]

RECRUIT --> STAFF_ASSIGN
PRIORITIZE --> STAFF_ASSIGN

SLA_MONITOR --> QUALITY_CHECK{Quality Acceptable?}

QUALITY_CHECK -->|Yes| STAFF_MONITOR
QUALITY_CHECK -->|No| COACHING[Training / QA / Coaching]

COACHING --> PERFORMANCE_CHECK{Improved?}
PERFORMANCE_CHECK -->|Yes| STAFF_MONITOR
PERFORMANCE_CHECK -->|No| REPLACE_AGENT[Replace / Reassign Staff]
REPLACE_AGENT --> RECRUIT

end
```

## Purpose

Workload/SLA/quality monitoring, hiring-need trigger, client approval gate, recruit/prioritize and coaching/replace loops.

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
