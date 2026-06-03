# Kitchen Electronics Factory — Architect Appointment & IFC Delivery Plan

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Factory ID:** CCK-EL-KIT
> **Document Version:** 1.0 | **Owner:** Facilities & Engineering Manager
> **Status:** Mobilisation Sprint — procurement-ready architect brief

---

## 1. Purpose

This document defines the sprint work package for appointing the factory architect and ensuring that **IFC model delivery** is an explicit contractual obligation. The architect appointment must support both building delivery and downstream BIM / digital twin requirements in this repository.

---

## 2. Sprint Outcome Required

| Outcome | Why It Matters |
|---------|----------------|
| Architect shortlist issued | Allows rapid commercial and technical comparison |
| IFC deliverables embedded in scope | Unlocks BIM GUID completion and spatial precision updates |
| Preferred bidder down-selected | Prevents continued blockage of IFC-dependent documents |

---

## 3. Shortlist Structure

The procurement process should maintain at least three qualified bidders:

| Bidder Slot | Required Capability | Mandatory |
|-------------|---------------------|-----------|
| Architect-01 | Industrial factory design; Nigerian permitting experience | Yes |
| Architect-02 | BIM-led delivery; IFC export capability; MEP coordination | Yes |
| Architect-03 | Hazardous area / industrial services coordination; fast-track documentation delivery | Yes |

> Replace slot identifiers with legal bidder names once procurement confirms the shortlist.

---

## 4. Mandatory Scope of Services

The architect scope must include:

1. Full architectural design package for the factory site and building
2. Coordination with structural, MEP, EHS, and smart-factory inputs
3. Issue of BIM deliverables aligned to factory zones and asset anchors
4. Delivery of **IFC model files** suitable for downstream GUID extraction and spatial data population

### 4.1 IFC Deliverable Requirements

| Requirement | Minimum Standard |
|-------------|------------------|
| File format | IFC 4.0 or later |
| Coordinate basis | Shared project coordinate system aligned to factory origin used in [bim/zone-boundaries.md](./bim/zone-boundaries.md) |
| Object identification | Stable IFC GUIDs for building, zones, rooms, major infrastructure, and anchor-bearing assets |
| Update cadence | Issue at concept freeze, design freeze, and pre-construction release |
| Zone mapping | All zones Z1–Z17 must be traceable to IFC spaces / areas |
| Delivery package | Native model + IFC export + issue note + revision register |

### 4.2 Contract Clauses to Include

| Clause | Intent |
|--------|--------|
| IFC delivery is a milestone deliverable | Prevents BIM output from becoming optional |
| GUID stability across revisions | Protects downstream BIM and digital twin references |
| Model issue dates tied to payment milestones | Creates enforceable delivery leverage |
| Data handover rights to Coo-Cah | Ensures reuse in MES, AMR, and digital twin contexts |

---

## 5. Bid Evaluation Matrix

| Criterion | Weight | Evaluation Question |
|-----------|--------|---------------------|
| Industrial factory experience | 25% | Has the bidder delivered comparable industrial buildings? |
| BIM / IFC capability | 25% | Can the bidder reliably issue IFC models with stable GUIDs? |
| Programme responsiveness | 20% | Can the bidder support the mobilisation timeline? |
| Hazard / utility coordination | 15% | Can the bidder design for R600a, SMT ESD, and IT/MES spaces? |
| Commercials | 15% | Are fees and deliverables acceptable for scope? |

---

## 6. Decision and Evidence Requirements

| Deliverable | Evidence |
|-------------|----------|
| Shortlist confirmed | Bidder list with contacts and scope issue date |
| Brief issued | Architect RFP / scope document |
| Down-selection completed | Evaluation matrix + recommendation note |
| IFC date locked | Contract term sheet or appointment letter |

---

## 7. Link to Repository BIM Work

The architect appointment directly enables completion of:

- [bim/zone-boundaries.md](./bim/zone-boundaries.md)
- [bim/asset-anchors.md](./bim/asset-anchors.md)
- future digital twin spatial model reconciliation

---

*For the programme dependency tracker, refer to [programme-control-pack.md](./programme-control-pack.md).*
*For current BIM placeholders, refer to [bim/zone-boundaries.md](./bim/zone-boundaries.md) and [bim/asset-anchors.md](./bim/asset-anchors.md).*
