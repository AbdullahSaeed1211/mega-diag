# 6. Customer Care / Sales Staffing Layer

> Human-in-the-loop routing across 5 agent types with SLA checks, missed-contact escalation and internal escalation tree.

```mermaid
flowchart TD

subgraph STAFF_BLOCK["6. Customer Care / Sales Staffing Layer"]
direction TB

HUMAN_REVIEW{Human Needed?}

HUMAN_REVIEW -->|Yes| STAFF_ASSIGN{Assign Staff Type}

STAFF_ASSIGN -->|Inbound Calls| VOICE_AGENT[Voice / Customer Care Agent]
STAFF_ASSIGN -->|Emails| EMAIL_AGENT[Email Support Agent]
STAFF_ASSIGN -->|Sales Follow-Up| SALES_AGENT[Sales / Conversion Agent]
STAFF_ASSIGN -->|Retention| RETENTION_AGENT[Retention Agent]
STAFF_ASSIGN -->|Complex Issue| SUPERVISOR[Supervisor / Client Team]

VOICE_AGENT --> SLA_CHECK
EMAIL_AGENT --> SLA_CHECK
SALES_AGENT --> SLA_CHECK
RETENTION_AGENT --> SLA_CHECK
SUPERVISOR --> SLA_CHECK

SLA_CHECK{Answered Within SLA?}

SLA_CHECK -->|Yes| CUSTOMER_HANDLED
SLA_CHECK -->|No| MISSED_CONTACT[Missed Contact Alert]

MISSED_CONTACT --> CALLBACK[Priority Callback / Response]
CALLBACK --> CUSTOMER_HANDLED

CUSTOMER_HANDLED{Issue / Need Resolved?}

CUSTOMER_HANDLED -->|Yes| NEXT_ACTION
CUSTOMER_HANDLED -->|No| ESCALATE_INTERNAL[Escalate to Higher-Level Team]

ESCALATE_INTERNAL --> INTERNAL_RESPONSE{Internal Team Responds?}

INTERNAL_RESPONSE -->|Yes| CUSTOMER_HANDLED
INTERNAL_RESPONSE -->|No| ESCALATION_ALERT[Management Escalation]
ESCALATION_ALERT --> INTERNAL_RESPONSE

end
```

## Purpose

Human-in-the-loop routing across 5 agent types with SLA checks, missed-contact escalation and internal escalation tree.

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
