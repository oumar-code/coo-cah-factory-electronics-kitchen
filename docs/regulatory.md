# Kitchen Electronics Factory — Regulatory & Compliance Framework

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Location:** Agbara Industrial Estate, Lagos State | **Phase:** Phase 1
> **Document Version:** 1.0 | **Owner:** Regulatory Affairs & Quality Team

---

## 1. Overview

The Kitchen Electronics Factory is subject to a multi-layer regulatory compliance framework combining Nigerian national standards, international IEC standards, environmental regulations, and factory safety legislation. The most distinctive compliance requirement for this factory — not shared by most Coo-Cah factories — is the **R600a refrigerant handling permit** under NESREA, which classifies isobutane (R600a) as a flammable substance requiring specific facility design, staff training, and usage reporting.

| Regulatory Body | Jurisdiction | Primary Obligation |
|-----------------|-------------|-------------------|
| SON — Standards Organisation of Nigeria | Nigeria-wide | Product certification (NIS standards) before sale |
| IEC — International Electrotechnical Commission | International | Product safety (IEC 60335 series) — adopted by SON |
| NESREA — Nat. Env. Standards & Reg. Enforcement Agency | Nigeria-wide | Environmental impact, R600a flammable gas permit |
| NIPC — Nigerian Investment Promotion Commission | Nigeria-wide | Pioneer Status (CIT exemption) |
| NAFDAC — National Agency for Food, Drug Admin & Control | Nigeria-wide | Food-contact materials (SDA appliances) |
| Federal Inland Revenue Service (FIRS) | Nigeria-wide | VAT, CIT, TET obligations |
| Lagos State Environmental Protection Agency (LASEPA) | Lagos State | Factory emissions, waste management |
| Ogun State EPA | Ogun State | Applicable if Sagamu site used |
| Nigeria Customs Service (NCS) | Nigeria-wide | Import duties, Form M, PAAR |

---

## 2. Product Certification — SON NIS Standards

All products manufactured and sold in Nigeria are required to carry the **SON MANCAP** (Mandatory Conformity Assessment Programme) product certification mark.

### 2.1 SON NIS Certification by Product

| Product | Applicable NIS Standard | IEC Reference | Key Test Requirements | Phase |
|---------|------------------------|---------------|----------------------|-------|
| Refrigerators (all) | NIS 2011 (IEC 62552) | IEC 62552:2015 | Energy consumption, temperature performance, safety | Phase 1 |
| Refrigerators — safety | NIS 1053 (IEC 60335-2-24) | IEC 60335-2-24:2020 | Electrical safety, earth bond, hipot, stability | Phase 1 |
| Microwave Ovens | NIS 2004 (IEC 60335-2-25) | IEC 60335-2-25:2020 | RF leakage < 5mW/cm², electrical safety, interlock test | Phase 1 |
| Electric Cookers | NIS 2010 (IEC 60335-2-6) | IEC 60335-2-6:2020 | Heating element safety, earth bond, temp test | Phase 1 |
| Induction Hobs | NIS 2010 (IEC 60335-2-6) | IEC 60335-2-6 Part 2 | EMC pre-compliance, coil efficiency, surface temp | Phase 1 |
| Blenders | NIS 2009 (IEC 60335-2-14) | IEC 60335-2-14:2020 | Motor safety, blade containment, hipot | Phase 1 |
| Kettles | NIS 2005 (IEC 60335-2-15) | IEC 60335-2-15:2020 | Auto-shutoff at 100°C, limescale test, safety | Phase 1 |
| Rice Cookers | NIS 2012 (IEC 60335-2-15) | IEC 60335-2-15:2020 | Thermal protection, thermostat accuracy, hipot | Phase 1 |
| Toasters | NIS (IEC 60335-2-9) | IEC 60335-2-9:2020 | Heating element, crumb tray, thermal cutout | Phase 1 |

### 2.2 SON Certification Process

