# Coo-Cah Kitchen Electronics Factory — Phase 1 Implementation Plan

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Factory ID:** CCK-EL-KIT
> **Location:** Agbara Industrial Estate, Lagos State / Sagamu, Ogun State
> **Document Version:** 1.0 | **Owner:** Factory Programme Director
> **Status:** Active — Phase 1 Planning Sprint

---

## 1. Purpose & Scope

This document defines the implementation plan for the Coo-Cah Kitchen Electronics Factory from planning and design through to full Phase 1 production readiness. It covers six parallel workstreams, gate criteria, critical dependencies, and machine-free documentation deliverables that can be completed before physical commissioning begins.

The plan is structured around three gates:

| Gate | Name | Criteria |
|------|------|----------|
| Gate 1 | Design Complete | All planning, BIM, regulatory, and supply-chain documentation signed off |
| Gate 2 | Infrastructure Ready | Civil works, utilities, MES servers, and network infrastructure commissioned |
| Gate 3 | Production Ready | All production lines, safety systems, and MES fully commissioned; OEE baseline achieved |

---

## 2. Programme Overview

| Phase | Period | Theme | Investment (₦B) |
|-------|--------|-------|-----------------|
| Phase 1 | 2025–2027 | Foundation — MES, AMR fleet, SMT, refrigerator line | 1.2 |
| Phase 2 | 2028–2029 | Robotics on fridge line; AI QC; digital twin live | 1.8 |
| Phase 3 | 2030–2031 | Lights-out SDA; AI scheduling; net-zero certification | 1.4 |

