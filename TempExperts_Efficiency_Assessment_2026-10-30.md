# TempExperts — Marketing & Revenue Operations Efficiency Assessment

**Prepared for:** Ashley Rosulek, Marketing Ops / AI Systems Manager, Carter William LLC
**Date:** 2026-10-30
**Scope:** TempExperts brand, with cross-brand items where the shared HubSpot portal makes them inseparable
**Evidence base:** HubSpot portal "TempExperts" (ID 247558730) read live via API; "TempExperts Virtual Whiteboard" Google Sheet; Campaign Operating Model (2026-07-28); Q3 Campaign Brief (2026-07-28); Notion Q2 plan; Gmail traffic Aug–Oct 2026
**Not inspected:** Bullhorn / Loxo, SourceWhale, Haley Marketing CMS, HubSpot workflows list, GA4 report contents, Canva, Blaze.ai, O365 config. Zapier, Monday, Canva and Wix connectors failed to connect this session.

Every statement below is tagged **Fact**, **Observation**, **Interpretation**, **Hypothesis**, or **Recommendation**.

---

## 1. Executive Summary

TempExperts' revenue operations run on a Google Sheet, not on HubSpot or the ATS. The HubSpot portal is 31 days old, has one user, zero deals, zero forms, zero landing pages, and zero marketing sends. The Whiteboard sheet, edited today, holds the job board (592 rows), placements and margin math (1,787 rows), onboarding compliance (250 rows), a hand-typed lead log (143 rows), and weekly GP stats. It is owned by a personal Gmail account.

The largest efficiency gains are not in campaign execution. They are in (1) moving the three operational ledgers that live in the Whiteboard into systems that can be automated and reported on, (2) deciding the portal architecture that the July operating model flagged as Critical and that has since been answered by default, and (3) removing a file-shuttling habit that currently routes every deliverable through personal email.

Twelve recommendations follow. Five are quick wins executable in under a day each.

---

## 2. Current State

### 2.1 Technical Findings (System State)

| Area | Finding | Tag |
| --- | --- | --- |
| HubSpot portal | Portal name "TempExperts", Standard tier, created 2026-09-29, US/Eastern, USD | Fact |
| Users | 1 user (Ashley R). No teams configured. | Fact |
| Contacts | 62 total. 100% lifecycle = Lead. 100% candidate_status = Unassigned. 59 owned by Ashley, 3 unassigned. | Fact |
| Contact record sources | 32 EMAIL_INTEGRATION, 27 INTEGRATION, 2 INTERNAL_PROCESSING, 1 MEETINGS | Fact |
| Companies | 25 total, 100% source = CRM_SETTING (auto-created from contact email domains) | Fact |
| Deals | 0 records. Pipeline is the HubSpot default 7-stage sales pipeline. | Fact |
| Forms | 0 | Fact |
| Landing pages | 0 | Fact |
| Tickets | 0 records. Ticket pipeline is active (kickback emails published 2026-10-14). | Fact |
| Lists | 3: "ZoomInfo Contacts" (dynamic), "Keller North America Group A" and "Group B" (static) | Fact |
| Marketing emails | 14 objects. 12 are a Pivot Right nurture: SET A (6 automated emails, 2 published) and SET B (6 batch emails, all draft). From-name on both sets is "PivotRight". 2 are ticket kickbacks. | Fact |
| Email sends | 0 sends Aug 1 – Oct 27. Health score: NOT_ENOUGH_DATA for all 3 months. | Fact |
| Meetings | 1 meetings link (ashley-r) | Fact |
| Custom properties | Contact: candidate_status, pr_heard_about, pr_employees_affected, pr_rif_timeline. Company: industry_focus, number_of_open_roles. | Fact |
| Campaigns object | REQUIRES_ACCOUNT_MODIFICATION (not available on this tier) | Fact |
| Analytics | GA4 property "TempExperts" exists; a scheduled "Web & Job Board Performance" report emails weekly | Fact |
| ATS | Bullhorn → Loxo migration, planned cutover 2026-10-18 (per July plan). Post-cutover state not verified. | Fact (plan) / Unknown (state) |

### 2.2 Observed Reality (Operational Behavior)