| Stage | Activity | Lead Time | Responsible |
|-------|----------|-----------|-------------|
| 1 | Application to SON (product registration) | Week 1 | Regulatory Affairs |
| 2 | Sample submission (5 units per SKU) | Weeks 2–3 | Production + QA |
| 3 | Testing at SON laboratory or SON-accredited lab | 6–12 weeks | SON / Third-party lab |
| 4 | Factory inspection (SON auditors) | Arranged with SON | Factory Manager |
| 5 | MANCAP certificate issued | ~16–20 weeks total | SON |
| 6 | Annual renewal + surveillance testing | Annually | Regulatory Affairs |

### 2.3 SON Energy Rating

All refrigerators must carry the **SON Energy Star** energy efficiency label (per NIS 2011). Energy testing per IEC 62552 is conducted on our in-factory energy efficiency test bench (Yokogawa WT333). Results are submitted to SON as part of the MANCAP application.

---

## 3. IEC 60335 Compliance (Household Appliance Safety)

IEC 60335 Part 1 (General Requirements) applies to ALL electrical appliances in the factory product range. Part 2 variants apply to specific product types.

| Test | IEC Clause | Requirement | Equipment Used |
|------|------------|-------------|----------------|
| Dielectric strength (hipot) | Cl. 16 | 1,250 V AC for 1 min; no breakdown | Chroma 19053 |
| Earth bond continuity | Cl. 27 | ≤ 0.1 Ω bond; 25 A for 1 min | Chroma 19053 |
| Insulation resistance | Cl. 16.3 | ≥ 2 MΩ at 500 V DC | Chroma 19036 |
| Temperature test | Cl. 11 | Surface temps within IEC table limits | Thermocouple logger |
| Leakage current (functional) | Cl. 13 | ≤ 0.25 mA (accessible) | Clamp meter |
| Stability test | Cl. 20 | No tipping on 10° tilt | Test jig |
| Microwave leakage | IEC 60335-2-25 Cl. 32 | ≤ 5 mW/cm² at 5 cm | Narda SMR-3 |

All test results are linked to individual unit serial numbers via the MES and archived for ≥ 7 years for product liability purposes.

---

## 4. NESREA Environmental Compliance

### 4.1 Environmental Impact Assessment (EIA)

An EIA is required under NESREA guidelines before factory construction commences. Scope includes assessment of:

- R600a (isobutane) flammable gas handling and atmospheric release risk
- PU foam chemical (polyol + MDI isocyanate) vapour emissions
- Noise emissions from factory operations
- Solid waste (EPS foam offcuts, scrap steel, packaging waste)
- Refrigerant recovery and recycling plan

**Status:** EIA application planned for Q3 2025. Consultant appointed; scoping completed.

### 4.2 R600a Refrigerant Handling

R600a (isobutane, UN1969) is classified as a flammable gas (LEL: 1.8% v/v in air). NESREA and NFPA 58 standards apply to storage and handling.

| Requirement | Detail | Compliance Method |
|-------------|--------|-------------------|
| Storage quantity limits | Max 50 kg in production zone; bulk store in separate building | Compliant by design (see [floor-plan.md](./floor-plan.md)) |
| Ventilation in gas zone | ≥ 15 air changes/hour; negative pressure | Dedicated HVAC with ATEX fans |
| Fixed gas detection | Continuous monitoring; alarm at 10% LEL; shutdown at 25% LEL | Draeger Polytron 8000 array |
| Charging station grounding | Anti-static charging workstation; conductive floor | Conductive ESD tile flooring throughout Z5 |
| Cylinder storage | Upright; chained; labelled; 30°C max | Dedicated cylinder store — separate from production |
| Staff training | NEBOSH + R600a handling certification for all gas zone staff | Refreshed annually |
| Monthly usage reporting | NESREA gas usage declaration | MES Gas Module auto-report |
| Emergency response plan | Published R600a MSDS + emergency evacuation procedure | Posted in Z5 and Z14 |

### 4.3 PU Foam Chemical Compliance

