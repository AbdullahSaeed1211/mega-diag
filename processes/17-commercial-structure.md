# 17. Commercial Structure

> Determines staffing vs. service scope, margins, project costs, revenue-share terms and client commercial approval.

```mermaid
flowchart TD

subgraph COMMERCIAL_BLOCK["17. Commercial Structure"]
direction TB

COMMERCIAL_START[Determine Scope]

COMMERCIAL_START --> STAFF_REQUIRED{Staff Required?}

STAFF_REQUIRED -->|Yes| STAFF_PRICING[Actual Staffing Cost]
STAFF_REQUIRED -->|No| SERVICE_SCOPE

STAFF_PRICING --> STAFF_MARGIN[Add Management / Staffing Margin]
STAFF_MARGIN --> STAFF_TOTAL[Client Staffing Fee]

SERVICE_SCOPE{Marketing / Development Required?}

SERVICE_SCOPE -->|Yes| PROJECT_COST[Separate Project / Monthly Service Cost]
SERVICE_SCOPE -->|No| REV_SHARE_CHECK

PROJECT_COST --> REV_SHARE_CHECK

REV_SHARE_CHECK{Performance / Revenue Share Included?}

REV_SHARE_CHECK -->|No| STANDARD_FEE[Standard Agency Fee Structure]
REV_SHARE_CHECK -->|Yes| EXPENSE_DEFINITION[Define Approved Direct Expenses]

EXPENSE_DEFINITION --> ATTRIBUTABLE_REV[Define Attributable Revenue]
ATTRIBUTABLE_REV --> REFUND_RULES[Define Refunds / Chargebacks]
REFUND_RULES --> PAYMENT_TIMING[Define Reporting + Payment Timing]
PAYMENT_TIMING --> AGENCY_SHARE[Agency Performance Fee]

STAFF_TOTAL --> CLIENT_COMMERCIAL_REVIEW
PROJECT_COST --> CLIENT_COMMERCIAL_REVIEW
STANDARD_FEE --> CLIENT_COMMERCIAL_REVIEW
AGENCY_SHARE --> CLIENT_COMMERCIAL_REVIEW

CLIENT_COMMERCIAL_REVIEW{Terms Approved?}

CLIENT_COMMERCIAL_REVIEW -->|Yes| GO_LIVE
CLIENT_COMMERCIAL_REVIEW -->|No| NEGOTIATE[Revise Scope / Margin / Fee / Share]

NEGOTIATE --> CLIENT_COMMERCIAL_REVIEW

end
```

## Purpose

Determines staffing vs. service scope, margins, project costs, revenue-share terms and client commercial approval.

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