| Area | Observation | Tag |
| --- | --- | --- |
| System of record | The Whiteboard sheet is the operating ledger: job orders, candidate pipeline per order, placements with pay/bill/markup, onboarding checklist, leads, weekly GP/hours/TTO/COB. Last edited 2026-10-30. | Fact |
| Sheet ownership | Owner is rstrother6@gmail.com, a personal account. Shared to Ashley 2026-10-01. | Fact |
| Lead capture | 143-row "Leads" tab (date, category, company, position, Bullhorn candidate, location, TE assigned). None of these companies appear as HubSpot deals. | Fact |
| Onboarding | 47-column tab tracking background, drug, E-Verify, direct deposit, pay card, benefits, approver and escalator per placement. Status values are free text ("Done", "Sent", "N/A", "Clear", "[merged]"). Columns AM–AU duplicate columns Q–Z. | Fact |
| PII in sheet | Candidate home addresses, phones, personal emails, age, gender, ethnicity (Mock Trial tab) in a sheet with link-based sharing | Fact |
| Brand mixing | HubSpot portal named TempExperts contains Pivot Right emails, Pivot Right form-field properties, and a CarterWill tab lives in the TempExperts Whiteboard | Fact |
| Portal architecture decision | July operating model rated "one portal vs. per-brand" as Critical and open. No decision document found. The portal now holds two brands' assets with no brand property, no brand subscription types, and one sending identity. | Observation |
| Q3 campaign | "Every Shift Covered" brief planned Aug 24 launch with LP, form, 4-email nurture, 6 outbound waves. HubSpot shows 0 forms, 0 LPs, 0 sends. | Fact |
| Content workflow | 10 of 16 emails to/from the tempexperts.com mailbox in 45 days are self-sent attachments (social post PDFs, calendars, audit HTML, resume, phone photos) from personal Gmail to work mailbox. | Fact |
| Email auto-capture | 32 contacts (52%) were created by the Outlook/Gmail integration. Sampled newest record is a content vendor, not a prospect. | Fact / Observation |
| Enrichment | ZoomInfo → HubSpot sync is live (27 contacts). The dynamic list exists. No territory property, no routing workflow visible. | Fact / Observation |
| Nurture duplication | SET B reproduces SET A's six-touch structure as batch emails. Two copies of one sequence to maintain. | Observation |

### 2.3 Interpretations and Hypotheses

- **Interpretation.** HubSpot is currently a Pivot Right nurture tool and a ZoomInfo landing zone. TempExperts' revenue motion has not been moved into it.
- **Interpretation.** The portal-architecture question has been answered by circumstance: one shared portal. That is a workable choice on this tier, but only if brand is modeled explicitly.
- **Hypothesis.** The Q3 campaign slipped because the Loxo cutover, onboarding, and Pivot Right nurture build consumed the window. Needs confirmation.
- **Hypothesis.** SET B exists to allow manual batch sends while SET A's workflow enrollment is unresolved. Needs confirmation.
- **Hypothesis.** The "C" / "A" column headers on the Whiteboard board are a status code (Confirmed / Active, or Client / Applicant). The sheet carries no legend.

---

## 3. Risk Assessment

| # | Issue | Severity | Business risk | Operational risk | Technical risk | Reporting risk |
| --- | --- | --- | --- | --- | --- | --- |
| R1 | Operating ledger owned by a personal Gmail account | Critical | Loss of access on departure; no retention control | Single owner can lock or delete | No audit trail, no backup policy | All GP/margin history is in one file |
| R2 | Candidate PII (address, age, ethnicity) in link-shared sheet | Critical | Privacy exposure; EEO data co-located with hiring decisions | Accidental forwarding | No access logging | None |
| R3 | Lead log outside CRM | High | Leads worked from memory; no follow-up SLA | Ron is the single assignee | Nothing to automate against | No pipeline, no conversion rate, no source attribution |
| R4 | Shared portal with no brand model | High | Pivot Right and TempExperts audiences cross-contaminate; CAN-SPAM identity per brand unclear | Every list and workflow needs manual brand filtering | Subscription types, sender domains, and reports cannot be segmented | Cross-brand referral (G7) cannot be measured |
| R5 | Default sales pipeline, 0 deals | High | Job orders have no stage, value, or close date in any marketing-visible system | Whiteboard remains the only pipeline | Nothing for Skills or dashboards to read | Unified dashboard (G5) has no revenue source |
| R6 | Email auto-capture polluting contacts | Medium | Vendors and personal contacts become "Leads" | Manual cleanup | Lifecycle and health metrics skewed from day one | Lead counts overstated |
| R7 | Duplicate nurture sets | Medium | Copy drift between A and B | Double edits | Two assets per change | Split performance data |
| R8 | ATS ↔ HubSpot sync unverified post-cutover | Medium | Marketing cannot see placements | Manual reconciliation | Loxo API mapping unknown | Attribution blocked |
| R9 | Self-emailed attachments as file transfer | Low | Version confusion; personal-account retention of work product | Time cost per hand-off | No single source for assets | None |

---

## 4. Recommendations

### Quick Wins (≤1 day each)

