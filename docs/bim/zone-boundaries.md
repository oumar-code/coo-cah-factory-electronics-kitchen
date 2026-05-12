# Kitchen Electronics Factory — BIM Zone Boundaries

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Factory ID:** CCK-EL-KIT
> **Document Version:** 1.0 | **Owner:** Smart Factory Core Team / Facilities & Engineering
> **Status:** DESIGN-LEVEL — IFC model delivery pending from architect

---

## 1. Overview

This document records the three-dimensional zone boundaries for all 17 production zones in the Kitchen Electronics Factory. Boundaries are used by the Digital Twin spatial model, the MES asset location system, and the AMR fleet navigation system.

**Coordinate system:**

| Axis | Direction | Reference point |
|------|-----------|-----------------|
| X | East (positive) | SW corner of factory building = X:0 |
| Y | North (positive) | SW corner of factory building = Y:0 |
| Z | Up (positive) | Finished floor level = Z:0 |
| Units | Metres | All coordinates in metres |

> **Important:** Coordinates in this document are **design-level estimates** derived from architectural drawings and zone area data in [floor-plan.md](../floor-plan.md). They will be updated with **IFC-model-exact coordinates** upon delivery of the IFC file from the appointed architect.
>
> Fields marked **[IFC-PENDING]** require update after IFC delivery.

---

## 2. Factory Building Envelope

| Parameter | Value | Status |
|-----------|-------|--------|
| Building origin (SW corner) | (0.0, 0.0, 0.0) | Design |
| Building footprint (E–W) | 120.0 m | Design |
| Building footprint (N–S) | 125.0 m | Design |
| Total floor area | ~15,000 m² | Design |
| Eave height (production bays) | 9.0 m | Design |
| Eave height (office / service areas) | 3.0–5.0 m | Design |
| IFC model file | `CCK-EL-KIT-FACTORY-v1.ifc` | **[IFC-PENDING]** |
| IFC GUID (building element) | `[IFC-PENDING]` | **[IFC-PENDING]** |

---

## 3. Zone Boundary Register

### Z1 — Raw Material & Component Store

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z1 | Fixed |
| Zone Name | Raw Material & Component Store | Fixed |
| Floor area | ~1,500 m² | Design |
| Zone height | 9.0 m | Design |
| X min | 0.0 m | Design |
| X max | 50.0 m | Design |
| Y min | 95.0 m | Design |
| Y max | 125.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 9.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Racking; incoming QC bay; ESD-controlled sub-zone; 3 loading docks |
| AMR zone designation | Yes — inbound dock zone |
| ESD classification | Sub-zone ESD controlled (Z1-ESD: X:40–50, Y:95–110) |

---

### Z2 — SMT PCB Production

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z2 | Fixed |
| Zone Name | SMT PCB Production | Fixed |
| Floor area | ~1,200 m² | Design |
| Zone height | 6.0 m | Design |
| X min | 50.0 m | Design |
| X max | 90.0 m | Design |
| Y min | 97.0 m | Design |
| Y max | 125.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 6.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | ESD conductive flooring throughout; positive pressure HVAC; 22–24°C; 40–60% RH |
| AMR zone designation | Yes — SMT component replenishment |
| ESD classification | Full ESD zone — conductive tiles; ioniser bars |
| HVAC zone | Dedicated precision HVAC unit (Daikin) |

---

### Z3 — Refrigerator Sheet Metal Fabrication

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z3 | Fixed |
| Zone Name | Refrigerator Sheet Metal Fabrication | Fixed |
| Floor area | ~1,000 m² | Design |
| Zone height | 9.0 m | Design |
| X min | 90.0 m | Design |
| X max | 120.0 m | Design |
| Y min | 95.0 m | Design |
| Y max | 125.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 9.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Roll-form lines; press brake; overhead crane (5T) |
| AMR zone designation | No — forklift access only |
| Overhead crane envelope | X:90–120, Y:95–125, Z:0–8.5 |

---

