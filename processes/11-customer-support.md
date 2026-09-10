# 11. Customer Support

> Tiered support routing (FAQ, account, urgent, billing, regulated, technical) with resolution check to supervisor.

```mermaid
flowchart TD

subgraph SUPPORT_BLOCK["11. Customer Support"]
direction TB

SUPPORT_FLOW{Support Type}

SUPPORT_FLOW -->|Basic FAQ| SELF_SERVICE[FAQ / Automated Answer]
SUPPORT_FLOW -->|Account / Order| EMAIL_AGENT
SUPPORT_FLOW -->|Urgent| VOICE_AGENT
SUPPORT_FLOW -->|Billing| BILLING_SUPPORT[Billing Team]
SUPPORT_FLOW -->|Medical / Regulated / Sensitive| CLIENT_SPECIALIST[Authorized Client Specialist]
SUPPORT_FLOW -->|Technical| TECH_SUPPORT[Technical Support]

SELF_SERVICE --> SUPPORT_RESOLVED
BILLING_SUPPORT --> SUPPORT_RESOLVED
CLIENT_SPECIALIST --> SUPPORT_RESOLVED
TECH_SUPPORT --> SUPPORT_RESOLVED

SUPPORT_RESOLVED{Resolved?}

SUPPORT_RESOLVED -->|Yes| POST_PURCHASE
SUPPORT_RESOLVED -->|No| SUPERVISOR

end
```

## Purpose

Tiered support routing (FAQ, account, urgent, billing, regulated, technical) with resolution check to supervisor.

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
