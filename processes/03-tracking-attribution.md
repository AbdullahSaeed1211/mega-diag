# 3. Tracking, Analytics & Attribution

> Installs and verifies the full tracking stack (GA, GTM, Ads, Pixel/CAPI, call/form/calendar, UTMs) with debug loop.

```mermaid
flowchart TD

subgraph TRACKING_BLOCK["3. Tracking, Analytics & Attribution"]
direction TB

TRACKING_STAGE{Tracking Installed Correctly?}

TRACKING_STAGE -->|No| INSTALL_TRACKING[Install Tracking Stack]
TRACKING_STAGE -->|Yes| TRACK_VERIFY

INSTALL_TRACKING --> T1[Google Analytics]
INSTALL_TRACKING --> T2[Google Tag Manager]
INSTALL_TRACKING --> T3[Google Ads Conversion Tracking]
INSTALL_TRACKING --> T4[Meta Pixel / CAPI]
INSTALL_TRACKING --> T5[Call Tracking]
INSTALL_TRACKING --> T6[Form Tracking]
INSTALL_TRACKING --> T7[Calendar Tracking]
INSTALL_TRACKING --> T8[UTM Standards]

T1 --> TRACK_VERIFY
T2 --> TRACK_VERIFY
T3 --> TRACK_VERIFY
T4 --> TRACK_VERIFY
T5 --> TRACK_VERIFY
T6 --> TRACK_VERIFY
T7 --> TRACK_VERIFY
T8 --> TRACK_VERIFY

TRACK_VERIFY{Conversions Firing Correctly?}

TRACK_VERIFY -->|No| FIX_TRACKING[Debug Attribution / Events]
FIX_TRACKING --> TRACK_VERIFY

TRACK_VERIFY -->|Yes| CRM_STAGE

end
```

## Purpose

Installs and verifies the full tracking stack (GA, GTM, Ads, Pixel/CAPI, call/form/calendar, UTMs) with debug loop.

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
