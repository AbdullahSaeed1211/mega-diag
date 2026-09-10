# 8. Sales & Conversion

> Qualification gateway, offer presentation, purchase decision and objection handling (price/trust/payment/not-ready).

```mermaid
flowchart TD

subgraph SALES_BLOCK["8. Sales & Conversion"]
direction TB

SALES_READY[Qualified Sales Opportunity]

SALES_READY --> QUALIFY{Qualified?}

QUALIFY -->|No| DISQUALIFY_REASON{Why?}
DISQUALIFY_REASON -->|Budget| NURTURE_BUDGET[Budget Nurture]
DISQUALIFY_REASON -->|Timing| LONG_TERM_NURTURE
DISQUALIFY_REASON -->|Bad Fit| LOST_LEAD
DISQUALIFY_REASON -->|Missing Info| HUMAN_REVIEW

QUALIFY -->|Yes| OFFER_PRESENTED[Present Offer / Checkout / Quote]

OFFER_PRESENTED --> PURCHASE_DECISION{Purchase Completed?}

PURCHASE_DECISION -->|Yes| PAYMENT_STAGE
PURCHASE_DECISION -->|No| ABANDON_REASON{Why Not?}

ABANDON_REASON -->|Price| PRICE_OBJECTION[Handle Price Objection]
ABANDON_REASON -->|Trust| TRUST_OBJECTION[Provide Proof / Reassurance]
ABANDON_REASON -->|Questions| HUMAN_REVIEW
ABANDON_REASON -->|Payment Issue| PAYMENT_SUPPORT
ABANDON_REASON -->|Not Ready| LONG_TERM_NURTURE

PRICE_OBJECTION --> PURCHASE_DECISION
TRUST_OBJECTION --> PURCHASE_DECISION
PAYMENT_SUPPORT --> PURCHASE_DECISION

end
```

## Purpose

Qualification gateway, offer presentation, purchase decision and objection handling (price/trust/payment/not-ready).

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
