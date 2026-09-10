# 4. CRM, Lead Routing & Automation

> Deploys or reviews CRM, defines pipeline, maps 10 lead sources, handles routing, dedupe, consent and automated journey.

```mermaid
flowchart TD

subgraph CRM_BLOCK["4. CRM, Lead Routing & Automation"]
direction TB

CRM_STAGE{CRM Exists?}

CRM_STAGE -->|No| CRM_BUILD[Deploy CRM / GoHighLevel / Other]
CRM_STAGE -->|Yes| CRM_REVIEW[Review Existing CRM]

CRM_BUILD --> CRM_PIPELINE
CRM_REVIEW --> CRM_PIPELINE

CRM_PIPELINE{Sales Pipeline Defined?}

CRM_PIPELINE -->|No| BUILD_PIPELINE[Create Pipeline Stages]
CRM_PIPELINE -->|Yes| LEAD_SOURCE_MAP
BUILD_PIPELINE --> LEAD_SOURCE_MAP

LEAD_SOURCE_MAP[Define Lead Sources]

LEAD_SOURCE_MAP --> LS1[Website]
LEAD_SOURCE_MAP --> LS2[Landing Pages]
LEAD_SOURCE_MAP --> LS3[Phone]
LEAD_SOURCE_MAP --> LS4[Email]
LEAD_SOURCE_MAP --> LS5[Calendar]
LEAD_SOURCE_MAP --> LS6[WhatsApp / SMS]
LEAD_SOURCE_MAP --> LS7[Google Ads]
LEAD_SOURCE_MAP --> LS8[Meta Ads]
LEAD_SOURCE_MAP --> LS9[Organic / SEO]
LEAD_SOURCE_MAP --> LS10[Referral / Partner]

LS1 --> ROUTING
LS2 --> ROUTING
LS3 --> ROUTING
LS4 --> ROUTING
LS5 --> ROUTING
LS6 --> ROUTING
LS7 --> ROUTING
LS8 --> ROUTING
LS9 --> ROUTING
LS10 --> ROUTING

ROUTING{Every Lead Routed<br/>to Correct Owner?}

ROUTING -->|No| CREATE_ROUTING[Create Routing Rules]
CREATE_ROUTING --> DUPLICATE_CHECK

ROUTING -->|Yes| DUPLICATE_CHECK

DUPLICATE_CHECK{Duplicate Lead?}
DUPLICATE_CHECK -->|Yes| MERGE_LEAD[Merge / Update Existing Contact]
DUPLICATE_CHECK -->|No| CREATE_CONTACT[Create New Contact]

MERGE_LEAD --> CONSENT_CHECK
CREATE_CONTACT --> CONSENT_CHECK

CONSENT_CHECK{Communication Consent Available?}

CONSENT_CHECK -->|Yes| AUTOMATION_ENTRY
CONSENT_CHECK -->|No| LIMITED_CONTACT[Restrict Automated Outreach]
LIMITED_CONTACT --> HUMAN_REVIEW

AUTOMATION_ENTRY[Start Automated Journey]

AUTOMATION_ENTRY --> AUTO1[Instant Confirmation]
AUTO1 --> AUTO2[Email]
AUTO1 --> AUTO3[SMS / WhatsApp]
AUTO1 --> AUTO4[Calendar Link]
AUTO1 --> AUTO5[Internal Staff Alert]

AUTO2 --> RESPONSE_CHECK
AUTO3 --> RESPONSE_CHECK
AUTO4 --> RESPONSE_CHECK
AUTO5 --> RESPONSE_CHECK

end
```

## Purpose

Deploys or reviews CRM, defines pipeline, maps 10 lead sources, handles routing, dedupe, consent and automated journey.

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