| # | Recommendation | Business impact | Technical impact | Effort | Risk if ignored | Dependencies |
| --- | --- | --- | --- | --- | --- | --- |
| Q1 | Transfer ownership of the Whiteboard to a company-controlled account (Google Workspace or export to SharePoint/O365) and restrict sharing to named users | Closes R1, R2 exposure | Ownership transfer only | 1 hour | Loss of the operating ledger | Ron Strother agreement; company Google or O365 admin |
| Q2 | Split the Mock Trial and Onboarding PII into a separately permissioned file; strip ethnicity/age from any tab used for assignment | Closes R2 | Two files instead of one | 2 hours | Privacy exposure | Q1 |
| Q3 | Add a `brand` multi-select property on Contact, Company, and Deal; backfill 62 contacts; create one subscription type per brand | Makes the shared portal governable; unblocks R4 | 3 properties, 2–4 subscription types | 3 hours | Every future list and report needs manual brand logic | None |
| Q4 | Disable automatic contact creation from the email integration, or restrict it to replies from non-vendor domains | Stops R6 at source | One settings change | 15 min | Database quality degrades weekly | None |
| Q5 | Replace the three self-send email patterns with one shared folder per brand (O365 is already in the stack) | Removes R9; saves roughly one hand-off per working day | None | 1 hour | Continued version confusion | O365 admin |

### 30-Day Initiatives (operational)

| # | Recommendation | Business impact | Technical impact | Effort | Risk if ignored | Dependencies |
| --- | --- | --- | --- | --- | --- | --- |
| 30-1 | Rebuild the deal pipeline as a **Job Order pipeline** mirroring the Whiteboard columns (Open → Sourcing → Submitted → Interview → Offer → Started / Lost), with Temp/Temp-Hire/DH as deal type and bill rate, pay rate, markup as properties. Import the 143 Leads rows. | Gives TempExperts a pipeline marketing can see; retires the Leads tab | Custom pipeline + 6 properties + 1 import | 2 days | R3, R5 persist | Q3; confirm C/A legend with Ron |
| 30-2 | Consolidate SET A / SET B into one workflow-driven sequence; keep batch copies only if a documented manual-send use case exists | Halves nurture maintenance | 6 fewer email assets | 0.5 day | R7 | Decision on batch use case |
| 30-3 | Verify HubSpot ↔ Loxo sync post-cutover: which object maps to which, which direction, which fields. Document in the Living Tech Stack Audit. | Unblocks attribution and dashboard | Integration mapping doc + 5 test records | 1–2 days | R8 | Loxo admin access |
| 30-4 | Build the territory-routing workflow on the ZoomInfo dynamic list using the new `brand` property plus a `territory` property, assigning to Ron/territory rep. Add Ron and Vivianne as HubSpot users. | Delivers the JD's named automation; ends single-seat portal | 1 property, 1 workflow, 2 seats | 2 days | ZoomInfo contacts sit unworked | Territory rules from Ron; seat cost approval |

### 60-Day Initiatives (process)

| # | Recommendation | Business impact | Technical impact | Effort | Risk if ignored | Dependencies |
| --- | --- | --- | --- | --- | --- | --- |
| 60-1 | Move the Onboarding checklist into the HubSpot **ticket pipeline** (already enabled): one ticket per placement, one stage per compliance step, kickback emails already exist | Compliance steps become trackable with SLAs and owners; removes 47-column free-text tab | Ticket pipeline with ~8 stages, 10 properties | 3 days | Onboarding misses stay invisible | 30-1 (ticket associates to deal) |
| 60-2 | Rebuild the Q3 "Every Shift Covered" campaign as Q4/Q1 with the now-existing plumbing: 1 LP, 1 form (RFP), 4-email nurture under the TempExperts subscription type | First TempExperts marketing sends; first form data | 1 LP, 1 form, 4 emails, 1 workflow | 5 days | TempExperts stays unmarketed in HubSpot | Q3, 30-1, Haley Marketing LP decision |
| 60-3 | Replace the Weekly Stats tab with a HubSpot dashboard fed by the Job Order pipeline (GP, hours, TTO, COB by rep), with the sheet retained as read-only history | Weekly Friday check-in produced from data, not retyped | 1 dashboard, 6 reports | 2 days | Manual weekly stat entry continues | 30-1, 30-3 |

### 90-Day Initiatives (strategic)

| # | Recommendation | Business impact | Technical impact | Effort | Risk if ignored | Dependencies |
| --- | --- | --- | --- | --- | --- | --- |
| 90-1 | Document the portal architecture decision formally (shared portal + brand model) and the per-brand sending domain and DMARC posture for pivotright and tempexperts | Closes the July Critical item; deliverability protected before volume | DNS records; HubSpot sending domains | 2 days | Deliverability incident on first real send | IT/domain admin |
| 90-2 | Instrument the TempExperts → Pivot Right referral as a workflow (RIF signal on a TempExperts contact → Pivot Right deal + task), using the `pr_*` properties already created | G7 becomes measurable | 1 workflow, 1 form | 3 days | Referral revenue unmeasured | Q3, 30-1 |
| 90-3 | Retire the Whiteboard as a system of record; keep only the visual board view if Ron needs it, generated from the pipeline | Single source of truth | Sheet becomes a report | 1 week + change management | Dual entry forever | 30-1, 60-1, 60-3 |

