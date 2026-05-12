# Kitchen Electronics Factory — Intragroup Supply Coordination

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Factory ID:** CCK-EL-KIT
> **Location:** Agbara Industrial Estate, Lagos State / Sagamu, Ogun State
> **Document Version:** 1.0 | **Owner:** Supply Chain Manager
> **Status:** Design Complete — Activation pending factory commissioning

---

## 1. Overview

The Coo-Cah Kitchen Electronics Factory operates within the **Coo-Cah Technologies Holdings** manufacturing ecosystem and depends on two sister factories for critical inputs. This document defines the intragroup supply coordination agreements, call-off procedures, escalation paths, and service levels that govern materials flow between the three factories.

| Supply Relationship | Supplier Factory | Materials | Status |
|---------------------|-----------------|-----------|--------|
| Link A | Coo-Cah Plastics Factory (Agbara) | Plastic housings, refrigerator liners, SDA casings | Planned — activate at production start |
| Link B | Coo-Cah Personal Electronics Factory (Agbara/Sagamu) | PCB assemblies (Phase 2 consolidation target) | Planned — Phase 2 |
| Link C | Coo-Cah Power Electronics / Garage Factory (Sagamu) | UPS and inverter backup units | Planned — one-off at commissioning |

All intragroup transactions are governed by the **Coo-Cah Group Transfer Pricing Policy** and recorded in the group ERP system (SAP/Oracle/Odoo) using intercompany purchase orders and delivery notes.

---

## 2. Link A — Coo-Cah Plastics Factory → Kitchen Electronics (Primary, Daily)

### 2.1 Materials Supplied

| Component | Part Number Prefix | Specification | Daily Volume | Safety Stock |
|-----------|-------------------|---------------|--------------|-------------|
| Microwave oven outer plastic housing | CCK-PLAS-MW-HSG | ABS HH, food-grade lacquer, cosmetic class A | 200 units/day | 7 days |
| Microwave door inner frame | CCK-PLAS-MW-DFR | ABS, microwave-transparent grade | 200 units/day | 7 days |
| SDA housing sets — blender | CCK-PLAS-SDA-BL | ABS/PP, food-grade, cosmetic class A | 500 units/day | 7 days |
| SDA housing sets — kettle | CCK-PLAS-SDA-KT | ABS/PP, food-grade | 350 units/day | 7 days |
| SDA housing sets — rice cooker | CCK-PLAS-SDA-RC | PP, heat-resistant, food-grade | 270 units/day | 7 days |
| SDA housing sets — toaster | CCK-PLAS-SDA-TS | ABS/HIPS, heat-resistant | 300 units/day | 7 days |
| Refrigerator interior liner | CCK-PLAS-REF-LIN | HIPS, food-safe white, no-warp spec | 320 units/day | 7 days |
| Cooker control panel housing | CCK-PLAS-CK-PNL | PC+ABS, heat-resistant class B | 180 units/day | 7 days |

### 2.2 Logistics & Delivery Schedule

| Parameter | Detail |
|-----------|--------|
| Transport | Dedicated intragroup truck — Coo-Cah Plastics to Kitchen Electronics |
| Frequency | 2 deliveries per day (Morning run: 06:00; Afternoon run: 13:00) |
| Route | Coo-Cah Plastics Factory → A1 Agbara/Sagamu corridor → Kitchen Electronics Z1 (RMS) dock |
| Distance | ~12 km within Agbara/Sagamu industrial corridor |
| Transit time | ~25–35 minutes per run |
| Vehicle type | 7-tonne flatbed or curtainsider with ESD-safe racking for housings |
| Packaging | Reusable plastic dunnage trays (Coo-Cah standard tray system) |
| Driver | Coo-Cah Group Logistics — not outsourced |

### 2.3 Quality Gate at Receipt

All incoming plastic components from the Plastics Factory pass through a **Goods Receipt QC scan** at Z1 (Raw Material Store) before entering production:

| QC Check | Method | Accept Criteria | Reject Action |
|----------|--------|-----------------|---------------|
| Dimensional check | Coordinate Measuring Machine or gauge | Within ±0.3 mm on critical dimensions | Return to Plastics Factory; NCR raised |
| Cosmetic — surface | 100-lux visual inspection | No scratches, sink marks, short-shots visible at 0.5 m | Return to Plastics Factory |
| Material certificate | Review plastic lot certificate | ABS/PP/HIPS food-grade cert present | Hold and escalate to QA |
| Barcode scan | MES goods receipt scan | Part number + batch code matches PO | Reject with NCR |
| Quantity verify | Count vs delivery note | ±2 units tolerance | Debit note issued if short |