### Z4 — Refrigerator Assembly (Main)

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z4 | Fixed |
| Zone Name | Refrigerator Assembly — Main | Fixed |
| Floor area | ~2,200 m² | Design |
| Zone height | 9.0 m | Design |
| X min | 0.0 m | Design |
| X max | 100.0 m | Design |
| Y min | 73.0 m | Design |
| Y max | 95.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 9.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Overhead Power & Free chain conveyor (60m loop); 12 stop-stations; PU foam injection station |
| AMR zone designation | Yes — component kitting inbound; passes through Z4 east aisle |
| Overhead conveyor envelope | X:5–95, Y:75–93, Z:2.5–3.5 (conveyor rail height) |
| Phase 2 robot cell provision | X:20–50, Y:78–90 (pre-allocated floor space) |

---

### Z5 — R600a Gas Charging Zone

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z5 | Fixed |
| Zone Name | R600a Gas Charging Zone | Fixed |
| Floor area | ~600 m² | Design |
| Zone height | 6.0 m | Design |
| X min | 0.0 m | Design |
| X max | 30.0 m | Design |
| Y min | 50.0 m | Design |
| Y max | 70.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 6.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | ATEX Zone 2 (below 0.5 m AFF); negative-pressure ventilation; 12 gas detectors; sealed floor |
| AMR zone designation | No — AMR excluded from gas zone |
| ATEX classification | Zone 2 (< 0.5 m AFF) — ATEX-certified all equipment |
| Ventilation | Forced negative pressure; min 15 air changes/hour; ATEX fans |
| Access control | Interlocked door; ESD verification pad at entry |
| Buffer zone | 1.5 m exclusion corridor on all four sides — no ignition sources |

---

### Z6 — Microwave Oven Assembly

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z6 | Fixed |
| Zone Name | Microwave Oven Assembly | Fixed |
| Floor area | ~800 m² | Design |
| Zone height | 6.0 m | Design |
| X min | 50.0 m | Design |
| X max | 86.0 m | Design |
| Y min | 50.0 m | Design |
| Y max | 72.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 6.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Cavity press; spot weld station; hi-pot and RF leakage test bays |
| AMR zone designation | Yes — SDA/MW component kitting |
| RF shielding | Hi-pot test bay screened (Faraday enclosure) |

---

### Z7 — Electric Cooker Assembly

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z7 | Fixed |
| Zone Name | Electric Cooker Assembly | Fixed |
| Floor area | ~700 m² | Design |
| Zone height | 6.0 m | Design |
| X min | 86.0 m | Design |
| X max | 117.0 m | Design |
| Y min | 50.0 m | Design |
| Y max | 72.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 6.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Induction coil winding station; glass surface bonding; cooker safety test rig |
| AMR zone designation | Yes — component kitting |

---

### Z8 — SDA Assembly Lines (A, B, C)

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z8 | Fixed |
| Zone Name | SDA Assembly Lines A, B, C | Fixed |
| Floor area | ~1,800 m² | Design |
| Zone height | 6.0 m | Design |
| X min | 0.0 m | Design |
| X max | 82.0 m | Design |
| Y min | 36.0 m | Design |
| Y max | 58.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 6.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | 3 parallel production lines; blenders (Line A), kettles/toasters (Line B), rice cookers (Line C) |
| AMR zone designation | Yes — SDA component kitting; WIP to Z9 |
| Phase 3 provision | Lights-out conveyor conversion space reserved (Line A east section) |

---

### Z9 — In-Process QC (IPQC)

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z9 | Fixed |
| Zone Name | In-Process QC (IPQC) | Fixed |
| Floor area | ~600 m² | Design |
| Zone height | 5.0 m | Design |
| X min | 0.0 m | Design |
| X max | 33.0 m | Design |
| Y min | 18.0 m | Design |
| Y max | 36.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 5.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Noise test booths (fridges); safety/hi-pot test; visual inspection; refrigerator performance test rack |
| AMR zone designation | Yes — WIP pass-through to Z11 |

---