---

## 5. Implementation Roadmap

| Week | Items | Owner | Gate |
| --- | --- | --- | --- |
| 1 | Q1, Q2, Q4, Q5 | Ashley + Ron | Sheet ownership transferred |
| 2 | Q3, 30-2 | Ashley | Brand property live on 62 contacts |
| 3–4 | 30-1, 30-4 | Ashley + Ron | Job Order pipeline holds the 143 leads; routing fires on next ZoomInfo sync |
| 5–6 | 30-3, 60-3 | Ashley + Loxo admin | Sync mapping documented; Friday report pulled from dashboard |
| 7–8 | 60-1, 60-2 | Ashley + Vivianne | First TempExperts send under its own subscription type |
| 9–12 | 90-1, 90-2, 90-3 | Ashley + ownership | Whiteboard read-only |

---

## 6. Success Metrics

| Metric | Baseline (2026-10-30) | 90-day target | Source |
| --- | --- | --- | --- |
| Operational ledgers outside a governed system | 3 (job orders, onboarding, leads) | 0 | Inventory |
| HubSpot users | 1 | 3+ | HubSpot settings |
| Deals in Job Order pipeline | 0 | ≥143 (historic) + all new orders | HubSpot |
| Contacts with `brand` populated | 0 of 62 | 100% | HubSpot |
| Contacts created by email auto-capture per month | 32 in 31 days | <5 | HubSpot record source |
| Self-sent attachment emails per month | ~7 | 0 | Gmail |
| TempExperts marketing sends | 0 | ≥1 campaign, ≥4 emails | HubSpot analytics |
| Nurture assets per sequence | 2 sets (12 emails) | 1 set (6 emails) | HubSpot |
| Weekly stats entry method | Manual sheet | Dashboard | Observation |

---

## 7. What to Investigate (data needed before 30-1 and 30-3)

Potential contributors to the gap between the July plan and the October portal state may include Loxo cutover load, Pivot Right nurture priority, Haley Marketing LP dependency, and seat or budget constraints. These are hypotheses; none is confirmed.

Required inputs:

1. Loxo post-cutover state and API access level.
2. Meaning of the "C" / "A" codes and the "HN / EH / IM / KF / VB / RS / CC" candidate suffixes on the Whiteboard.
3. Whether SourceWhale writes activity back to HubSpot or Loxo.
4. HubSpot workflows list (not readable through this session's tools).
5. Which sending domain each brand's emails authenticate under today.
6. Contents of the GA4 "Web & Job Board Performance" report (attachment not retrievable here).

---

## Appendix A — HubSpot inventory snapshot, 2026-10-30

| Object | Count | Notes |
| --- | --- | --- |
| Contacts | 62 | all Lead, all candidate_status Unassigned |
| Companies | 25 | all auto-created from email domains |
| Deals | 0 | default pipeline |
| Tickets | 0 | pipeline active, kickbacks published |
| Forms | 0 | |
| Landing pages | 0 | |
| Lists | 3 | 1 dynamic (ZoomInfo), 2 static (Keller A/B) |
| Marketing emails | 14 | 12 Pivot Right nurture, 2 ticket kickbacks |
| Marketing sends, Aug–Oct | 0 | |
| Users | 1 | |
| Meetings links | 1 | |

## Appendix B — Whiteboard sheet inventory

| Tab | Range | Role today | Proposed destination |
| --- | --- | --- | --- |
| TempExperts Whiteboard | A1:H592 | Live job board with candidate pipeline per order | Job Order pipeline (deals) |
| Off The Board | A1:AD1787 | Placements, bill/pay/markup, future starts | Deals (closed) + Loxo |
| Skill Market positions | A1:O181 | Board by skill category | Deal property: category |
| CarterWill Open Orders | A1:L19 | Legal recruiting orders (other brand) | Deals with brand = CarterWill |
| Mock Trial | A1:Z246 | Event attendee roster with sensitive PII | Separate restricted file; Marketing Event object if retained |
| Onboarding | A1:AU250 | Compliance checklist per placement | Ticket pipeline |
| Leads | A1:M143 | Hand-typed inbound/outbound leads | Deals (Open stage) |
| Weekly Stats & ATH | A1:I13 | GP, hours, TTO, COB, margin | Dashboard |
