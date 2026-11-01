# TempExperts — Operations Efficiency Assessment

**Prepared for:** Ashley Rosulek, Marketing Ops / AI Systems Manager, Carter William LLC
**Date:** 2026-11-01
**Scope:** TempExperts operating processes and tooling, excluding HubSpot (out of scope by request)
**Evidence base:** "TempExperts Virtual Whiteboard" Google Sheet (8 tabs, edited 2026-10-30); Campaign Operating Model (2026-07-28); Q3 Campaign Brief (2026-07-28); Living Tech Stack Audit (referenced); Notion Q2 plan; Gmail traffic Aug–Oct 2026
**Not inspected:** Bullhorn / Loxo, SourceWhale, Haley Marketing CMS, GA4 report contents, Canva, Blaze.ai, O365 config. Zapier, Monday, Canva and Wix connectors failed to connect this session.

Every statement below is tagged **Fact**, **Observation**, **Interpretation**, **Hypothesis**, or **Recommendation**.

---

## 1. Executive Summary

TempExperts runs its day-to-day revenue operation on one Google Sheet. The Whiteboard holds the live job board (592 rows), placements with pay, bill and markup math (1,787 rows), the onboarding compliance checklist (250 rows, 47 columns), a hand-typed lead log (143 rows), and the weekly GP, hours, TTO and COB stats. It is owned by a personal Gmail account and shared by link.

The ATS migration from Bullhorn to Loxo was scheduled to cut over on 2026-10-18. If Loxo is live, the sheet now duplicates work the ATS is designed to hold: job orders, candidate pipeline per order, placements and starts. The efficiency opportunity is therefore less about adding tools and more about retiring double entry.

Three habits compound the problem: deliverables are shuttled from personal Gmail to the work mailbox as attachments, social content is produced as static PDFs with no scheduling tool, and weekly stats are retyped from the sheet rather than reported from a system.

Eleven recommendations follow. Five are quick wins executable in under a day each.

---

## 2. Current State

### 2.1 Technical Findings (System State)

| Area | Finding | Tag |
| --- | --- | --- |
| Operating ledger | Google Sheet "TempExperts Virtual Whiteboard", created 2020-04-02, 8 tabs, last edited 2026-10-30 | Fact |
| Sheet ownership | Owner rstrother6@gmail.com (personal account). Shared to Ashley 2026-10-01. | Fact |
| ATS | Bullhorn → Loxo migration; planned cutover 2026-10-18. Post-cutover state not verified. | Fact (plan) / Unknown (state) |
| Outbound | SourceWhale is the sequence engine, TempExperts only | Fact (per July audit) |
| Enrichment | ZoomInfo Copilot in use | Fact (per July audit) |
| Website / SEO | Haley Marketing owns TempExperts.com and SEO; job feed integration must re-point to Loxo (P14) | Fact (per July audit) |
| Analytics | GA4 property "TempExperts" exists; a scheduled "Web & Job Board Performance" report emails weekly (last 2026-10-26) | Fact |
| Social | LinkedIn corporate page, LinkedIn Recruiter, Facebook page (admin invite 2026-09) | Fact |
| Design / content | Canva brand kit and templates; Blaze.ai flagged in July as overlapping with Cowork Skills | Fact (per July audit) |
| Productivity | O365 in the stack | Fact (per July audit) |
| Job board | tampabay@tempexperts.com sends job board confirmations | Fact |

### 2.2 Observed Reality (Operational Behavior)

