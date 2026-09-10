# 5. Lead Intent & Response Handling

> Manages response detection, 4-step follow-up sequence, nurture vs. close decision and 8-way intent classification.

```mermaid
flowchart TD

subgraph INTENT_BLOCK["5. Lead Intent & Response Handling"]
direction TB

RESPONSE_CHECK{Customer Responded?}

RESPONSE_CHECK -->|Yes| INTENT_CLASSIFY{Intent}
RESPONSE_CHECK -->|No| FOLLOWUP_SEQUENCE

FOLLOWUP_SEQUENCE[Automated Follow-Up Sequence]

FOLLOWUP_SEQUENCE --> FU1[Follow-Up 1]
FU1 --> FU2[Follow-Up 2]
FU2 --> FU3[Follow-Up 3]
FU3 --> FU4[Final Follow-Up]

FU1 --> RESPONSE_RECHECK{Response?}
FU2 --> RESPONSE_RECHECK
FU3 --> RESPONSE_RECHECK
FU4 --> RESPONSE_RECHECK

RESPONSE_RECHECK -->|Yes| INTENT_CLASSIFY
RESPONSE_RECHECK -->|No| NURTURE_OR_CLOSE

NURTURE_OR_CLOSE{Long-Term Value?}
NURTURE_OR_CLOSE -->|Yes| LONG_TERM_NURTURE[Move to Nurture Campaign]
NURTURE_OR_CLOSE -->|No| LOST_LEAD[Mark Lost / No Response]

LONG_TERM_NURTURE --> REACTIVATION_POOL

INTENT_CLASSIFY -->|Ready to Buy| SALES_READY
INTENT_CLASSIFY -->|Needs Information| HUMAN_REVIEW
INTENT_CLASSIFY -->|Book Appointment| BOOKING_FLOW
INTENT_CLASSIFY -->|Support Question| SUPPORT_FLOW
INTENT_CLASSIFY -->|Cancellation| RETENTION_FLOW
INTENT_CLASSIFY -->|Complaint| ESCALATION_FLOW
INTENT_CLASSIFY -->|Spam / Invalid| INVALID_LEAD
INTENT_CLASSIFY -->|Not Ready| LONG_TERM_NURTURE

INVALID_LEAD[Mark Spam / Invalid / Block if Needed]

end
```

## Purpose

Manages response detection, 4-step follow-up sequence, nurture vs. close decision and 8-way intent classification.

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
