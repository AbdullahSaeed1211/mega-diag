# 7. Calendar & Appointment Flow

> Handles availability, waitlist, confirmation, reminder sequence, show/no-show and reschedule into reactivation.

```mermaid
flowchart TD

subgraph BOOKING_BLOCK["7. Calendar & Appointment Flow"]
direction TB

BOOKING_FLOW{Appointment Available?}

BOOKING_FLOW -->|Yes| BOOK_APPT[Book Appointment]
BOOKING_FLOW -->|No| WAITLIST[Offer Alternative Time / Waitlist]

WAITLIST --> BOOK_APPT

BOOK_APPT --> CONFIRM_APPT[Send Confirmation]
CONFIRM_APPT --> REMINDER1[Reminder Sequence]
REMINDER1 --> SHOW_CHECK{Customer Shows?}

SHOW_CHECK -->|Yes| APPOINTMENT_COMPLETE[Appointment Completed]
SHOW_CHECK -->|No| NO_SHOW[No-Show Workflow]

NO_SHOW --> RESCHEDULE_ATTEMPT[Reschedule Outreach]
RESCHEDULE_ATTEMPT --> RESCHEDULED{Rescheduled?}

RESCHEDULED -->|Yes| BOOK_APPT
RESCHEDULED -->|No| REACTIVATION_POOL

APPOINTMENT_COMPLETE --> SALES_READY

end
```

## Purpose

Handles availability, waitlist, confirmation, reminder sequence, show/no-show and reschedule into reactivation.

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
