# 9. Payment & Transaction Flow

> Payment success/failure branching with retry, gateway tech support, cart recovery and fraud manual review.

```mermaid
flowchart TD

subgraph PAYMENT_BLOCK["9. Payment & Transaction Flow"]
direction TB

PAYMENT_STAGE{Payment Successful?}

PAYMENT_STAGE -->|Yes| CUSTOMER_CREATED[Customer / Order Confirmed]
PAYMENT_STAGE -->|No| PAYMENT_REASON{Failure Type}

PAYMENT_REASON -->|Card Declined| RETRY_PAYMENT[Retry / Alternate Payment Method]
PAYMENT_REASON -->|Gateway Error| TECH_PAYMENT[Technical Payment Support]
PAYMENT_REASON -->|Abandoned Checkout| CART_RECOVERY[Abandoned Checkout Recovery]
PAYMENT_REASON -->|Fraud / Risk| MANUAL_PAYMENT_REVIEW[Manual Review]

RETRY_PAYMENT --> PAYMENT_STAGE
TECH_PAYMENT --> PAYMENT_STAGE
CART_RECOVERY --> PURCHASE_DECISION
MANUAL_PAYMENT_REVIEW --> PAYMENT_STAGE

CUSTOMER_CREATED --> FULFILLMENT_STAGE

end
```

## Purpose

Payment success/failure branching with retry, gateway tech support, cart recovery and fraud manual review.

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