### 2.4 Call-Off Procedure

1. **Daily kanban signal:** MES materials module generates a daily call-off for each housing type at 15:00 the day before delivery, based on the next day's production schedule.
2. **Call-off transmitted:** MES sends intercompany call-off to Coo-Cah Plastics Factory MES/ERP via REST API (`/api/v1/interco/call-off`).
3. **Plastics Factory confirms:** Confirmation acknowledgement returned within 2 hours.
4. **Amendment window:** Call-off quantities can be revised up or down by ±15% up to 20:00 the evening before delivery.
5. **Emergency top-up:** If intra-day stock falls below safety stock level, an emergency call-off can be triggered by the Supply Chain Coordinator; Plastics Factory commits to 4-hour response.

### 2.5 Service Level Agreement

| KPI | Target | Measurement | Escalation Trigger |
|-----|--------|-------------|-------------------|
| On-time delivery | ≥ 97% of deliveries on schedule | MES goods receipt timestamp vs scheduled window | < 95% in any week |
| Quantity accuracy | ≥ 99% of deliveries correct quantity | MES goods receipt scan vs PO | < 98% in any week |
| Quality pass rate | ≥ 98% of components pass goods receipt QC | MES QC scan records | < 96% in any shipment |
| Emergency call-off response | ≤ 4 hours from request to delivery | Timestamp log | > 4 hours on any occasion |
| Lead time (standard) | 1–2 days (call-off to delivery) | MES order-to-receipt | > 2 days on two consecutive occasions |

### 2.6 Escalation Path — Link A

| Level | Trigger | Escalation Action | Owner |
|-------|---------|-------------------|-------|
| Level 1 | Single delivery late / quality issue | Supply Chain Coordinator contacts Plastics Factory Production Controller | Kitchen Electronics Supply Chain Coordinator |
| Level 2 | Two consecutive misses on any SLA KPI | Kitchen Electronics Supply Chain Manager contacts Plastics Factory Operations Manager | Kitchen Electronics Supply Chain Manager |
| Level 3 | Sustained failure (≥ 3 days disruption) | Group Supply Chain Director convenes cross-factory recovery meeting | Group Supply Chain Director |
| Level 4 | Inability to supply for ≥ 5 days | Group CEO notified; external spot purchase activated | Group CEO |

---

## 3. Link B — Coo-Cah Personal Electronics Factory → Kitchen Electronics (Phase 2)

### 3.1 Overview

In Phase 1, the Kitchen Electronics Factory operates its own in-house **SMT PCB line** (Z2) to produce all circuit boards for its appliances. The supply from the Personal Electronics Factory is a **Phase 2 consolidation target** — designed to shift PCB manufacturing responsibility to the larger, more capable PE factory SMT line, freeing the Kitchen Electronics SMT line for higher-mix / lower-volume board types.

| Phase | PCB Source | Rationale |
|-------|------------|-----------|
| Phase 1 (2025–2027) | In-house SMT line (Z2) | Own production while PE factory PCB capacity is dedicated to PE products |
| Phase 2 (2028–2029) | Coo-Cah Personal Electronics SMT line (primary for volume boards) + in-house backup | Consolidation enables lower cost per board; PE SMT line runs at higher utilisation |

### 3.2 Phase 2 Target Materials

| PCB Assembly | Part Number | Volume | Specification |
|-------------|------------|--------|---------------|
| Refrigerator control board | CCK-PCB-FRIDGE-V2 | 350 pcs/day | Siemens Opcenter BOM; SMT + THT hybrid |
| SDA generic control platform | CCK-PCB-SDA-GEN | 1,200 pcs/day | SMT; single-sided; volume part |
| Microwave controller PCB | CCK-PCB-MW-CTRL | 200 pcs/day | SMT + THT; high-voltage creepage clearances |

### 3.3 Phase 2 Coordination Prerequisites

The following must be achieved before Link B activates:

- [ ] PE SMT line Phase 2 capacity expansion confirmed
- [ ] CCK PCB design files transferred to PE factory quality system
- [ ] Joint qualification run (FAI) completed on PE SMT line for each board type
- [ ] Intercompany supply agreement signed
- [ ] MES-to-MES API integration between Kitchen Electronics and Personal Electronics tested

---

## 4. Link C — Coo-Cah Power Electronics / Garage Factory → Kitchen Electronics (One-Off, Commissioning)

### 4.1 Materials Supplied

These are one-off commissioning purchases — not recurring supply.

| Item | Part Number | Qty | Specification | Purpose |
|------|------------|-----|---------------|---------|
| Rack-mount UPS | CCG-UPS-1kVA | 8 units | 1 kVA rack-mount; 15 min backup at full load | MES edge server room (Z16); critical IT backup |
| Pure sinewave inverter | CCG-INV-PSW-3kVA | 4 units | 3 kVA pure sinewave; ATEX-compliant enclosure | Gas zone (Z5) — gas monitoring systems; ATEX requirement |

### 4.2 Coordination Procedure

1. Kitchen Electronics Engineering Manager raises intercompany purchase order in ERP.
2. Garage Power Electronics Factory confirms lead time (typically 2–4 weeks from order).
3. Units delivered and installed by Coo-Cah Group Electrical team.
4. Kitchen Electronics Facilities Manager signs acceptance certificate.
5. Warranty: 24 months from commissioning date; fault returns handled intercompany within 5 working days.

### 4.3 ATEX Compliance Note

The 4 × CCG-INV-PSW-3kVA inverters destined for Z5 (R600a Gas Charging Zone) must be installed in **ATEX Zone 2-rated enclosures** before installation. The Garage Power Electronics Factory supplies the inverter unit; the ATEX enclosure is procured separately by Kitchen Electronics Facilities team and fitted by a certified ATEX electrician.

---

## 5. Group Transfer Pricing & Financial Settlement

| Parameter | Detail |
|-----------|--------|
| Pricing basis | Group cost + 8% standard markup (as per group transfer pricing policy) |
| Settlement cycle | Monthly intercompany netting — cleared by Group Finance by the 10th of the following month |
| Invoice format | Intercompany invoice raised in ERP by supplying factory; auto-matched to Kitchen Electronics GRN |
| Currency | Nigerian Naira (₦) for all intragroup transactions |
| Dispute resolution | Supply Chain Director → Group CFO within 30 days if not resolved at operational level |
| External benchmark check | Annual review vs. external market prices to ensure arm's-length pricing |

---

## 6. Communication & Coordination Cadence

| Forum | Frequency | Participants | Agenda |
|-------|-----------|-------------|--------|
| Daily call-off system | Automated (MES-to-MES) | No human needed — automated | Stock levels, next-day call-offs |
| Weekly supply review | Every Monday 09:00 | Supply Chain Coordinators — all 3 factories | Delivery performance, quality issues, next-week outlook |
| Monthly supply board | Monthly | Supply Chain Managers + Operations Managers | KPI review, SLA performance, phase planning |
| Quarterly intragroup review | Quarterly | Group Supply Chain Director + Factory Directors | Phase 2 readiness, capacity, pricing review |

---

## 7. Emergency / Disruption Protocol

If Coo-Cah Plastics Factory experiences a supply disruption affecting any housing component, the following fall-back sequence is activated:

| Step | Action | Trigger | Lead Time |
|------|--------|---------|-----------|
| 1 | Draw down to zero from Kitchen Electronics Z1 safety stock (7 days) | Supply disruption confirmed | Immediate |
| 2 | Activate spot purchase from approved external plastic moulder (Lagos/Agbara corridor) | Safety stock < 3 days | 3–5 days for small quantities |
| 3 | Convene cross-factory recovery meeting (Level 3 escalation) | Day 3 of disruption | Same day |
| 4 | Adjust Kitchen Electronics production schedule — prioritise products with adequate housing stock | Day 5 if no resolution | Same day |

---

*For supply chain BOM details, refer to [docs/supply-chain.md](./supply-chain.md).*
*For MES API integration (intercompany call-off endpoint), refer to [docs/mes-integration.md](./mes-integration.md).*
*For implementation gate criteria, refer to [implementation-plan.md](./implementation-plan.md).*
