# 16. Reporting, Revenue Attribution & Optimization

> Collects funnel data, tracks 12 KPIs, unified dashboard, attribution check and leak-diagnosis with 9 fix paths.

```mermaid
flowchart TD

subgraph REPORTING_BLOCK["16. Reporting, Revenue Attribution & Optimization"]
direction TB

REPORT_EVENT[Collect Funnel Data]

REPORT_EVENT --> METRICS

METRICS[Track KPIs]

METRICS --> K1[Traffic]
METRICS --> K2[Cost per Lead]
METRICS --> K3[Lead Response Time]
METRICS --> K4[Appointment Rate]
METRICS --> K5[Show Rate]
METRICS --> K6[Close Rate]
METRICS --> K7[Revenue]
METRICS --> K8[Retention]
METRICS --> K9[Cancellation Rate]
METRICS --> K10[Recovered Revenue]
METRICS --> K11[Staff Performance]
METRICS --> K12[ROAS / CAC]

K1 --> REPORT_DASHBOARD
K2 --> REPORT_DASHBOARD
K3 --> REPORT_DASHBOARD
K4 --> REPORT_DASHBOARD
K5 --> REPORT_DASHBOARD
K6 --> REPORT_DASHBOARD
K7 --> REPORT_DASHBOARD
K8 --> REPORT_DASHBOARD
K9 --> REPORT_DASHBOARD
K10 --> REPORT_DASHBOARD
K11 --> REPORT_DASHBOARD
K12 --> REPORT_DASHBOARD

REPORT_DASHBOARD[Unified Dashboard]

REPORT_DASHBOARD --> ATTRIBUTION_CHECK{Can Revenue Be Attributed?}

ATTRIBUTION_CHECK -->|Yes| PERFORMANCE_MODEL
ATTRIBUTION_CHECK -->|No| ATTRIBUTION_FIX[Fix Tracking / CRM / Source Mapping]
ATTRIBUTION_FIX --> TRACK_VERIFY

PERFORMANCE_MODEL[Calculate Campaign + Sales Performance]

PERFORMANCE_MODEL --> OPT_DECISION{Performance Good?}

OPT_DECISION -->|Yes| SCALE[Scale Winning Channels / Offers]
OPT_DECISION -->|No| FAILURE_DIAGNOSIS

FAILURE_DIAGNOSIS{Where Is the Leak?}

FAILURE_DIAGNOSIS -->|Traffic| FIX_CHANNEL[Change Targeting / Creative / Channel]
FAILURE_DIAGNOSIS -->|Landing Page| AB_VARIANTS
FAILURE_DIAGNOSIS -->|CTA| ADD_CTA
FAILURE_DIAGNOSIS -->|CRM| CRM_REVIEW
FAILURE_DIAGNOSIS -->|Slow Response| STAFF_MONITOR
FAILURE_DIAGNOSIS -->|Poor Close Rate| SALES_TRAINING[Sales Training / Script Review]
FAILURE_DIAGNOSIS -->|High Churn| RETENTION_FLOW
FAILURE_DIAGNOSIS -->|Tracking| FIX_TRACKING
FAILURE_DIAGNOSIS -->|Offer| OFFER_REVIEW[Review Pricing / Positioning / Offer]

FIX_CHANNEL --> MARKETING_START
SALES_TRAINING --> SALES_READY
OFFER_REVIEW --> CREATE_OFFER_PAGES
SCALE --> MARKETING_START

end
```

## Purpose

Collects funnel data, tracks 12 KPIs, unified dashboard, attribution check and leak-diagnosis with 9 fix paths.

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