| Area | Observation | Tag |
| --- | --- | --- |
| Job board | "TempExperts Whiteboard" tab (A1:H592): one column per open order with client, title, pay, schedule, and candidates listed below with date and recruiter initials. Status codes "C" / "A" in row 1 carry no legend. | Fact |
| Placements | "Off The Board" tab (A1:AD1787): future starts, bill rate, pay rate, markup multiplier, WC rate, and GP per placement. Columns Q–AA repeat columns J–O. | Fact |
| Skill boards | "Skill Market positions" tab (A1:O181) duplicates the board layout by category (Shipping/Warehouse etc.). | Fact |
| Other brand | "CarterWill Open Orders" tab (A1:L19) lives inside the TempExperts sheet. | Fact |
| Onboarding | "Onboarding" tab (A1:AU250): background, drug, E-Verify, direct deposit, pay card, web time/benefits, approver, escalator. Status values are free text ("Done", "Sent", "N/A", "Clear", "[merged]"). Columns AM–AU duplicate columns Q–Z. | Fact |
| Leads | "Leads" tab (A1:M143): date, category, company, position, Bullhorn candidate, location, TE assigned. Most rows have only a mailing address in column M. | Fact |
| Weekly stats | "Weekly Stats & ATH" tab: GP $25,002, hours 2,700, TTO 60, COB 13, GM 25.09%, GP/hour $9.26, MU 51.68% (dated 3/19). All-time highs dated 2021–2023. Individual GP by rep (Ron, Erik, Hollee, Sam). | Fact |
| PII | Candidate home addresses, phones, personal emails, age, gender, ethnicity (Mock Trial tab), in a link-shared sheet | Fact |
| Content workflow | 10 of 16 threads touching the tempexperts.com mailbox in 45 days are self-sent attachments from personal Gmail: social post PDFs, content calendar PDF, audit HTML, resume, phone photos | Fact |
| Social production | October posts for TempExperts, Pivot Right and Resume Professors exist as PDFs. No scheduling tool identified. | Fact / Observation |
| Q3 campaign | "Every Shift Covered" brief planned Aug 24 launch with 6 outbound waves, LP, nurture, PR pitch. No evidence of execution found in Drive or mail. | Observation |
| Reporting | Weekly Friday check-in exists (per July deck). Stats are entered by hand in the sheet. | Fact / Observation |

### 2.3 Interpretations and Hypotheses

- **Interpretation.** The Whiteboard is a visual board, a placement ledger, a compliance tracker, a CRM and a KPI report in one file. Each of those has a better-fit home in the existing stack; the sheet persists because it is fast and everyone can see it.
- **Interpretation.** The duplicated column blocks (Off The Board Q–AA, Onboarding AM–AU) indicate at least one prior attempt to restructure the sheet that was never finished.
- **Hypothesis.** The Weekly Stats tab is stale (last dated entry 3/19) and the real weekly numbers are being produced elsewhere, possibly in Bullhorn reports. Needs confirmation.
- **Hypothesis.** The Q3 campaign slipped because the Loxo cutover and onboarding consumed the window. Needs confirmation.
- **Hypothesis.** "C" / "A" means Confirmed / Active or Client / Applicant. The sheet carries no legend.

---

## 3. Risk Assessment

| # | Issue | Severity | Business risk | Operational risk | Technical risk | Reporting risk |
| --- | --- | --- | --- | --- | --- | --- |
| R1 | Operating ledger owned by a personal Gmail account | Critical | Loss of access on departure; no retention control | Single owner can lock or delete | No audit trail, no backup policy | All GP and margin history in one file |
| R2 | Candidate PII incl. ethnicity and age in a link-shared sheet | Critical | Privacy exposure; EEO data co-located with hiring decisions | Accidental forwarding | No access logging | None |
| R3 | Job orders and placements double-entered in sheet and ATS | High | Recruiter time spent on duplicate entry; two versions of truth | Board and ATS drift | Loxo adoption undermined | Fill rate and time-to-fill unmeasurable |
| R4 | Onboarding compliance tracked in free text | High | Missed I-9, E-Verify or background steps | No owner, no SLA, no reminder | Nothing to automate | Compliance status unreportable |
| R5 | Lead log outside any system with follow-up | High | Leads worked from memory; single assignee | No SLA | Nothing to sequence | No conversion or source data |
| R6 | ATS ↔ website job feed not re-pointed to Loxo | Medium | Stale or missing jobs on TempExperts.com | Manual job posting | Haley dependency | Job board traffic unattributed |
| R7 | Self-emailed attachments as file transfer | Medium | Work product retained in a personal account; version confusion | Time per hand-off | No single asset source | None |
| R8 | Social content as static PDFs, no scheduler | Low | Posting cadence depends on manual effort | Missed posts | None | No engagement data |
| R9 | Weekly stats retyped | Low | Friday check-in depends on manual entry | Errors | None | Stale KPIs (last dated 3/19) |

---

## 4. Recommendations

### Quick Wins (≤1 day each)

