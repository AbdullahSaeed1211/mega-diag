# 2. Website & Digital Foundation

> Ensures a live, mobile-optimized, fast, trustworthy website with clear offer pages, CTAs, dedicated LPs and A/B variants.

```mermaid
flowchart TD

subgraph WEBSITE_BLOCK["2. Website & Digital Foundation"]
direction TB

WEBSITE_STAGE{Website Live?}

WEBSITE_STAGE -->|No| WEBSITE_REASON{Why Not?}

WEBSITE_REASON -->|New Version Coming| TEMP_PAGE[Launch Temporary Holding / Lead Capture Page]
WEBSITE_REASON -->|Broken| REPAIR_SITE[Repair Existing Website]
WEBSITE_REASON -->|No Website| BUILD_SITE[Build Website]
WEBSITE_REASON -->|Migration| MIGRATE_SITE[Migrate / Restore Website]

TEMP_PAGE --> WEBSITE_READY
REPAIR_SITE --> WEBSITE_READY
BUILD_SITE --> WEBSITE_READY
MIGRATE_SITE --> WEBSITE_READY

WEBSITE_STAGE -->|Yes| WEBSITE_READY[Website Available]

WEBSITE_READY --> MOBILE_CHECK{Mobile Optimized?}
MOBILE_CHECK -->|No| FIX_MOBILE[Fix Responsive UX]
MOBILE_CHECK -->|Yes| SPEED_CHECK
FIX_MOBILE --> SPEED_CHECK

SPEED_CHECK{Fast Enough?}
SPEED_CHECK -->|No| SPEED_FIX[Performance Optimization]
SPEED_CHECK -->|Yes| TRUST_CHECK
SPEED_FIX --> TRUST_CHECK

TRUST_CHECK{Trust Elements Present?}
TRUST_CHECK -->|No| ADD_TRUST[Add Reviews / Credentials / FAQs / Policies / Proof]
TRUST_CHECK -->|Yes| OFFER_CHECK
ADD_TRUST --> OFFER_CHECK

OFFER_CHECK{Clear Product / Service Pages?}
OFFER_CHECK -->|No| CREATE_OFFER_PAGES[Create Dedicated Offer Pages]
OFFER_CHECK -->|Yes| CTA_CHECK
CREATE_OFFER_PAGES --> CTA_CHECK

CTA_CHECK{Clear CTA on Every Revenue Page?}
CTA_CHECK -->|No| ADD_CTA[Add Call / Form / Calendar / Message CTA]
CTA_CHECK -->|Yes| LANDING_CHECK
ADD_CTA --> LANDING_CHECK

LANDING_CHECK{Dedicated Landing Page<br/>for Each Paid Offer?}

LANDING_CHECK -->|No| CREATE_LPS[Create Product-Specific Landing Pages]
LANDING_CHECK -->|Yes| LP_READY[Landing Pages Ready]
CREATE_LPS --> LP_READY

LP_READY --> AB_SETUP{A/B Testing Needed?}
AB_SETUP -->|Yes| AB_VARIANTS[Create Landing Page Variants]
AB_SETUP -->|No| TRACKING_STAGE
AB_VARIANTS --> TRACKING_STAGE

end
```

## Purpose

Ensures a live, mobile-optimized, fast, trustworthy website with clear offer pages, CTAs, dedicated LPs and A/B variants.

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
