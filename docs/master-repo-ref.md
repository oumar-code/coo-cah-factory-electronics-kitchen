# Master Repository Reference

This document establishes the formal traceability link between this factory repository and the
**Coo-Cah Technologies Holdings** master orchestrating repository.

---

## Master Repository

| Attribute | Value |
|---|---|
| **Repository** | [oumar-code/Coo-Kah-Doks](https://github.com/oumar-code/Coo-Kah-Doks) |
| **Purpose** | Single source of truth for strategy, architecture, blueprints, and group-wide standards |
| **Template Version Used** | v1.0 |
| **Factory Template Path** | `factories/_template/` |
| **Factory Blueprint Path** | `factories/electronics/kitchen-electronics/` |
| **Group Standards Path** | `docs/` (within master repo) |

---

## Factory Registration

| Attribute | Value |
|---|---|
| **Factory Name** | Coo-Cah Kitchen Electronics Factory |
| **Factory ID** | CCK-EL-KIT |
| **Factory Repository** | `coo-cah-factory-electronics-kitchen` |
| **Registration Reference** | `orchestration/factory-status-registry.md` (in Coo-Kah-Doks) |
| **Vertical** | Electronics |
| **Sub-vertical** | Kitchen & Domestic Appliances |
| **Tier** | Tier 2 — Consumer Electronics Vertical |
| **Phase** | Phase 1 (Planning) |
| **Status** | PLANNED |
| **Location** | Agbara Industrial Estate / Sagamu Interchange, Lagos/Ogun State, Nigeria |
| **Registered** | 2025 |

---

## Group-Wide Standards Applied

This repository follows all group-wide standards as defined in `docs/` within the master repo
[oumar-code/Coo-Kah-Doks](https://github.com/oumar-code/Coo-Kah-Doks). The following standards
are explicitly adopted and applied in this factory repository:

| Standard Area | Master Repo Reference | Applied In This Repo |
|---|---|---|
| ISO 9001:2015 — Quality Management | `docs/standards/iso-9001.md` | [regulatory.md](./regulatory.md) |
| ISO 45001:2018 — Health & Safety | `docs/standards/iso-45001.md` | [regulatory.md](./regulatory.md) |
| ISO 14001:2015 — Environmental (Phase 2) | `docs/standards/iso-14001.md` | [regulatory.md](./regulatory.md) |
| ISO 50001:2018 — Energy (Phase 2) | `docs/standards/iso-50001.md` | [energy-profile.md](./energy-profile.md) |
| Automation Phases Framework | `docs/automation/phases.md` | [automation-roadmap.md](./automation-roadmap.md) |
| Supply Chain Doctrine | `docs/supply-chain/doctrine.md` | [supply-chain.md](./supply-chain.md) |
| Energy Strategy | `docs/energy/strategy.md` | [energy-profile.md](./energy-profile.md) |
| MES Integration Standards | `docs/mes/integration-standards.md` | [mes-integration.md](./mes-integration.md) |
| AI Platform Standards | `docs/ai/platform.md` | [digital-twin.md](./digital-twin.md) |
| Digital Twin Architecture | `docs/digital-twin/architecture.md` | [digital-twin.md](./digital-twin.md) |
| Factory Blueprint Template | `factories/_template/` | All `docs/` files |
| Kitchen Electronics Blueprint | `factories/electronics/kitchen-electronics/` | All `docs/` files |

---

## Compliance Confirmation

This repository confirms adherence to the following group-wide requirements from the master repo:

- ✅ **Document format**: All documents use the standard markdown + Mermaid diagram format as
  defined in `factories/_template/` within Coo-Kah-Doks.
- ✅ **Naming conventions**: File names, SKU codes, zone labels, and machine designations follow
  the group-wide naming standards.
- ✅ **MES integration**: This factory adopts the group MES integration standard; all production
  data, serial numbers, and test records flow to the group MES platform as specified in
  `docs/mes/integration-standards.md`.
- ✅ **Automation phases**: Phase 1, 2, and 3 definitions in this repo are consistent with the
  group-wide automation phases framework.
- ✅ **Energy strategy**: The 700 kWp + 800 kWh BESS design follows the group energy
  independence strategy. Solar self-sufficiency target (≥ 80%) is the group standard.
- ✅ **Supply chain doctrine**: 90-day safety stock for critical imported sub-assemblies (compressors,
  magnetrons, IGBT modules), dual-source policy, and intra-group supplier priority are all per the
  group supply chain doctrine.
- ✅ **Regulatory framework**: SON NIS, IEC 60335, NESREA (R600a), and NIPC Pioneer Status
  obligations are per the group Nigerian regulatory compliance framework.
- ✅ **R600a refrigerant traceability**: Unique requirement for this factory — full gas charging
  traceability per MES Gas Module (see [mes-integration.md](./mes-integration.md)).

---

## Version History

| Version | Date | Description | Author |
|---|---|---|---|
| 1.0 | 2025 | Initial factory repository creation — Phase 1 Planning | Coo-Cah Engineering Team |

---

## Related Repositories

| Repository | Relationship |
|---|---|
| [oumar-code/Coo-Kah-Doks](https://github.com/oumar-code/Coo-Kah-Doks) | Master orchestrating repo — strategy, blueprints, group standards |
| `coo-cah-factory-chemicals-plastics` | Tier 1 intra-group supplier — plastic casings for microwaves, SDA products, refrigerator liners |
| `coo-cah-factory-electronics-power` | Sister factory — inverter and UPS backup power for factory energy resilience |
| `coo-cah-factory-personal-electronics` | Sister factory — potential Phase 2 PCB supply consolidation |
| `coo-cah-factory-chemicals-metallurgical` | Sister factory — potential steel sheet metal sourcing development |