| # | Recommendation | Business impact | Technical impact | Effort | Risk if ignored | Dependencies |
| --- | --- | --- | --- | --- | --- | --- |
| Q1 | Transfer ownership of the Whiteboard to a company-controlled account (Google Workspace or export to SharePoint/O365) and restrict sharing to named users | Closes R1 | Ownership transfer only | 1 hour | Loss of the operating ledger | Ron Strother agreement; company Google or O365 admin |
| Q2 | Move the Mock Trial roster and the Onboarding PII columns into a separately permissioned file; remove ethnicity and age from any tab used for assignment | Closes R2 | Two files instead of one | 2 hours | Privacy exposure | Q1 |
| Q3 | Add a legend tab to the Whiteboard: status codes, recruiter initials (HN, EH, IM, KF, VB, RS, CC), employment type codes (DH, T-H, T-P), markup conventions | Removes tribal knowledge; makes any later migration mappable | One tab | 1 hour | Migration mapping impossible | Ron |
| Q4 | Delete the duplicated column blocks (Off The Board Q–AA, Onboarding AM–AU) after confirming they are not referenced by formulas | Halves the width of two tabs; reduces entry error | Sheet cleanup | 1 hour | Continued double entry inside the sheet | Q3 |
| Q5 | Replace self-send email transfers with one shared folder per brand (O365/SharePoint or Google Drive) and a single "Deliverables" subfolder convention | Removes R7; saves roughly one hand-off per working day | None | 1 hour | Version confusion persists | O365 or Workspace admin |

### 30-Day Initiatives (operational)

| # | Recommendation | Business impact | Technical impact | Effort | Risk if ignored | Dependencies |
| --- | --- | --- | --- | --- | --- | --- |
| 30-1 | Confirm Loxo cutover state. If live, make Loxo the system of record for job orders, candidate pipeline and placements, and freeze the "TempExperts Whiteboard", "Skill Market positions" and "Off The Board" tabs as read-only history | Ends R3 double entry | Loxo job order and placement configuration | 3 days | Two systems of truth indefinitely | Loxo admin access; Ron buy-in |
| 30-2 | Rebuild the visual board as a Loxo pipeline view (or a Google Sheet that reads from a Loxo export) so Ron keeps the at-a-glance layout without typing into it | Preserves the board habit while removing entry | Loxo saved view or scheduled export | 2 days | Board reverts to manual | 30-1 |
| 30-3 | Re-point the Haley Marketing job feed to Loxo (P14) and verify the GA4 "Web & Job Board Performance" report still populates | Closes R6; jobs on site stay current | Haley integration change | 2 days plus Haley lead time | Stale job board | 30-1, Haley Marketing |
| 30-4 | Move the Leads tab into SourceWhale (or Loxo companies/contacts if SourceWhale is sequence-only): one record per lead, owner, next action date | Closes R5; leads get a follow-up cadence | 143-row import | 1 day | Leads worked from memory | Q3; SourceWhale admin |

### 60-Day Initiatives (process)

| # | Recommendation | Business impact | Technical impact | Effort | Risk if ignored | Dependencies |
| --- | --- | --- | --- | --- | --- | --- |
| 60-1 | Convert the Onboarding checklist into a structured tracker with one row per placement, one dropdown per compliance step (Not started / Sent / Done / N/A), owner and due date, and a conditional-format overdue flag. Build it in Loxo if it supports onboarding tasks; otherwise a locked Google Sheet with data validation. | Closes R4; missed steps become visible | Data validation + conditional format, or Loxo tasks | 2 days | Compliance misses stay invisible | Q2, Q3 |
| 60-2 | Replace the Weekly Stats tab with a scheduled Loxo (or Bullhorn) report for GP, hours, TTO, COB by rep, delivered to the Friday check-in | Closes R9 | Saved report + schedule | 1 day | Manual retyping continues | 30-1 |
| 60-3 | Adopt a social scheduler (Canva Content Planner is already in the stack; LinkedIn native scheduling is free) and retire the PDF-per-month hand-off | Closes R8; engagement data captured | Canva Content Planner setup | 1 day | Manual posting | Q5 |
| 60-4 | Decide Blaze.ai: retire if Cowork Skills cover the same drafting, per the July risk note | Cost saved; one fewer tool | Vendor cancellation | 0.5 day | Duplicate spend | Skill parity check |

### 90-Day Initiatives (strategic)

