# 14. Complaint & Escalation Management

> Severity triage (low/medium/high-legal) through email agent, supervisor, or client executive with documented resolution.

```mermaid
flowchart TD

subgraph ESCALATION_BLOCK["14. Complaint & Escalation Management"]
direction TB

ESCALATION_FLOW{Severity}

ESCALATION_FLOW -->|Low| EMAIL_AGENT
ESCALATION_FLOW -->|Medium| SUPERVISOR
ESCALATION_FLOW -->|High / Legal / Compliance / Medical| CLIENT_EXECUTIVE[Client Executive / Authorized Team]

CLIENT_EXECUTIVE --> RESOLUTION_DOCUMENTED[Document Resolution]
SUPERVISOR --> RESOLUTION_DOCUMENTED

RESOLUTION_DOCUMENTED --> CUSTOMER_NOTIFICATION[Notify Customer]
CUSTOMER_NOTIFICATION --> SATISFACTION_CHECK

end
```

## Purpose

Severity triage (low/medium/high-legal) through email agent, supervisor, or client executive with documented resolution.

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
