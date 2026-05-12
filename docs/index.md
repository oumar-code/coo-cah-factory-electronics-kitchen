# Coo-Cah Kitchen Electronics Factory

![Status: PLANNED](https://img.shields.io/badge/Status-PLANNED-yellow)
![Tier: 2 — Consumer Electronics](https://img.shields.io/badge/Tier-2%20Consumer%20Electronics-orange)
![Phase: 1](https://img.shields.io/badge/Phase-1-blue)
![Location: Agbara/Sagamu, Lagos/Ogun State](https://img.shields.io/badge/Location-Agbara%2FSagamu%2C%20Lagos%2FOgun-green)
![Master Repo: Coo-Kah-Doks](https://img.shields.io/badge/Master%20Repo-Coo--Kah--Doks-purple)

> **Tier 2 — Consumer Electronics Vertical** — This factory manufactures household kitchen appliances
> targeting the Nigerian market, with expansion into West Africa and export to the African diaspora.
> See [master-repo-ref.md](./master-repo-ref.md) for traceability back to the
> [Coo-Kah-Doks](https://github.com/oumar-code/Coo-Kah-Doks) master repository.

---

## Factory Overview

| Attribute | Value |
|---|---|
| **Factory Name** | Coo-Cah Kitchen Electronics Factory |
| **Factory ID** | CCK-EL-KIT |
| **Repository** | `coo-cah-factory-electronics-kitchen` |
| **Vertical** | Electronics — Kitchen & Domestic Appliances |
| **Location** | Agbara Industrial Estate, Lagos State / Sagamu, Ogun State, Nigeria |
| **Tier** | Tier 2 — Consumer Electronics Vertical |
| **Phase** | Phase 1 (Planning / Development) |
| **Status** | PLANNED |
| **Facility Area** | ~15,000 m² |
| **Direct Employees** | ~350 (Phase 1) |
| **Indirect Employees** | ~80 (Phase 1) |
| **Estimated Peak Load** | ~500 kW |
| **Solar PV** | 700 kWp — rooftop system |
| **BESS** | 800 kWh LFP (CATL/BYD containerised) |
| **Backup Generator** | 1 × Perkins 500 kVA diesel, 2,000 L tank (~72 h at 40% load) |
| **Quality Standards** | ISO 9001:2015 (Phase 1); ISO 14001 (Phase 2) |
| **Safety Standard** | ISO 45001:2018 |
| **Regulatory** | SON NIS, IEC 60335, NESREA (R600a), NIPC Pioneer Status |

---

## Products — Phase 1 SKUs

| SKU Code | Product | Variants | Phase |
|---|---|---|---|
| **CCK-REF-2D-FF** | 2-Door Frost-Free Refrigerator | 220L / 280L | Phase 1 |
| **CCK-REF-1D-DC** | Single Door Direct Cool Fridge | 90L / 130L / 150L | Phase 1 |
| **CCK-MW-SOLO** | Microwave Oven — Solo | 20L / 25L / 30L | Phase 1 |
| **CCK-MW-GRILL** | Microwave Oven — Grill | 25L / 30L | Phase 1 |
| **CCK-MW-CONV** | Microwave Oven — Convection | 30L | Phase 1 |
| **CCK-EC-2IND** | Electric Cooker — 2-Burner Induction | 2 × 2,000W zones | Phase 1 |
| **CCK-EC-4CONV** | Electric Cooker — 4-Burner Conventional | 4-plate, 6,000W total | Phase 1 |
| **CCK-BL-500 / 1000** | Blender | 500W / 1000W, 1.5L jar | Phase 1 |
| **CCK-KT-1.5 / 1.7** | Electric Kettle | 1.5L / 1.7L, 2,200W | Phase 1 |
| **CCK-RC-1.8 / 3.0** | Rice Cooker | 1.8L / 3.0L | Phase 1 |
| **CCK-TS-2 / 4** | Pop-Up Toaster | 2-slice / 4-slice | Phase 1 |

---

## Production Capacity Targets

| Product Line | Phase 1 (2025–2027) | Phase 2 (2028–2029) | Phase 3 (2030–2031) |
|---|---|---|---|
| Refrigerators (all types) | 80,000 units/year | 150,000 units/year | 250,000 units/year |
| Microwaves (all variants) | 60,000 units/year | 120,000 units/year | 200,000 units/year |
| Electric Cookers | 50,000 units/year | 100,000 units/year | 180,000 units/year |
| Blenders | 100,000 units/year | 200,000 units/year | 350,000 units/year |
| Kettles | 80,000 units/year | 160,000 units/year | 280,000 units/year |
| Rice Cookers | 60,000 units/year | 120,000 units/year | 200,000 units/year |
| Toasters | 70,000 units/year | 130,000 units/year | 220,000 units/year |
| **Total (All SKUs)** | **500,000 units/year** | **980,000 units/year** | **1,680,000 units/year** |

---

## Cross-Factory Dependencies

### This Factory Supplies (Outbound)

| Destination | Product / Service | Notes |
|---|---|---|
| Coo-Cah Distribution Hubs (Lagos, Abuja, PH) | Finished kitchen appliances | National distribution |
| Coo-Cah Export Terminal | Export-ready kitchen appliances | West Africa + diaspora |

### This Factory Receives (Inbound)

| Source | Material / Component | Lead Time | Safety Stock |
|---|---|---|---|
| **Coo-Cah Plastics Factory** (Agbara) | ABS/HIPS/PP plastic casings, microwave housings, refrigerator liners | 1–2 days (intra-group) | 7 days |
| **Coo-Cah Power Electronics Factory** (Sagamu) | Inverter UPS backup for MES servers, gas zone | One-off commissioning | — |
| Embraco / Secop (Brazil/Slovakia) | Refrigerator compressors | 10–14 weeks | 60 days |
| Galanz / LG (China/Korea) | Magnetrons (microwaves) | 8–12 weeks | 45 days |
| Infineon (Germany) | IGBT modules (induction cookers) | 8–10 weeks | 60 days |
| China / Taiwan OEM | SMT components, bare PCBs | 4–8 weeks | 30 days |

---

## Energy Profile Summary

| Parameter | Value |
|---|---|
| Facility Area | ~15,000 m² |
| Estimated Peak Load | ~500 kW |
| Daily Energy Consumption | ~3,500 kWh/day (16h operational) |
| Solar PV | 700 kWp — rooftop monocrystalline PERC |
| BESS | 800 kWh LFP (CATL/BYD containerised) |
| Solar Irradiance | 4.8 PSH/day average (Lagos) |
| Target Solar Self-Sufficiency | ≥ 80% |
| Grid Supply (Agbara/Sagamu DISCO) | ~8–12 h/day |
| Backup Generator | 1 × Perkins 500 kVA diesel; 2,000 L tank (~72 h at 40% load) |

> The 700 kWp + 800 kWh system is designed to make the factory effectively grid-independent
> during all production hours. The foam injection machine (45 kW peak) and HVAC (120 kW) are the
> largest loads; BESS dispatch is managed to absorb foam injection spikes.

See [docs/energy-profile.md](./energy-profile.md) for full demand analysis and cost model.

---

## Key Performance Indicators

| KPI | Phase 1 Target | Measurement Frequency |
|---|---|---|
| Overall Equipment Effectiveness | ≥ 75% | Daily |
| First-Pass Yield | ≥ 97% | Per Batch |
| Defect Rate (DPPM — customer escapes) | < 2,000 ppm | Monthly |
| On-Time Delivery | ≥ 93% | Weekly |
| Energy Intensity — Refrigerators | ≤ 18 kWh/unit | Monthly |
| Energy Intensity — Small Appliances | ≤ 2 kWh/unit | Monthly |
| Solar Self-Sufficiency | ≥ 80% | Monthly |
| MES Data Completeness | ≥ 97% | Daily |
| Warranty Claim Rate (12-month) | < 1% | Quarterly |
| Lost Time Injury Rate | Zero LTI | Continuous |

---

## Phase 1 Milestone Checklist

| # | Milestone | Target Date | Status |
|---|---|---|---|
| M1 | NIPC Pioneer Status application submitted | Q3 2025 | 🔲 Planned |
| M2 | NESREA EIA submitted | Q3 2025 | 🔲 Planned |
| M3 | Factory site acquired / lease signed (Agbara) | Q4 2025 | 🔲 Planned |
| M4 | Civil construction commenced | Q1 2026 | 🔲 Planned |
| M5 | Rooftop solar civil works commenced (700 kWp) | Q1 2026 | 🔲 Planned |
| M6 | SMT line installed and commissioned | Q2 2026 | 🔲 Planned |
| M7 | BESS (800 kWh LFP) energised | Q2 2026 | �� Planned |
| M8 | Refrigerator line commissioned (2-door FF + 1D DC) | Q3 2026 | 🔲 Planned |
| M9 | MES deployed across all production zones | Q4 2026 | 🔲 Planned |
| M10 | AMR fleet (10 units) commissioned | Q4 2026 | 🔲 Planned |
| M11 | R600a gas charging station NESREA-certified | Q2 2027 | 🔲 Planned |
| M12 | ISO 9001:2015 certification audit | Q3 2027 | 🔲 Planned |
| M13 | Small appliance lines (blender, kettle, etc.) live | Q3 2027 | 🔲 Planned |
| M14 | SON NIS type-test samples submitted (refrigerators) | Q4 2027 | 🔲 Planned |
| M15 | Phase 1 OEE target achieved (≥ 72%) | Q4 2027 | 🔲 Planned |

---

## Documentation Index

### Core Factory Documents

| Document | Description |
|---|---|
| [master-repo-ref.md](./master-repo-ref.md) | Master repo traceability, version reference, group standards |
| [machinery.md](./machinery.md) | Full equipment register: SMT line, refrigerator assembly, microwave/cooker, SDA, QC |
| [energy-profile.md](./energy-profile.md) | Power demand analysis, solar design, BESS, energy cost model |
| [floor-plan.md](./floor-plan.md) | 15,000 m² layout: zones, flow paths, R600a gas zone, solar roof |
| [automation-roadmap.md](./automation-roadmap.md) | Phase 1→3 automation strategy: MES, AMR, robotic foam injection, lights-out SDA |
| [supply-chain.md](./supply-chain.md) | Component sourcing: compressors, magnetrons, plastics, packaging |
| [intragroup-supply-coordination.md](./intragroup-supply-coordination.md) | Intragroup supply agreements: Plastics, Personal Electronics, Garage Power |
| [regulatory.md](./regulatory.md) | SON NIS, IEC 60335, NESREA R600a, Pioneer Status |
| [capex-opex.md](./capex-opex.md) | Phased CapEx, unit economics, BOM cost model, payback analysis |
| [digital-twin.md](./digital-twin.md) | Asset registry, foam/reflow/gas DT models, energy monitoring |
| [mes-integration.md](./mes-integration.md) | R600a gas traceability, serial numbers, OEE framework, API reference |

### Gate & Implementation Readiness Documents

| Document | Description |
|---|---|
| [./implementation-plan.md](./implementation-plan.md) | Phase 1 implementation plan: 6 workstreams, gate criteria, risk register |
| [gap-closure-report.md](./gap-closure-report.md) | Gate readiness gap tracker: status of all machine-free and machine-required items |
| [ai-platform-status.md](./ai-platform-status.md) | AI platform: 5 Phase 1 services, stub endpoints, go-live criteria, blockers |
| [pentest-scoping.md](./pentest-scoping.md) | IT/OT penetration test scope, rules of engagement, Digital Encode Limited |
| [sensor-map.md](./sensor-map.md) | Design-phase sensor registry: 143 sensors across all 17 zones |

### BIM & Spatial Data

| Document | Description |
|---|---|
| [bim/zone-boundaries.md](./bim/zone-boundaries.md) | 3D zone boundary coordinates for all 17 production zones (design-level; IFC pending) |
| [bim/asset-anchors.md](./bim/asset-anchors.md) | Asset anchor coordinates for all key equipment and infrastructure (IFC pending) |

---

## Master Repository

This factory repository is part of the **Coo-Cah Technologies Holdings** manufacturing ecosystem.
The master orchestrating repository is [oumar-code/Coo-Kah-Doks](https://github.com/oumar-code/Coo-Kah-Doks).

All group-wide standards (ISO requirements, automation phases, supply chain doctrine, energy strategy,
AI platform, MES integration standards) are defined in the master repo and this repository is fully
traceable back to those standards. See [master-repo-ref.md](./master-repo-ref.md) for details.