| Chemical | Classification | Controls |
|----------|---------------|---------|
| MDI Isocyanate (foam component) | IARC Group 3; respiratory sensitiser | LEV (Local Exhaust Ventilation) at foam injection station; RPE (P100 + OV mask) for maintenance |
| Polyol blend | Low toxicity | Store per SDS; secondary containment |
| Blowing agent (cyclopentane) | Flammable; GWP < 5 | ATEX controls on foam machine; no open flames within 3m |

---

## 5. NIPC Pioneer Status

**Pioneer Status** under the Nigerian Investment Promotion Commission grants a **5-year Company Income Tax (CIT) holiday** on profits from eligible pioneer activities. Kitchen electronics manufacturing (including refrigerators, microwaves, and small domestic appliances) qualifies under the list of pioneer industries.

| Detail | Value |
|--------|-------|
| Scheme | NIPC Pioneer Status |
| Tax Benefit | 30% CIT exemption for 5 years; extendable by 2+2 years |
| Eligible Activities | Refrigerator, microwave, electric cooker, SDA manufacturing |
| Application Timing | Pre-production (must apply before first sale) |
| Benefit Period Start | From first date of production / first sale |
| Application Timeline | 6–9 months from submission to certificate |

### 5.1 Pioneer Status Application Checklist

| Item | Status |
|------|--------|
| Certificate of Incorporation (CAC) | Planned |
| Evidence of Investment (CapEx plan, bank statements) | Planned |
| NIPC application form + pioneer activity description | Planned |
| Environmental Certificate (NESREA/LASEPA) | Planned |
| Tax clearance certificate (FIRS) | Planned |
| SON product certification application | Planned |
| Application submission to NIPC | Q3 2025 |

---

## 6. NAFDAC Compliance (Food-Contact Appliances)

Blenders, kettles, and rice cookers have parts in contact with food or drinking water. NAFDAC requires material safety compliance:

| Requirement | Applicable Products | Details |
|-------------|---------------------|---------|
| Material safety datasheet (MSDS) | Blender jar (PC/Tritan), kettle body, rice cooker pot | Supplier-provided MSDS + food-contact declaration |
| BPA-free certification | Blender jar, rice cooker pot inner | Supplier material certificate |
| Stainless steel grade (kettles) | 304 or 316 SS for heating element and body | Supplier mill certificate |
| NAFDAC notification | All food-contact appliances | Notification (not registration) — per product category |

---

## 7. Factory Safety & Labour Compliance

| Standard / Regulation | Detail | Implementation |
|-----------------------|--------|----------------|
| ISO 45001:2018 | OHS Management System | QMS + OHSMS implemented from factory commissioning |
| Nigeria Factories Act | Requirement for factory registration with FMITI | Factory registration before start of production |
| NSITF (Employee Compensation) | Mandatory employer contribution — 1% of payroll | Payroll integration from Day 1 |
| ITF (Industrial Training Fund) | 1% levy on companies with 5+ employees | Annual contribution |
| Minimum Wage Compliance | National minimum wage (₦70,000/month as of 2024) | All staff paid above minimum |
| Fire Safety Certificate | Lagos State Fire Service (or Ogun State equivalent) | Factory inspection + annual certification |
| R600a First Responder Training | All production shift supervisors | Trained by certified NEBOSH instructor |

---

## 8. Compliance Calendar

| Month | Activity |
|-------|----------|
| January | Annual SON surveillance inspection; ISO 9001 internal audit |
| February | NESREA R600a annual declaration; environmental monitoring report |
| March | NIPC Pioneer Status annual progress report |
| April | Quarterly safety audit (ISO 45001) |
| July | Half-year OEE and quality performance review |
| September | SON energy rating retest (selected SKUs) |
| November | Annual NAFDAC food-contact material review |
| December | Annual LASEPA/Ogun EPA compliance submission; year-end audit |

---

*For supply chain and customs compliance, refer to [supply-chain.md](./supply-chain.md).*
*For MES traceability supporting compliance, refer to [mes-integration.md](./mes-integration.md).*
