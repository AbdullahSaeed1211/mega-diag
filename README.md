```
flowchart TD

%% =========================================================
%% MASTER REVENUE + CUSTOMER JOURNEY ECOSYSTEM
%% =========================================================

START([New Client / Business]) --> DISCOVERY

%% =========================================================
%% 1. DISCOVERY + AUDIT
%% =========================================================

subgraph DISCOVERY_BLOCK["1. Discovery & Current-State Audit"]
direction TB

DISCOVERY[Collect Business Information]

DISCOVERY --> D1[Products / Services]
DISCOVERY --> D2[Target Markets]
DISCOVERY --> D3[Current Website]
DISCOVERY --> D4[Existing Marketing]
DISCOVERY --> D5[Existing CRM]
DISCOVERY --> D6[Sales Process]
DISCOVERY --> D7[Customer Support]
DISCOVERY --> D8[Retention Process]
DISCOVERY --> D9[Analytics / Tracking]
DISCOVERY --> D10[Existing Vendors / Developers]

D1 --> PRODUCT_MAP[Map Core Revenue Offers]
D2 --> PRODUCT_MAP
D3 --> TECH_AUDIT[Technical Audit]
D4 --> MARKETING_AUDIT[Marketing Audit]
D5 --> CRM_AUDIT[CRM Audit]
D6 --> SALES_AUDIT[Sales Audit]
D7 --> SUPPORT_AUDIT[Support Audit]
D8 --> RETENTION_AUDIT[Retention Audit]
D9 --> TRACKING_AUDIT[Tracking Audit]
D10 --> ACCESS_AUDIT[Access / Ownership Audit]

end

PRODUCT_MAP --> ECOSYSTEM_CHECK
TECH_AUDIT --> ECOSYSTEM_CHECK
MARKETING_AUDIT --> ECOSYSTEM_CHECK
CRM_AUDIT --> ECOSYSTEM_CHECK
SALES_AUDIT --> ECOSYSTEM_CHECK
SUPPORT_AUDIT --> ECOSYSTEM_CHECK
RETENTION_AUDIT --> ECOSYSTEM_CHECK
TRACKING_AUDIT --> ECOSYSTEM_CHECK
ACCESS_AUDIT --> ECOSYSTEM_CHECK

ECOSYSTEM_CHECK{Enough Access + Data<br/>to Audit Properly?}

ECOSYSTEM_CHECK -->|No| ACCESS_REQUEST[Request Missing Access / Credentials]
ACCESS_REQUEST --> ACCESS_TYPES

ACCESS_TYPES[Website / Hosting / Domain / Analytics / Ads / CRM / Email / Phone / Social / Payments]

ACCESS_TYPES --> ACCESS_RECEIVED{Access Received?}

ACCESS_RECEIVED -->|Yes| ECOSYSTEM_CHECK
ACCESS_RECEIVED -->|No| LIMITED_AUDIT[Proceed With Limited Audit<br/>Document Unknowns]
LIMITED_AUDIT --> WEBSITE_STAGE

ECOSYSTEM_CHECK -->|Yes| WEBSITE_STAGE

%% =========================================================
%% 2. WEBSITE FOUNDATION
%% =========================================================

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

%% =========================================================
%% 3. TRACKING + ATTRIBUTION
%% =========================================================

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

%% =========================================================
%% 4. CRM / GOHIGHLEVEL / SYSTEM OF RECORD
%% =========================================================

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

%% =========================================================
%% 5. CUSTOMER RESPONSE + INTENT
%% =========================================================

subgraph INTENT_BLOCK["5. Lead Intent & Response Handling"]
direction TB

RESPONSE_CHECK{Customer Responded?}

RESPONSE_CHECK -->|Yes| INTENT_CLASSIFY{Intent}
RESPONSE_CHECK -->|No| FOLLOWUP_SEQUENCE

FOLLOWUP_SEQUENCE[Automated Follow-Up Sequence]

FOLLOWUP_SEQUENCE --> FU1[Follow-Up 1]
FU1 --> FU2[Follow-Up 2]
FU2 --> FU3[Follow-Up 3]
FU3 --> FU4[Final Follow-Up]

FU1 --> RESPONSE_RECHECK{Response?}
FU2 --> RESPONSE_RECHECK
FU3 --> RESPONSE_RECHECK
FU4 --> RESPONSE_RECHECK

RESPONSE_RECHECK -->|Yes| INTENT_CLASSIFY
RESPONSE_RECHECK -->|No| NURTURE_OR_CLOSE

NURTURE_OR_CLOSE{Long-Term Value?}
NURTURE_OR_CLOSE -->|Yes| LONG_TERM_NURTURE[Move to Nurture Campaign]
NURTURE_OR_CLOSE -->|No| LOST_LEAD[Mark Lost / No Response]

LONG_TERM_NURTURE --> REACTIVATION_POOL

INTENT_CLASSIFY -->|Ready to Buy| SALES_READY
INTENT_CLASSIFY -->|Needs Information| HUMAN_REVIEW
INTENT_CLASSIFY -->|Book Appointment| BOOKING_FLOW
INTENT_CLASSIFY -->|Support Question| SUPPORT_FLOW
INTENT_CLASSIFY -->|Cancellation| RETENTION_FLOW
INTENT_CLASSIFY -->|Complaint| ESCALATION_FLOW
INTENT_CLASSIFY -->|Spam / Invalid| INVALID_LEAD
INTENT_CLASSIFY -->|Not Ready| LONG_TERM_NURTURE

INVALID_LEAD[Mark Spam / Invalid / Block if Needed]

end

%% =========================================================
%% 6. HUMAN STAFFING LAYER
%% =========================================================

subgraph STAFF_BLOCK["6. Customer Care / Sales Staffing Layer"]
direction TB

HUMAN_REVIEW{Human Needed?}

HUMAN_REVIEW -->|Yes| STAFF_ASSIGN{Assign Staff Type}

STAFF_ASSIGN -->|Inbound Calls| VOICE_AGENT[Voice / Customer Care Agent]
STAFF_ASSIGN -->|Emails| EMAIL_AGENT[Email Support Agent]
STAFF_ASSIGN -->|Sales Follow-Up| SALES_AGENT[Sales / Conversion Agent]
STAFF_ASSIGN -->|Retention| RETENTION_AGENT[Retention Agent]
STAFF_ASSIGN -->|Complex Issue| SUPERVISOR[Supervisor / Client Team]

VOICE_AGENT --> SLA_CHECK
EMAIL_AGENT --> SLA_CHECK
SALES_AGENT --> SLA_CHECK
RETENTION_AGENT --> SLA_CHECK
SUPERVISOR --> SLA_CHECK

SLA_CHECK{Answered Within SLA?}

SLA_CHECK -->|Yes| CUSTOMER_HANDLED
SLA_CHECK -->|No| MISSED_CONTACT[Missed Contact Alert]

MISSED_CONTACT --> CALLBACK[Priority Callback / Response]
CALLBACK --> CUSTOMER_HANDLED

CUSTOMER_HANDLED{Issue / Need Resolved?}

CUSTOMER_HANDLED -->|Yes| NEXT_ACTION
CUSTOMER_HANDLED -->|No| ESCALATE_INTERNAL[Escalate to Higher-Level Team]

ESCALATE_INTERNAL --> INTERNAL_RESPONSE{Internal Team Responds?}

INTERNAL_RESPONSE -->|Yes| CUSTOMER_HANDLED
INTERNAL_RESPONSE -->|No| ESCALATION_ALERT[Management Escalation]
ESCALATION_ALERT --> INTERNAL_RESPONSE

end

%% =========================================================
%% 7. APPOINTMENT FLOW
%% =========================================================

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

%% =========================================================
%% 8. SALES / CONVERSION
%% =========================================================

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

%% =========================================================
%% 9. PAYMENT + ORDER EXCEPTIONS
%% =========================================================

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

%% =========================================================
%% 10. FULFILLMENT / DELIVERY
%% =========================================================

subgraph FULFILLMENT_BLOCK["10. Fulfillment & Customer Experience"]
direction TB

FULFILLMENT_STAGE[Begin Fulfillment / Service Delivery]

FULFILLMENT_STAGE --> FULFILLMENT_CHECK{Fulfillment Successful?}

FULFILLMENT_CHECK -->|Yes| POST_PURCHASE
FULFILLMENT_CHECK -->|No| FULFILLMENT_ISSUE{Issue Type}

FULFILLMENT_ISSUE -->|Delay| DELAY_NOTICE[Proactive Customer Update]
FULFILLMENT_ISSUE -->|Incorrect Order| CORRECT_ORDER[Correct / Replace]
FULFILLMENT_ISSUE -->|Technical Problem| SUPPORT_FLOW
FULFILLMENT_ISSUE -->|Customer Error| CUSTOMER_EDUCATION[Guide Customer]
FULFILLMENT_ISSUE -->|Internal Error| INTERNAL_FIX[Internal Resolution]

DELAY_NOTICE --> FULFILLMENT_CHECK
CORRECT_ORDER --> FULFILLMENT_CHECK
CUSTOMER_EDUCATION --> FULFILLMENT_CHECK
INTERNAL_FIX --> FULFILLMENT_CHECK

end

%% =========================================================
%% 11. CUSTOMER SUPPORT
%% =========================================================

subgraph SUPPORT_BLOCK["11. Customer Support"]
direction TB

SUPPORT_FLOW{Support Type}

SUPPORT_FLOW -->|Basic FAQ| SELF_SERVICE[FAQ / Automated Answer]
SUPPORT_FLOW -->|Account / Order| EMAIL_AGENT
SUPPORT_FLOW -->|Urgent| VOICE_AGENT
SUPPORT_FLOW -->|Billing| BILLING_SUPPORT[Billing Team]
SUPPORT_FLOW -->|Medical / Regulated / Sensitive| CLIENT_SPECIALIST[Authorized Client Specialist]
SUPPORT_FLOW -->|Technical| TECH_SUPPORT[Technical Support]

SELF_SERVICE --> SUPPORT_RESOLVED
BILLING_SUPPORT --> SUPPORT_RESOLVED
CLIENT_SPECIALIST --> SUPPORT_RESOLVED
TECH_SUPPORT --> SUPPORT_RESOLVED

SUPPORT_RESOLVED{Resolved?}

SUPPORT_RESOLVED -->|Yes| POST_PURCHASE
SUPPORT_RESOLVED -->|No| SUPERVISOR

end

%% =========================================================
%% 12. POST-PURCHASE + RETENTION
%% =========================================================

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

%% =========================================================
%% 13. PAID / ORGANIC MARKETING
%% =========================================================

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

%% =========================================================
%% 14. COMPLAINT / ESCALATION
%% =========================================================

subgraph ESCALATION_BLOCK["14. Complaint & Escalation Management"]
direction TB

ESCALATION_FLOW{Severity}

ESCALATION_FLOW -->|Low| EMAIL_AGENT
ESCALATION_FLOW -->|Medium| SUPERVISOR
ESCALATION_FLOW -->|High / Legal / Compliance / Medical| CLIENT_EXECUTIVE[Client Executive / Authorized Team]

CLIENT_EXECUTIVE --> RESOLUTION_DOCUMENTED[Document Resolution]
SUPERVISOR --> RESOLUTION_DOCUMENTED

RESOLUTION_DOCUMENTED --> CUSTOMER_NOTIFICATION[Notify Customer]
CUSTOMER_NOTIFICATION --> SATISFACTION_CHECK

end

%% =========================================================
%% 15. STAFFING CAPACITY
%% =========================================================

subgraph STAFFING_BLOCK["15. Staffing Capacity & Operations"]
direction TB

STAFF_MONITOR[Monitor Workload]

STAFF_MONITOR --> VOLUME_CHECK{Lead / Call Volume Within Capacity?}

VOLUME_CHECK -->|Yes| SLA_MONITOR[Monitor SLA & Quality]
VOLUME_CHECK -->|No| HIRING_NEED[Additional Staffing Needed]

HIRING_NEED --> STAFF_COST[Estimate Staff Cost]
STAFF_COST --> CLIENT_APPROVAL{Client Approves Additional Staff?}

CLIENT_APPROVAL -->|Yes| RECRUIT[Recruit / Vet / Train]
CLIENT_APPROVAL -->|No| PRIORITIZE[Prioritize Leads / Adjust Coverage]

RECRUIT --> STAFF_ASSIGN
PRIORITIZE --> STAFF_ASSIGN

SLA_MONITOR --> QUALITY_CHECK{Quality Acceptable?}

QUALITY_CHECK -->|Yes| STAFF_MONITOR
QUALITY_CHECK -->|No| COACHING[Training / QA / Coaching]

COACHING --> PERFORMANCE_CHECK{Improved?}
PERFORMANCE_CHECK -->|Yes| STAFF_MONITOR
PERFORMANCE_CHECK -->|No| REPLACE_AGENT[Replace / Reassign Staff]
REPLACE_AGENT --> RECRUIT

end

CUSTOMER_HANDLED --> STAFF_MONITOR

%% =========================================================
%% 16. DATA + REPORTING
%% =========================================================

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

%% =========================================================
%% 17. COMMERCIAL / AGENCY MODEL
%% =========================================================

subgraph COMMERCIAL_BLOCK["17. Commercial Structure"]
direction TB

COMMERCIAL_START[Determine Scope]

COMMERCIAL_START --> STAFF_REQUIRED{Staff Required?}

STAFF_REQUIRED -->|Yes| STAFF_PRICING[Actual Staffing Cost]
STAFF_REQUIRED -->|No| SERVICE_SCOPE

STAFF_PRICING --> STAFF_MARGIN[Add Management / Staffing Margin]
STAFF_MARGIN --> STAFF_TOTAL[Client Staffing Fee]

SERVICE_SCOPE{Marketing / Development Required?}

SERVICE_SCOPE -->|Yes| PROJECT_COST[Separate Project / Monthly Service Cost]
SERVICE_SCOPE -->|No| REV_SHARE_CHECK

PROJECT_COST --> REV_SHARE_CHECK

REV_SHARE_CHECK{Performance / Revenue Share Included?}

REV_SHARE_CHECK -->|No| STANDARD_FEE[Standard Agency Fee Structure]
REV_SHARE_CHECK -->|Yes| EXPENSE_DEFINITION[Define Approved Direct Expenses]

EXPENSE_DEFINITION --> ATTRIBUTABLE_REV[Define Attributable Revenue]
ATTRIBUTABLE_REV --> REFUND_RULES[Define Refunds / Chargebacks]
REFUND_RULES --> PAYMENT_TIMING[Define Reporting + Payment Timing]
PAYMENT_TIMING --> AGENCY_SHARE[Agency Performance Fee]

STAFF_TOTAL --> CLIENT_COMMERCIAL_REVIEW
PROJECT_COST --> CLIENT_COMMERCIAL_REVIEW
STANDARD_FEE --> CLIENT_COMMERCIAL_REVIEW
AGENCY_SHARE --> CLIENT_COMMERCIAL_REVIEW

CLIENT_COMMERCIAL_REVIEW{Terms Approved?}

CLIENT_COMMERCIAL_REVIEW -->|Yes| GO_LIVE
CLIENT_COMMERCIAL_REVIEW -->|No| NEGOTIATE[Revise Scope / Margin / Fee / Share]

NEGOTIATE --> CLIENT_COMMERCIAL_REVIEW

end

%% =========================================================
%% 18. GO-LIVE READINESS
%% =========================================================

subgraph LAUNCH_BLOCK["18. Go-Live Checklist"]
direction TB

GO_LIVE[Pre-Launch Review]

GO_LIVE --> GL1{Website Ready?}
GL1 -->|No| WEBSITE_STAGE
GL1 -->|Yes| GL2

GL2{Landing Pages Ready?}
GL2 -->|No| CREATE_LPS
GL2 -->|Yes| GL3

GL3{Tracking Verified?}
GL3 -->|No| TRACK_VERIFY
GL3 -->|Yes| GL4

GL4{CRM + Automations Tested?}
GL4 -->|No| CRM_REVIEW
GL4 -->|Yes| GL5

GL5{Phone / Email / Forms Tested?}
GL5 -->|No| QA_COMMS[Fix Communications Routing]
GL5 -->|Yes| GL6

QA_COMMS --> GL5

GL6{Staff Trained + Available?}
GL6 -->|No| RECRUIT
GL6 -->|Yes| GL7

GL7{Reporting Ready?}
GL7 -->|No| REPORT_DASHBOARD
GL7 -->|Yes| LAUNCH

LAUNCH([Launch Ecosystem])

end

%% =========================================================
%% 19. LIVE ECOSYSTEM LOOP
%% =========================================================

LAUNCH --> MARKETING_START

CUSTOMER_CREATED --> REPORT_EVENT
LOST_LEAD --> REPORT_EVENT
INVALID_LEAD --> REPORT_EVENT
ARCHIVE_CONTACT --> REPORT_EVENT
HAPPY_CUSTOMER --> REPORT_EVENT
CANCEL_PROCESS --> REPORT_EVENT
APPOINTMENT_COMPLETE --> REPORT_EVENT
NO_SHOW --> REPORT_EVENT

%% =========================================================
%% TOP-LEVEL BUSINESS LOOP
%% =========================================================

REPORT_DASHBOARD --> BUSINESS_REVIEW{Monthly / Weekly Review}

BUSINESS_REVIEW -->|Growth Opportunity| SCALE
BUSINESS_REVIEW -->|Operational Issue| STAFF_MONITOR
BUSINESS_REVIEW -->|Website Issue| WEBSITE_STAGE
BUSINESS_REVIEW -->|Marketing Issue| MARKETING_START
BUSINESS_REVIEW -->|CRM Issue| CRM_REVIEW
BUSINESS_REVIEW -->|Retention Issue| RETENTION_FLOW
BUSINESS_REVIEW -->|Commercial Issue| COMMERCIAL_START
BUSINESS_REVIEW -->|Everything Healthy| CONTINUE[Continue + Monitor]

CONTINUE --> REPORT_EVENT
```
