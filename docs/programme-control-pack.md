# Kitchen Electronics Factory — Programme Control Pack

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Factory ID:** CCK-EL-KIT
> **Document Version:** 1.0 | **Owner:** Programme Director / PMO
> **Status:** Live — master tracker for the two-week mobilisation sprint

---

## 1. Purpose

This document is the **single control pack** for the mobilisation sprint. It consolidates deliverables, owners, target dates, dependencies, gates, evidence, decision points, and blocker escalation rules into one working tracker.

---

## 2. Master Deliverable Tracker

| ID | Deliverable | Owner | Target Date | Dependency | Gate | Evidence | Current State |
|----|-------------|-------|-------------|------------|------|----------|---------------|
| CTRL-01 | Control pack activated | Programme Director / PMO | Week 1 — Day 1 | None | G1 | This document | ✅ Live |
| CTRL-02 | NIPC Pioneer Status pack drafted | Regulatory Affairs Manager | Week 1 — Day 4 | CAC, CapEx plan, tax docs | G1 | [regulatory-submission-pack.md](./regulatory-submission-pack.md) | In progress |
| CTRL-03 | NESREA EIA pack drafted | Regulatory Affairs Manager | Week 1 — Day 4 | EIA consultant pack, site data, process description | G1 | [regulatory-submission-pack.md](./regulatory-submission-pack.md) | In progress |
| CTRL-04 | Architect shortlist and IFC brief issued | Facilities & Engineering Manager | Week 1 — Day 4 | Approved scope, procurement support | G1/G2 | [architect-ifc-delivery-plan.md](./architect-ifc-delivery-plan.md) | In progress |
| CTRL-05 | Pentest kickoff scheduled | InfoSec Lead | Week 1 — Day 3 | Contact matrix, staging owner, vendor confirmation | G1 | [pentest-kickoff-readiness.md](./pentest-kickoff-readiness.md) | In progress |
| CTRL-06 | Leadership hiring slate approved | HR Director | Week 1 — Day 5 | Budget approval, hiring priority order | G1 | [leadership-governance-plan.md](./leadership-governance-plan.md) | In progress |
| CTRL-07 | Supplier qualification framework agreed | Supply Chain Manager | Week 1 — Day 5 | Commodity categories, QA inputs, regulatory inputs | G1 | [supplier-qualification-readiness.md](./supplier-qualification-readiness.md) | In progress |
| CTRL-08 | NIPC pack submitted or approval-to-submit signed | Regulatory Affairs Manager | Week 2 — Day 2 | CTRL-02 | G1 | Submission receipt / approval checklist | Planned |
| CTRL-09 | NESREA EIA submitted or in final legal review | Regulatory Affairs Manager | Week 2 — Day 3 | CTRL-03, site pack | G1/G2 | Submission receipt / legal sign-off note | Planned |
| CTRL-10 | Architect down-selection completed | Facilities & Engineering Manager | Week 2 — Day 3 | CTRL-04, commercial review | G1/G2 | Bid evaluation + recommendation | Planned |
| CTRL-11 | Pentest pre-engagement checklist complete | InfoSec Lead / Smart Factory Lead | Week 2 — Day 3 | CTRL-05 | G1/G3 | [pentest-kickoff-readiness.md](./pentest-kickoff-readiness.md) | Planned |
| CTRL-12 | Site lease / acquisition decision paper issued | Legal Counsel / Finance Lead | Week 2 — Day 4 | Site commercial terms, board decision path | G2 | Decision paper | Planned |
| CTRL-13 | Intragroup supply sign-off session held | Supply Chain Manager | Week 2 — Day 4 | Named approvers confirmed | G1 | [intragroup-supply-coordination.md](./intragroup-supply-coordination.md) | Planned |
| CTRL-14 | Weekly executive dashboard published | Programme Director | Week 2 — Day 5 | Tracker status, blocker log, decision log | G1/G2 | Section 4 of this document | Planned |

---

## 3. Critical-Path Priorities

These items are managed as the sprint critical path:

