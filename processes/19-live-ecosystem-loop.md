# 19. Live Ecosystem Loop

> Connects launch to live marketing, funnels all terminal events into reporting and drives the weekly/monthly business review loop.

```mermaid
flowchart TD

%% 19. Live Ecosystem Loop — detached high-level view
LAUNCH([Launch Ecosystem]) --> MARKETING_START

MARKETING_START[Traffic Strategy] --> CHANNEL_DECISION
CHANNEL_DECISION{Channel}

CUSTOMER_CREATED[Customer / Order Confirmed] --> REPORT_EVENT
LOST_LEAD[Mark Lost / No Response] --> REPORT_EVENT
INVALID_LEAD[Mark Spam / Invalid / Block if Needed] --> REPORT_EVENT
ARCHIVE_CONTACT[Archive / Suppress] --> REPORT_EVENT
HAPPY_CUSTOMER[Active Customer] --> REPORT_EVENT
CANCEL_PROCESS[Process Cancellation] --> REPORT_EVENT
APPOINTMENT_COMPLETE[Appointment Completed] --> REPORT_EVENT
NO_SHOW[No-Show Workflow] --> REPORT_EVENT

REPORT_EVENT[Collect Funnel Data] --> METRICS[Track KPIs] --> REPORT_DASHBOARD[Unified Dashboard]
REPORT_DASHBOARD --> BUSINESS_REVIEW{Monthly / Weekly Review}

BUSINESS_REVIEW -->|Growth Opportunity| SCALE[Scale Winning Channels / Offers]
BUSINESS_REVIEW -->|Operational Issue| STAFF_MONITOR[Monitor Workload]
BUSINESS_REVIEW -->|Website Issue| WEBSITE_STAGE{Website Live?}
BUSINESS_REVIEW -->|Marketing Issue| MARKETING_START
BUSINESS_REVIEW -->|CRM Issue| CRM_REVIEW[Review Existing CRM]
BUSINESS_REVIEW -->|Retention Issue| RETENTION_FLOW{Why Cancelling?}
BUSINESS_REVIEW -->|Commercial Issue| COMMERCIAL_START[Determine Scope]
BUSINESS_REVIEW -->|Everything Healthy| CONTINUE[Continue + Monitor]
CONTINUE --> REPORT_EVENT

SCALE --> MARKETING_START
STAFF_MONITOR --> VOLUME_CHECK
WEBSITE_STAGE --> WEBSITE_REASON

```

## Purpose

Connects launch to live marketing, funnels all terminal events into reporting and drives the weekly/monthly business review loop.

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
