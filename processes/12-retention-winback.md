# 12. Retention, Cancellation & Win-Back

> Post-purchase follow-up, satisfaction check, recovery, upsell, churn monitoring, 6 save plays and win-back campaign.

```mermaid
flowchart TD

subgraph RETENTION_BLOCK["12. Retention, Cancellation & Win-Back"]
direction TB

POST_PURCHASE[Post-Purchase Follow-Up]

POST_PURCHASE --> PP1[Confirmation / Welcome]
PP1 --> PP2[Usage / Onboarding]
PP2 --> PP3[Customer Check-In]
PP3 --> SATISFACTION_CHECK{Customer Satisfied?}

SATISFACTION_CHECK -->|Yes| HAPPY_CUSTOMER
SATISFACTION_CHECK -->|No| RECOVERY_CASE[Service Recovery]

RECOVERY_CASE --> RETENTION_AGENT
RETENTION_AGENT --> RECOVERY_RESULT{Recovered?}

RECOVERY_RESULT -->|Yes| HAPPY_CUSTOMER
RECOVERY_RESULT -->|No| RETENTION_FLOW

HAPPY_CUSTOMER[Active Customer]

HAPPY_CUSTOMER --> REVIEW_REQUEST[Request Review / Testimonial]
HAPPY_CUSTOMER --> UPSELL_CHECK{Relevant Upsell / Cross-Sell?}

UPSELL_CHECK -->|Yes| CROSS_SELL[Offer Additional Product / Service]
UPSELL_CHECK -->|No| RETENTION_MONITOR

CROSS_SELL --> PURCHASE_DECISION

RETENTION_MONITOR[Monitor Customer Engagement]

RETENTION_MONITOR --> CANCEL_SIGNAL{Cancellation / Churn Signal?}

CANCEL_SIGNAL -->|No| HAPPY_CUSTOMER
CANCEL_SIGNAL -->|Yes| RETENTION_FLOW

RETENTION_FLOW{Why Cancelling?}

RETENTION_FLOW -->|Price| SAVE_PRICE[Alternative Plan / Offer]
RETENTION_FLOW -->|Not Using| SAVE_USAGE[Education / Re-Onboarding]
RETENTION_FLOW -->|Poor Experience| SAVE_SERVICE[Service Recovery]
RETENTION_FLOW -->|Competitor| SAVE_VALUE[Reinforce Value]
RETENTION_FLOW -->|Temporary Need| PAUSE_OPTION[Pause / Defer]
RETENTION_FLOW -->|Cannot Resolve| CANCEL_PROCESS[Process Cancellation]

SAVE_PRICE --> SAVE_RESULT
SAVE_USAGE --> SAVE_RESULT
SAVE_SERVICE --> SAVE_RESULT
SAVE_VALUE --> SAVE_RESULT
PAUSE_OPTION --> SAVE_RESULT

SAVE_RESULT{Customer Saved?}

SAVE_RESULT -->|Yes| HAPPY_CUSTOMER
SAVE_RESULT -->|No| CANCEL_PROCESS

CANCEL_PROCESS --> EXIT_SURVEY[Capture Cancellation Reason]
EXIT_SURVEY --> REACTIVATION_POOL

REACTIVATION_POOL[Win-Back / Reactivation Pool]
REACTIVATION_POOL --> REACTIVATION_TRIGGER{Eligible to Contact Later?}

REACTIVATION_TRIGGER -->|Yes| WINBACK_CAMPAIGN[Win-Back Campaign]
REACTIVATION_TRIGGER -->|No| ARCHIVE_CONTACT[Archive / Suppress]

WINBACK_CAMPAIGN --> WINBACK_RESPONSE{Returns?}
WINBACK_RESPONSE -->|Yes| SALES_READY
WINBACK_RESPONSE -->|No| ARCHIVE_CONTACT

end
```

## Purpose

Post-purchase follow-up, satisfaction check, recovery, upsell, churn monitoring, 6 save plays and win-back campaign.

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