| Rank | Item | Why It Matters | Escalation Owner |
|------|------|----------------|------------------|
| 1 | NESREA EIA submission | Unlocks civil works and infrastructure sequence | Programme Director |
| 2 | Site lease / acquisition decision | Required before site-specific permits, architect appointment, and contractor mobilisation | Legal Counsel |
| 3 | Architect appointment + IFC delivery | Unlocks BIM GUID completion and spatial model precision | Facilities & Engineering Manager |
| 4 | Pentest kickoff readiness | Clears the path for staging security validation before broader IT/OT rollout | InfoSec Lead |
| 5 | Approved Supplier List framework | Enables controlled supplier qualification and long-lead procurement preparation | Supply Chain Manager |

---

## 4. Weekly Executive Dashboard

### 4.1 Headline Status

| Area | Status | This Week Outcome | Key Blocker | Decision Needed |
|------|--------|-------------------|-------------|-----------------|
| Regulatory | Amber | NIPC and NESREA packs drafted and reviewed | Final legal exhibits | Approval to submit |
| Site / Commercial | Amber | Lease / acquisition decision paper assembled | Commercial term alignment | Preferred site commercial route |
| Facilities / BIM | Amber | Architect scope issued with IFC requirement | Bidder nomination and commercial evaluation | Down-select architect |
| Smart Factory / Security | Amber | Pentest kickoff and readiness checklist prepared | Staging IP ranges and test accounts | Confirm testing window |
| Procurement / Supply Chain | Amber | ASL framework agreed; critical suppliers grouped by commodity | Commodity owner sign-off | Freeze qualification order |
| Governance / HR | Amber | Leadership slate and governance cadence documented | Final budget confirmation | Approve priority hires |

### 4.2 30-Day Look-Ahead

| Horizon | Focus |
|---------|-------|
| Days 1–10 | Submit regulatory packs; down-select architect; complete pentest readiness; approve ASL framework |
| Days 11–20 | Resolve site commercial decision; issue architect appointment; commence supplier qualification; confirm pentest execution window |
| Days 21–30 | Manage submission feedback; drive IFC delivery plan; prepare long-lead PO release gate |

---

## 5. Decision Log

| Decision ID | Topic | Required By | Decision Owner | Inputs Required | Status |
|-------------|-------|-------------|----------------|-----------------|--------|
| DEC-01 | Site commercial route (lease vs acquisition) | Week 2 — Day 4 | Legal Counsel / Finance Lead | Term sheet, legal review, CapEx impact | Open |
| DEC-02 | Architect selection | Week 2 — Day 3 | Facilities & Engineering Manager | Bid evaluation, IFC commitment, fees | Open |
| DEC-03 | Pentest execution window | Week 2 — Day 2 | InfoSec Lead | Staging readiness, vendor confirmation | Open |
| DEC-04 | Regulatory submission release | Week 2 — Day 3 | Programme Director | Pack completeness, legal review | Open |
| DEC-05 | Supplier qualification order | Week 2 — Day 5 | Supply Chain Manager | Commodity criticality, QA input, lead times | Open |

---

## 6. Blocker Escalation Register

| Blocker Type | Trigger | Escalation Rule | Owner |
|--------------|---------|-----------------|-------|
| Missing approval | Required sign-off delayed more than 48 hours | Escalate at next decision forum; notify Programme Director same day | Deliverable owner |
| Missing data pack | Inputs unavailable for more than 24 hours | Escalate to function lead; assign recovery owner | PMO |
| External vendor delay | Vendor non-response for 2 business days | Escalate to procurement sponsor | Procurement Lead |
| Cross-functional dependency | Deliverable blocked by another workstream | Resolve in daily blocker review; hard escalate if unresolved within 48 hours | Programme Director |

---

## 7. Evidence Standard

Every tracked item must have one primary evidence artefact:

- submission receipt
- signed checklist
- approved decision note
- issued brief / bid pack
- meeting minutes with named attendees
- linked repository document with current status

No item may be marked complete without evidence linked in the tracker.

---

*For sprint objectives and cadence, refer to [mobilisation-sprint.md](./mobilisation-sprint.md).*
*For detailed work packages, refer to the linked readiness documents in this tracker.*