| # | Recommendation | Business impact | Technical impact | Effort | Risk if ignored | Dependencies |
| --- | --- | --- | --- | --- | --- | --- |
| 90-1 | Re-run the "Every Shift Covered" demand-gen campaign on the now-clean plumbing: SourceWhale waves from the territory Skill, Haley LP, LinkedIn organic cadence, GA4 measurement | First real load test of the outreach Skill | Per the Q3 brief | 6 weeks | Skill stays untested | 30-3, 30-4, 60-3 |
| 90-2 | Retire the Whiteboard as a system of record; keep only the board view generated from Loxo | Single source of truth | Sheet becomes a report | 1 week + change management | Dual entry forever | 30-1, 30-2, 60-1, 60-2 |

---

## 5. Implementation Roadmap

| Week | Items | Owner | Gate |
| --- | --- | --- | --- |
| 1 | Q1, Q2, Q3, Q5 | Ashley + Ron | Sheet ownership transferred; legend published |
| 2 | Q4, 30-1 (confirm Loxo state) | Ashley + Loxo admin | Loxo confirmed live or not |
| 3–4 | 30-2, 30-4 | Ashley + Ron | Board view reads from Loxo; leads loaded |
| 5–6 | 30-3, 60-2 | Ashley + Haley | Job feed on Loxo; Friday stats from report |
| 7–8 | 60-1, 60-3, 60-4 | Ashley + Ron | Onboarding tracker live; October-style PDFs retired |
| 9–12 | 90-1, 90-2 | Ashley + ownership | Campaign in market; Whiteboard read-only |

---

## 6. Success Metrics

| Metric | Baseline (2026-10-30) | 90-day target | Source |
| --- | --- | --- | --- |
| Operational ledgers in the Whiteboard | 5 (board, placements, onboarding, leads, stats) | 0 editable; board view read-only | Inventory |
| Whiteboard owner | Personal Gmail | Company account | Drive metadata |
| Tabs containing candidate PII | 2 | 0 (moved to restricted file) | Inventory |
| Duplicate column blocks | 2 | 0 | Sheet |
| Self-sent attachment emails per month | ~7 | 0 | Gmail |
| Job orders entered twice (sheet + ATS) | All | 0 | Recruiter check |
| Onboarding steps with free-text status | 100% | 0% | Tracker |
| Weekly stats entry method | Manual | Scheduled report | Observation |
| Social posts scheduled vs. manually posted | 0% scheduled | ≥80% scheduled | Scheduler |

---

## 7. What to Investigate

Potential contributors to the gap between the July plan and the current state may include Loxo cutover load, Haley Marketing dependency on the LP, and single-operator bandwidth across four brands. These are hypotheses; none is confirmed.

Required inputs:

1. Loxo post-cutover state: live, partial, or deferred. Which objects migrated.
2. Meaning of "C" / "A" and the recruiter initials on the Whiteboard.
3. Whether the Weekly Stats tab is still maintained or superseded by an ATS report.
4. Whether SourceWhale holds company and contact records or sequences only.
5. Haley Marketing's job feed source today (Bullhorn, Loxo, or manual).
6. Contents of the GA4 "Web & Job Board Performance" report.
7. Whether Loxo supports onboarding tasks or checklists natively.

---

## Appendix — Whiteboard sheet inventory

| Tab | Range | Role today | Proposed destination |
| --- | --- | --- | --- |
| TempExperts Whiteboard | A1:H592 | Live job board with candidate pipeline per order | Loxo job orders; board view generated from Loxo |
| Off The Board | A1:AD1787 | Placements, bill/pay/markup, future starts | Loxo placements |
| Skill Market positions | A1:O181 | Board by skill category | Loxo saved view by category |
| CarterWill Open Orders | A1:L19 | Legal recruiting orders (other brand) | CarterWill's own tracker or Loxo with brand tag |
| Mock Trial | A1:Z246 | Event attendee roster with sensitive PII | Separate restricted file |
| Onboarding | A1:AU250 | Compliance checklist per placement | Structured tracker (Loxo tasks or locked sheet) |
| Leads | A1:M143 | Hand-typed inbound/outbound leads | SourceWhale or Loxo companies |
| Weekly Stats & ATH | A1:I13 | GP, hours, TTO, COB, margin | Scheduled ATS report |