**Current Phase:** Phase 1 — Planning & Design
**Programme Director:** TBC (appointed at Gate 1)
**Master Repo Reference:** [oumar-code/Coo-Kah-Doks](https://github.com/oumar-code/Coo-Kah-Doks)

---

## 3. Workstream Structure

The Phase 1 implementation is organised into six parallel workstreams, each with its own lead, deliverables, and gate checkpoints.

### Workstream 1 — Regulatory & Legal

**Lead:** Regulatory Affairs Manager
**Objective:** Secure all permits, licences, and certifications required before construction and production.

| # | Deliverable | Owner | Target | Gate | Machine Required? |
|---|-------------|-------|--------|------|-------------------|
| R1 | NIPC Pioneer Status application submitted | Regulatory Affairs | Q3 2025 | G1 | ❌ No |
| R2 | NESREA Environmental Impact Assessment submitted | Regulatory Affairs | Q3 2025 | G1 | ❌ No |
| R3 | NESREA EIA approved | Regulatory Affairs | Q4 2025 | G2 | ❌ No |
| R4 | Lagos State EIA clearance (LASEPA) | Regulatory Affairs | Q4 2025 | G2 | ❌ No |
| R5 | Factory site acquired / lease executed (Agbara) | Legal / Finance | Q4 2025 | G2 | ❌ No |
| R6 | NESREA R600a refrigerant handling permit | Regulatory Affairs | Q2 2026 | G2 | ✅ Yes — gas zone |
| R7 | Factory registration (FMITI Factories Act) | HR / Legal | Q3 2026 | G3 | ✅ Yes — building |
| R8 | SON MANCAP application — all Phase 1 SKUs | Regulatory Affairs | Q3 2026 | G3 | ✅ Yes — samples |
| R9 | ISO 9001:2015 QMS certification audit | QA Manager | Q3 2027 | G3 | ✅ Yes — audit |
| R10 | Fire Safety Certificate (Lagos/Ogun State) | EHS Manager | Q3 2026 | G3 | ✅ Yes — inspection |

### Workstream 2 — Facilities & Civil Works

**Lead:** Facilities & Engineering Manager
**Objective:** Deliver the 15,000 m² factory building, utilities, and special infrastructure (R600a zone, SMT ESD zone, solar/BESS) ready for equipment installation.

| # | Deliverable | Owner | Target | Gate | Machine Required? |
|---|-------------|-------|--------|------|-------------------|
| F1 | Architectural drawings finalised | Facilities | Q3 2025 | G1 | ❌ No |
| F2 | BIM model (IFC) delivered by architect | Facilities / BIM team | Q3 2025 | G1 | ❌ No |
| F3 | Zone boundary coordinates populated in BIM registry | Smart Factory | Q4 2025 | G1 | ❌ No |
| F4 | Asset anchor coordinates populated in BIM registry | Smart Factory | Q4 2025 | G1 | ❌ No |
| F5 | Civil construction commenced | Contractor | Q1 2026 | G2 | ❌ No |
| F6 | Building structure complete | Contractor | Q4 2026 | G2 | ✅ Yes — construction |
| F7 | R600a gas zone (Z5) commissioned — ATEX certified | Facilities | Q1 2027 | G2 | ✅ Yes — ATEX |
| F8 | SMT ESD zone (Z2) commissioned | Facilities | Q2 2026 | G2 | ✅ Yes — infrastructure |
| F9 | Rooftop solar (700 kWp) and BESS (800 kWh) energised | Energy team | Q2 2026 | G2 | ✅ Yes — electrical |
| F10 | Compressed air system commissioned (Atlas Copco GA55+) | Facilities | Q2 2026 | G2 | ✅ Yes — mechanical |

### Workstream 3 — Smart Factory & MES

**Lead:** Smart Factory Core Team / IT Manager
**Objective:** Deploy Siemens Opcenter MES, MES edge node, network infrastructure, and AI platform stubs before production equipment arrives.

| # | Deliverable | Owner | Target | Gate | Machine Required? |
|---|-------------|-------|--------|------|-------------------|
| S1 | MES architecture design document | Smart Factory | Q3 2025 | G1 | ❌ No |
| S2 | Sensor registry — design-phase (this repo) | Smart Factory | Q4 2025 | G1 | ❌ No |
| S3 | AI platform status document (stub endpoints) | Smart Factory / AI Team | Q4 2025 | G1 | ❌ No |
| S4 | Penetration test scoping document | InfoSec / Digital Encode | Q4 2025 | G1 | ❌ No |
| S5 | IT/OT network infrastructure deployed (Z16) | IT Manager | Q2 2026 | G2 | ✅ Yes — server room |
| S6 | MES edge node commissioned | Smart Factory | Q3 2026 | G2 | ✅ Yes — servers |
| S7 | Siemens Opcenter Execution Discrete deployed | Smart Factory | Q3 2026 | G3 | ✅ Yes — MES |
| S8 | OPC-UA integrations live (SMT line) | Smart Factory | Q3 2026 | G3 | ✅ Yes — machines |
| S9 | R600a gas MES module commissioned | Smart Factory | Q2 2027 | G3 | ✅ Yes — gas zone |
| S10 | Penetration test executed; findings remediated | Digital Encode / InfoSec | Q4 2025 | G1 | ❌ No — staging env |
| S11 | AI platform production go-live (GPU node) | AI Team / Smart Factory | Q4 2026 | G3 | ✅ Yes — GPU server |
| S12 | MES data completeness ≥ 95% sustained | Smart Factory | Q4 2027 | G3 | ✅ Yes — live ops |

### Workstream 4 — Supply Chain & Procurement

**Lead:** Supply Chain Manager
**Objective:** Qualify suppliers, execute all import logistics, and activate intra-group supply agreements before production start.

| # | Deliverable | Owner | Target | Gate | Machine Required? |
|---|-------------|-------|--------|------|-------------------|
| SC1 | Intra-group supply coordination agreement (Plastics, Power Electronics) | Supply Chain | Q4 2025 | G1 | ❌ No |
| SC2 | Approved Supplier List (ASL) finalised | Supply Chain | Q4 2025 | G1 | ❌ No |
| SC3 | Long-lead items PO issued (compressors, magnetrons) | Procurement | Q1 2026 | G2 | ❌ No |
| SC4 | Safety stock targets established in ERP/MES | Supply Chain | Q2 2026 | G2 | ❌ No |
| SC5 | First container of compressors received and QC-cleared | Supply Chain | Q2 2026 | G2 | ✅ Yes — goods receipt |
| SC6 | R600a refrigerant first delivery; NESREA documented | Supply Chain / EHS | Q2 2027 | G3 | ✅ Yes — gas zone |
| SC7 | Intra-group Plastics Factory daily run-rate established | Supply Chain | Q3 2027 | G3 | ✅ Yes — production |
| SC8 | SON CoC obtained for all imported components | Regulatory Affairs | Q1 2026 | G2 | ❌ No |

### Workstream 5 — Production Equipment & Commissioning

**Lead:** Engineering & Production Manager
**Objective:** Procure, install, and commission all production equipment across all zones.

| # | Deliverable | Owner | Target | Gate | Machine Required? |
|---|-------------|-------|--------|------|-------------------|
| E1 | SMT line equipment ordered (JUKI, DEK, Heller, Koh Young) | Procurement | Q1 2026 | G2 | ❌ No |
| E2 | Refrigerator line equipment ordered | Procurement | Q1 2026 | G2 | ❌ No |
| E3 | AMR fleet (10 × MiR/Geek+) ordered | Procurement | Q2 2026 | G2 | ❌ No |
| E4 | SMT line installed and producing FAI boards | Engineering | Q3 2026 | G3 | ✅ Yes |
| E5 | Refrigerator assembly line commissioned | Engineering | Q3 2026 | G3 | ✅ Yes |
| E6 | R600a gas charging station certified (NESREA) | Engineering / EHS | Q2 2027 | G3 | ✅ Yes |
| E7 | Microwave oven line commissioned | Engineering | Q4 2026 | G3 | ✅ Yes |
| E8 | Electric cooker line commissioned | Engineering | Q4 2026 | G3 | ✅ Yes |
| E9 | SDA lines (blender, kettle, rice cooker, toaster) live | Engineering | Q3 2027 | G3 | ✅ Yes |
| E10 | AMR fleet fully operational (all routes mapped) | Engineering / Smart Factory | Q4 2026 | G3 | ✅ Yes |
| E11 | Phase 1 OEE target ≥ 72% sustained for 1 month | Production | Q4 2027 | G3 | ✅ Yes |

### Workstream 6 — HR, Training & EHS

**Lead:** HR Director / EHS Manager
**Objective:** Hire and train all Phase 1 direct and indirect workforce; establish EHS management system.

| # | Deliverable | Owner | Target | Gate | Machine Required? |
|---|-------------|-------|--------|------|-------------------|
| H1 | Organisation structure and headcount plan approved | HR Director | Q3 2025 | G1 | ❌ No |
| H2 | Key leadership roles hired (Factory Manager, Production, QA, EHS) | HR Director | Q4 2025 | G1 | ❌ No |
| H3 | Coo-Cah Manufacturing Academy curriculum designed | HR / Training | Q1 2026 | G1 | ❌ No |
| H4 | EHS Management System (ISO 45001) implemented | EHS Manager | Q2 2026 | G2 | ❌ No |
| H5 | R600a first-responder training — all shift supervisors | EHS Manager | Q1 2027 | G3 | ❌ No |
| H6 | Phase 1 production workforce hired (350 direct) | HR Director | Q2 2027 | G3 | ❌ No |
| H7 | Operator training completed on all production lines | HR / Training | Q3 2027 | G3 | ✅ Yes — live machines |

---

## 4. Machine-Free Sprint — Immediate Deliverables

The following items can be completed now, without any physical machines or construction activity. **All are Gate 1 deliverables.**

| # | Deliverable | Document | Owner | Status |
|---|-------------|----------|-------|--------|
| 1 | Implementation plan | `implementation-plan.md` (this document) | Programme Director | ✅ Done |
| 2 | Intragroup supply coordination | `docs/intragroup-supply-coordination.md` | Supply Chain Manager | ✅ Done |
| 3 | Pentest scoping document | `docs/pentest-scoping.md` | InfoSec / Digital Encode | ✅ Done |
| 4 | AI platform status | `docs/ai-platform-status.md` | AI Platform Team | ✅ Done |
| 5 | BIM zone boundaries (design level) | `docs/bim/zone-boundaries.md` | Smart Factory / BIM | ✅ Done — IFC pending |
| 6 | BIM asset anchors (design level) | `docs/bim/asset-anchors.md` | Smart Factory / BIM | ✅ Done — IFC pending |
| 7 | Sensor registry (design phase) | `docs/sensor-map.md` | Smart Factory | ✅ Done — commissioning expands |
| 8 | Gap closure report | `docs/gap-closure-report.md` | Programme Director | ✅ Done |

---

## 5. Critical Path & Dependencies

```
R1 (NIPC application)
  └─► R2 (NESREA EIA submitted)
        └─► R3 (NESREA EIA approved)
              └─► F5 (Civil construction commenced)
                    └─► F6 (Building complete)
                          ├─► E4 (SMT line installed)
                          ├─► E5 (Refrigerator line)
                          └─► S5 (IT/OT network)
                                └─► S6 (MES edge node)
                                      └─► S7 (Opcenter deployed)
                                            └─► S12 (MES data completeness)

F9 (Solar + BESS energised) ─► Energy self-sufficiency KPI tracking
SC3 (Long-lead POs issued) ─► SC5 (First containers received) ─► E4, E5
S10 (Pentest executed) ─► S11 (AI platform production go-live) ─► G3
```

**Longest critical path:** R2 → R3 → F5 → F6 → E5 → E6 (R600a certified) = approximately 24 months from EIA submission to gas charging certification.

---

## 6. Gate Criteria Summary

### Gate 1 — Design Complete (Target: Q4 2025)

| Check | Criterion | Evidence |
|-------|-----------|----------|
| G1-01 | All planning documentation complete | This repo — all docs populated |
| G1-02 | BIM zone boundaries documented (design level) | `docs/bim/zone-boundaries.md` |
| G1-03 | Sensor registry populated (design phase) | `docs/sensor-map.md` |
| G1-04 | Pentest scoping agreed and signed | `docs/pentest-scoping.md` |
| G1-05 | AI platform stub endpoints documented | `docs/ai-platform-status.md` |
| G1-06 | NIPC Pioneer Status application submitted | Submission receipt |
| G1-07 | NESREA EIA submitted | Submission receipt |
| G1-08 | Intra-group supply coordination signed | `docs/intragroup-supply-coordination.md` |
| G1-09 | Key leadership team in place | Org chart + offer letters |
| G1-10 | Gap closure report showing all G1 items closed | `docs/gap-closure-report.md` |

### Gate 2 — Infrastructure Ready (Target: Q3 2026)

| Check | Criterion | Evidence |
|-------|-----------|----------|
| G2-01 | Building structure handed over | Contractor certificate |
| G2-02 | IT/OT network infrastructure live | Network diagram + test report |
| G2-03 | Solar + BESS energised and stable | Commissioning report |
| G2-04 | NESREA EIA approved | NESREA certificate |
| G2-05 | Long-lead components in safety stock | MES/ERP inventory report |
| G2-06 | MES edge node commissioned | Opcenter deployment certificate |

### Gate 3 — Production Ready (Target: Q4 2027)

| Check | Criterion | Evidence |
|-------|-----------|----------|
| G3-01 | All production lines commissioned | OAT (Operational Acceptance Test) per line |
| G3-02 | R600a gas zone NESREA certified | NESREA permit |
| G3-03 | MES data completeness ≥ 95% for 30 days | MES dashboard export |
| G3-04 | Factory OEE ≥ 72% blended for 30 days | MES OEE report |
| G3-05 | ISO 9001 QMS certification | Certificate |
| G3-06 | SON MANCAP samples submitted | SON submission receipt |
| G3-07 | AI platform production go-live | Deployment report |
| G3-08 | Pentest findings remediated | Digital Encode closing report |

---

## 7. Risk Register

| Risk ID | Risk | Likelihood | Impact | Mitigation |
|---------|------|------------|--------|------------|
| RK-01 | NESREA EIA approval delayed beyond Q4 2025 | Medium | High | Appoint specialist EIA consultant; pre-engage NESREA; parallel processing |
| RK-02 | Compressor lead time extends beyond 14 weeks | Medium | High | Issue PO 6 months ahead; dual-source Embraco + Secop |
| RK-03 | R600a gas zone ATEX contractor availability | Medium | Medium | Pre-qualify ATEX contractor by Q2 2025 |
| RK-04 | Forex (NGN/USD) volatility on CapEx | High | High | Forward contracts; advance payment where possible |
| RK-05 | NIPC Pioneer Status approval delayed | Low | Medium | Engage NIPC early; legal counsel for application |
| RK-06 | SMT equipment delivery delays (import) | Low | High | Order SMT line by Q1 2026; confirm delivery with manufacturer |
| RK-07 | R600a refrigerant supply disruption | Low | Medium | 30-day safety stock; approved local distributor (Praxair/Linde) |
| RK-08 | MES integration complexity (OPC-UA + gas module) | Medium | Medium | Run MES pilot with SMT line first; stage integration |

---

*For factory layout and zone details, refer to [docs/floor-plan.md](./docs/floor-plan.md).*
*For supply chain and intragroup links, refer to [docs/supply-chain.md](./docs/supply-chain.md).*
*For gap closure tracking, refer to [docs/gap-closure-report.md](./docs/gap-closure-report.md).*
*For master programme standards, refer to [oumar-code/Coo-Kah-Doks](https://github.com/oumar-code/Coo-Kah-Doks).*
