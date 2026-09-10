# 1. Discovery & Current-State Audit

> Collects business information across 10 dimensions and runs 9 parallel audits to map revenue offers, technical stack, and ownership.

```mermaid
flowchart TD

subgraph DISCOVERY_BLOCK["1. Discovery & Current-State Audit"]
direction TB

DISCOVERY[Collect Business Information]

DISCOVERY --> D1[Products / Services]
DISCOVERY --> D2[Target Markets]
DISCOVERY --> D3[Current Website]
DISCOVERY --> D4[Existing Marketing]
DISCOVERY --> D5[Existing CRM]
DISCOVERY --> D6[Sales Process]
DISCOVERY --> D7[Customer Support]
DISCOVERY --> D8[Retention Process]
DISCOVERY --> D9[Analytics / Tracking]
DISCOVERY --> D10[Existing Vendors / Developers]

D1 --> PRODUCT_MAP[Map Core Revenue Offers]
D2 --> PRODUCT_MAP
D3 --> TECH_AUDIT[Technical Audit]
D4 --> MARKETING_AUDIT[Marketing Audit]
D5 --> CRM_AUDIT[CRM Audit]
D6 --> SALES_AUDIT[Sales Audit]
D7 --> SUPPORT_AUDIT[Support Audit]
D8 --> RETENTION_AUDIT[Retention Audit]
D9 --> TRACKING_AUDIT[Tracking Audit]
D10 --> ACCESS_AUDIT[Access / Ownership Audit]

end
```

## Purpose

Collects business information across 10 dimensions and runs 9 parallel audits to map revenue offers, technical stack, and ownership.

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