### Z10 — Final QC + Outbound Quality Audit (OBA)

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z10 | Fixed |
| Zone Name | Final QC + OBA | Fixed |
| Floor area | ~700 m² | Design |
| Zone height | 5.0 m | Design |
| X min | 33.0 m | Design |
| X max | 73.0 m | Design |
| Y min | 18.0 m | Design |
| Y max | 36.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 5.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | OBA sampling station; energy efficiency test bench (Yokogawa WT333); warranty label printer |
| AMR zone designation | Yes |

---

### Z11 — Packaging & Labelling

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z11 | Fixed |
| Zone Name | Packaging & Labelling | Fixed |
| Floor area | ~900 m² | Design |
| Zone height | 6.0 m | Design |
| X min | 73.0 m | Design |
| X max | 120.0 m | Design |
| Y min | 18.0 m | Design |
| Y max | 39.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 6.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Automatic carton erector (large + small); carton sealer; inline label printer/applicator; checkweigher |
| AMR zone designation | Yes — FG pallet build; dispatch to Z12 |

---

### Z12 — Finished Goods Warehouse (FGW)

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z12 | Fixed |
| Zone Name | Finished Goods Warehouse | Fixed |
| Floor area | ~2,200 m² | Design |
| Zone height | 9.0 m | Design |
| X min | 0.0 m | Design |
| X max | 120.0 m | Design |
| Y min | 0.0 m | Design |
| Y max | 18.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 9.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Selective pallet racking; 4 dispatch bays; ESFR sprinkler system; 4 loading dock doors |
| AMR zone designation | Yes — FG putaway; dispatch staging |
| Racking height | Up to 7.5 m (3 levels); forklift required above level 2 |

---

### Z13 — Maintenance Workshop

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z13 | Fixed |
| Zone Name | Maintenance Workshop | Fixed |
| Floor area | ~400 m² | Design |
| Zone height | 5.0 m | Design |
| X min | 100.0 m | Design |
| X max | 120.0 m | Design |
| Y min | 73.0 m | Design |
| Y max | 93.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 5.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Tool room; spare parts store; welding bay (local exhaust ventilation) |
| AMR zone designation | No |

---

### Z14 — Compressor & Test Services

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z14 | Fixed |
| Zone Name | Compressor & Test Services | Fixed |
| Floor area | ~400 m² | Design |
| Zone height | 5.0 m | Design |
| X min | 30.0 m | Design |
| X max | 50.0 m | Design |
| Y min | 50.0 m | Design |
| Y max | 70.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 5.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Refrigerant recovery unit; nitrogen leak test; compressor performance test rig |
| AMR zone designation | No |

---

### Z15 — EHS & First Aid

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z15 | Fixed |
| Zone Name | EHS & First Aid | Fixed |
| Floor area | ~200 m² | Design |
| Zone height | 3.0 m | Design |
| X min | 100.0 m | Design |
| X max | 120.0 m | Design |
| Y min | 93.0 m | Design |
| Y max | 103.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 3.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | First aid room; eyewash station; EHS officer office; SDS binder |
| AMR zone designation | No |

---

### Z16 — IT / MES Server Room

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z16 | Fixed |
| Zone Name | IT / MES Server Room | Fixed |
| Floor area | ~100 m² | Design |
| Zone height | 3.0 m | Design |
| X min | 100.0 m | Design |
| X max | 110.0 m | Design |
| Y min | 103.0 m | Design |
| Y max | 113.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 3.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | MES edge node servers; InfluxDB server; network core switches; MQTT broker node; FM-200 suppression |
| AMR zone designation | No |
| Access control | Card access only — IT Manager + Smart Factory Core Team |
| Cooling | Dedicated precision air conditioning (Stulz/APC CRAC unit) |
| Fire suppression | FM-200 clean agent (server-safe) |

---

### Z17 — Staff Facilities

