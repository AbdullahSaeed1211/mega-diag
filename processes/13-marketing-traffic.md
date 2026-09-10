# 13. Marketing & Traffic Acquisition

> Traffic strategy across 7 channels, LP intent-match gate, source tracking and 6-way CTA entry into CRM.

```mermaid
flowchart TD

subgraph MARKETING_BLOCK["13. Marketing & Traffic Acquisition"]
direction TB

MARKETING_START[Traffic Strategy]

MARKETING_START --> CHANNEL_DECISION

CHANNEL_DECISION{Channel}

CHANNEL_DECISION -->|Google Search| GOOGLE_ADS[Google Ads]
CHANNEL_DECISION -->|Meta| META_ADS[Facebook / Instagram Ads]
CHANNEL_DECISION -->|SEO| SEO[Organic Search]
CHANNEL_DECISION -->|Social| SOCIAL[Organic Social]
CHANNEL_DECISION -->|Email| EMAIL_MARKETING[Email Marketing]
CHANNEL_DECISION -->|Partners| PARTNER_TRAFFIC[Referral / Affiliate]
CHANNEL_DECISION -->|Retargeting| RETARGETING[Retargeting Campaign]

GOOGLE_ADS --> AD_LP_MATCH
META_ADS --> AD_LP_MATCH
RETARGETING --> AD_LP_MATCH

SEO --> CONTENT_PAGE[SEO Content / Service Page]
SOCIAL --> CONTENT_PAGE
EMAIL_MARKETING --> AD_LP_MATCH
PARTNER_TRAFFIC --> AD_LP_MATCH

AD_LP_MATCH{Dedicated Landing Page<br/>Matches Campaign Intent?}

AD_LP_MATCH -->|No| CREATE_LPS
AD_LP_MATCH -->|Yes| LP_VISITOR[Landing Page Visitor]

CONTENT_PAGE --> CTA_CHECK

LP_VISITOR --> TRACKING_CHECK2{Source / Campaign Tracked?}

TRACKING_CHECK2 -->|No| FIX_TRACKING
TRACKING_CHECK2 -->|Yes| CTA_EVENT

CTA_EVENT{Visitor Takes Action?}

CTA_EVENT -->|Call| PHONE_ENTRY[Inbound Call]
CTA_EVENT -->|Form| FORM_ENTRY[Form Submission]
CTA_EVENT -->|Calendar| BOOKING_FLOW
CTA_EVENT -->|Email| EMAIL_ENTRY[Email Inquiry]
CTA_EVENT -->|WhatsApp| MESSAGE_ENTRY[Message Inquiry]
CTA_EVENT -->|Purchase| PURCHASE_DECISION
CTA_EVENT -->|No Action| RETARGET_ELIGIBLE

PHONE_ENTRY --> DUPLICATE_CHECK
FORM_ENTRY --> DUPLICATE_CHECK
EMAIL_ENTRY --> DUPLICATE_CHECK
MESSAGE_ENTRY --> DUPLICATE_CHECK

RETARGET_ELIGIBLE{Consent / Platform Eligible?}
RETARGET_ELIGIBLE -->|Yes| RETARGETING
RETARGET_ELIGIBLE -->|No| EXIT_VISITOR[Visitor Leaves]

end
```

## Purpose

Traffic strategy across 7 channels, LP intent-match gate, source tracking and 6-way CTA entry into CRM.

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