| Attribute | Value | Status |
|-----------|-------|--------|
| Zone Code | Z17 | Fixed |
| Zone Name | Staff Facilities | Fixed |
| Floor area | ~400 m² | Design |
| Zone height | 3.0 m | Design |
| X min | 82.0 m | Design |
| X max | 102.0 m | Design |
| Y min | 36.0 m | Design |
| Y max | 56.0 m | Design |
| Z min | 0.0 m | Design |
| Z max | 3.0 m | Design |
| IFC Zone GUID | `[IFC-PENDING]` | **[IFC-PENDING]** |
| Key features | Canteen; locker rooms; prayer room; welfare notice board |
| AMR zone designation | No |

---

## 4. Zone Summary Table

| Zone | Name | Area (m²) | Height (m) | X range (m) | Y range (m) | IFC Status |
|------|------|-----------|-----------|-------------|-------------|-----------|
| Z1 | Raw Material & Component Store | 1,500 | 9.0 | 0–50 | 95–125 | [IFC-PENDING] |
| Z2 | SMT PCB Production | 1,200 | 6.0 | 50–90 | 97–125 | [IFC-PENDING] |
| Z3 | Sheet Metal Fabrication | 1,000 | 9.0 | 90–120 | 95–125 | [IFC-PENDING] |
| Z4 | Refrigerator Assembly — Main | 2,200 | 9.0 | 0–100 | 73–95 | [IFC-PENDING] |
| Z5 | R600a Gas Charging Zone | 600 | 6.0 | 0–30 | 50–70 | [IFC-PENDING] |
| Z6 | Microwave Oven Assembly | 800 | 6.0 | 50–86 | 50–72 | [IFC-PENDING] |
| Z7 | Electric Cooker Assembly | 700 | 6.0 | 86–117 | 50–72 | [IFC-PENDING] |
| Z8 | SDA Assembly Lines A, B, C | 1,800 | 6.0 | 0–82 | 36–58 | [IFC-PENDING] |
| Z9 | In-Process QC (IPQC) | 600 | 5.0 | 0–33 | 18–36 | [IFC-PENDING] |
| Z10 | Final QC + OBA | 700 | 5.0 | 33–73 | 18–36 | [IFC-PENDING] |
| Z11 | Packaging & Labelling | 900 | 6.0 | 73–120 | 18–39 | [IFC-PENDING] |
| Z12 | Finished Goods Warehouse | 2,200 | 9.0 | 0–120 | 0–18 | [IFC-PENDING] |
| Z13 | Maintenance Workshop | 400 | 5.0 | 100–120 | 73–93 | [IFC-PENDING] |
| Z14 | Compressor & Test Services | 400 | 5.0 | 30–50 | 50–70 | [IFC-PENDING] |
| Z15 | EHS & First Aid | 200 | 3.0 | 100–120 | 93–103 | [IFC-PENDING] |
| Z16 | IT / MES Server Room | 100 | 3.0 | 100–110 | 103–113 | [IFC-PENDING] |
| Z17 | Staff Facilities | 400 | 3.0 | 82–102 | 36–56 | [IFC-PENDING] |

---

## 5. IFC Delivery & Update Procedure

Upon receipt of the IFC model file (`CCK-EL-KIT-FACTORY-v1.ifc`) from the appointed architect:

1. Smart Factory Core Team extracts IFC Zone GUIDs for each of the 17 zones.
2. Each `[IFC-PENDING]` field in this document is updated with the exact IFC GUID and precise coordinates (to 3 decimal places).
3. Zone boundaries are imported into the Digital Twin spatial model (Unity/UE5 layer).
4. AMR navigation system updated with precise zone boundary polygons.
5. Document version incremented to 1.1 and committed to this repository.

**IFC Delivery Owner:** Facilities & Engineering Manager
**Expected:** Q3–Q4 2025 (with architect contract)

---

*For zone descriptions and features, refer to [docs/floor-plan.md](../floor-plan.md).*
*For asset locations within zones, refer to [docs/bim/asset-anchors.md](./asset-anchors.md).*
*For sensor placements within zones, refer to [docs/sensor-map.md](../sensor-map.md).*
