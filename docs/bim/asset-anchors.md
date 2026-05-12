# Kitchen Electronics Factory — BIM Asset Anchors

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Factory ID:** CCK-EL-KIT
> **Document Version:** 1.0 | **Owner:** Smart Factory Core Team / Facilities & Engineering
> **Status:** DESIGN-LEVEL — IFC GUID population pending architect IFC delivery

---

## 1. Overview

This document records the three-dimensional anchor coordinates (centroid points) for all significant production assets, infrastructure, and sensor mounting locations in the Kitchen Electronics Factory. Anchors are used by:

- **Digital Twin:** Maps physical assets to their virtual counterparts in the 3D model
- **MES CMMS:** Links maintenance tasks and asset records to physical locations
- **AMR Navigation:** Defines pick/drop points and zone-entry coordinates for the AMR fleet
- **Sensor registry:** Provides location context for all IoT sensor readings

**Coordinate system:** Origin at SW corner of factory building; X = East; Y = North; Z = height above finished floor level (all in metres). See [zone-boundaries.md](./zone-boundaries.md) for zone envelopes.

> **Note:** All anchor coordinates are **design-level estimates**. Fields marked **[IFC-PENDING]** will be updated with surveyed coordinates after IFC model delivery from the architect.

---

## 2. SMT PCB Line Assets — Zone Z2

| Asset ID | Asset Name | DT ID | Qty | Anchor (X, Y, Z) | Orientation | IFC GUID | IFC Status |
|----------|-----------|-------|-----|------------------|-------------|----------|-----------|
| CCK-Z2-001 | Solder Paste Screen Printer (DEK Horizon 02i) | DT-SMT-01 | 1 | (52.0, 112.0, 0.8) | Facing South | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-002 | P&P Machine — High Speed (JUKI FX-3R) | DT-SMT-02 | 1 | (58.0, 112.0, 1.2) | Facing South | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-003 | P&P Machine — Flexible (JUKI RX-7) | DT-SMT-03 | 1 | (64.0, 112.0, 1.2) | Facing South | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-004 | Reflow Oven (Heller 1964 MK5) | DT-SMT-04 | 1 | (71.0, 112.0, 1.5) | Facing South | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-005 | 3D AOI System (Koh Young Zenith) | DT-SMT-05 | 1 | (79.0, 112.0, 1.0) | Facing South | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-006 | SPI System (Koh Young KY8030-3) | DT-SMT-06 | 1 | (54.5, 112.0, 0.9) | Facing South | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-007 | Wave Soldering Machine (Seho PowerSelective) | — | 1 | (84.0, 112.0, 1.2) | Facing South | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-008 | ICT System (Keysight I1000D) | — | 1 | (87.0, 108.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-009 | Flying Probe Tester | — | 1 | (87.0, 104.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-010 | ESD Belt Conveyor (inline, full line) | — | 1 | (68.5, 112.0, 0.9) | Longitudinal E–W | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-011 | Vertical Lift Module — SMT Components (×2) | — | 2 | (52.0, 120.0, 1.0) | Facing South | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z2-012 | Rework Station (×2) | — | 2 | (87.0, 100.0, 0.9) | Facing West | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 3. Refrigerator Assembly Assets — Zones Z3 & Z4

| Asset ID | Asset Name | DT ID | Qty | Anchor (X, Y, Z) | Orientation | IFC GUID | IFC Status |
|----------|-----------|-------|-----|------------------|-------------|----------|-----------|
| CCK-Z3-001 | Roll-Form Line | — | 1 | (95.0, 112.0, 0.9) | Longitudinal N–S | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z3-002 | Press Brake | — | 1 | (108.0, 108.0, 1.2) | Facing West | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z3-003 | Overhead Crane (5T) — Z3 | — | 1 | (105.0, 110.0, 8.0) | Travelling E–W | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-001 | PU Foam Injection Machine (Hennecke TOPLINE) | DT-REF-01 | 1 | (25.0, 84.0, 1.5) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-002 | Foam Curing Conveyor / Holding Racks | — | 1 | (40.0, 84.0, 1.0) | Longitudinal E–W | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-003 | Overhead Chain Conveyor — Full Loop | DT-REF-02 | 1 | (50.0, 84.0, 3.0) | Loop centroid | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-004 | Compressor Pressing & Mounting Station (×1) | — | 1 | (10.0, 82.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-005 | Condenser Coil Assembly Station (×2) | — | 2 | (15.0, 80.0, 0.9) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-006 | Evaporator Assembly Station (×2) | — | 2 | (20.0, 80.0, 0.9) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-007 | Refrigerant Circuit Brazing Station | — | 1 | (30.0, 78.0, 1.0) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-008 | PCB Control Board Installation Station (×2) | — | 2 | (70.0, 80.0, 0.9) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-009 | Door Assembly Station (×4) | — | 4 | (80.0, 82.0, 0.9) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-010 | Performance Test Station (×3) | DT-REF-05 | 3 | (92.0, 78.0, 1.0) | Facing West | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-011 | Energy Efficiency Test Bench (Yokogawa WT333) (×2) | — | 2 | (92.0, 75.0, 1.0) | Facing West | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z4-012 | Safety Test — Hipot & Earth Bond (×2) | — | 2 | (95.0, 80.0, 1.0) | Facing West | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 4. R600a Gas Charging Zone Assets — Zone Z5

| Asset ID | Asset Name | DT ID | Qty | Anchor (X, Y, Z) | Orientation | IFC GUID | IFC Status |
|----------|-----------|-------|-----|------------------|-------------|----------|-----------|
| CCK-Z5-001 | Gas Charging Station (INFICON / Robinair) #1 | DT-REF-03 | 1 | (10.0, 60.0, 1.0) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z5-002 | Gas Charging Station #2 | DT-REF-03 | 1 | (10.0, 55.0, 1.0) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z5-003 | Vacuum Pump Station #1 (REFCO R-32) | DT-REF-04 | 1 | (20.0, 60.0, 0.5) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z5-004 | Vacuum Pump Station #2 | DT-REF-04 | 1 | (20.0, 55.0, 0.5) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z5-005 | R600a Cylinder Storage Rack | — | 1 | (5.0, 68.0, 0.5) | N wall | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z5-006 | Gas Refrigerant Recovery Unit (Refco Cora-L) | — | 1 | (25.0, 62.0, 0.8) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z5-007 | Emergency Shower / Eyewash | — | 1 | (28.0, 68.0, 0.0) | Fixed | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z5-008 | Manual ESD Button (Big Red) | — | 1 | (2.0, 50.5, 1.2) | W wall | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 5. Microwave Assembly Assets — Zone Z6

| Asset ID | Asset Name | DT ID | Qty | Anchor (X, Y, Z) | Orientation | IFC GUID | IFC Status |
|----------|-----------|-------|-----|------------------|-------------|----------|-----------|
| CCK-Z6-001 | Magnetron Assembly & Test Station (×2) | — | 2 | (56.0, 62.0, 0.9) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z6-002 | Door Assembly & Interlock Test Station (×2) | — | 2 | (66.0, 62.0, 0.9) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z6-003 | Microwave Leak Test Station (Narda SMR-3) (×2) | — | 2 | (76.0, 62.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z6-004 | Functional Test Station (×3) | — | 3 | (82.0, 58.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z6-005 | Hipot & Safety Test Station (×2) | — | 2 | (82.0, 54.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 6. Electric Cooker Assembly Assets — Zone Z7

| Asset ID | Asset Name | DT ID | Qty | Anchor (X, Y, Z) | Orientation | IFC GUID | IFC Status |
|----------|-----------|-------|-----|------------------|-------------|----------|-----------|
| CCK-Z7-001 | Induction Coil Assembly Station (×2) | — | 2 | (92.0, 62.0, 0.9) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z7-002 | Tempered Glass Hob Fitting (×2) | — | 2 | (99.0, 62.0, 0.9) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z7-003 | Cooker Safety & Function Test (×3) | — | 3 | (108.0, 58.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z7-004 | Induction Power & Efficiency Test (Fluke 1760) (×2) | — | 2 | (108.0, 54.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 7. SDA Assembly Line Assets — Zone Z8

| Asset ID | Asset Name | DT ID | Qty | Anchor (X, Y, Z) | Orientation | IFC GUID | IFC Status |
|----------|-----------|-------|-----|------------------|-------------|----------|-----------|
| CCK-Z8-001 | SDA Line A — Blender Assembly Conveyor | — | 1 | (20.0, 47.0, 0.9) | Longitudinal E–W | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z8-002 | SDA Line B — Kettle/Toaster Assembly Conveyor | — | 1 | (20.0, 43.0, 0.9) | Longitudinal E–W | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z8-003 | SDA Line C — Rice Cooker Assembly Conveyor | — | 1 | (20.0, 39.0, 0.9) | Longitudinal E–W | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z8-004 | Blender Function Test Rigs (×4) | — | 4 | (65.0, 47.0, 0.9) | Facing West | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z8-005 | Kettle Auto-Boil Test Rigs (×4) | — | 4 | (65.0, 43.0, 0.9) | Facing West | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z8-006 | SDA Safety & Hipot Test (Chroma 19053) (×4) | — | 4 | (75.0, 44.0, 1.0) | Facing West | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 8. QC & Packaging Assets — Zones Z9, Z10, Z11

| Asset ID | Asset Name | DT ID | Qty | Anchor (X, Y, Z) | Orientation | IFC GUID | IFC Status |
|----------|-----------|-------|-----|------------------|-------------|----------|-----------|
| CCK-Z9-001 | Noise Test Booths (fridge) (×2) | — | 2 | (10.0, 28.0, 1.0) | Fixed | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z9-002 | Safety / Hipot Test Stations Z9 (×2) | — | 2 | (22.0, 26.0, 1.0) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z10-001 | Energy Efficiency Test Bench (Yokogawa WT333) (×2) | — | 2 | (45.0, 28.0, 1.0) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z10-002 | OBA Inspection Table (×2) | — | 2 | (60.0, 26.0, 0.9) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z11-001 | Auto Carton Erector — Large (Wexxar WF30) | — | 1 | (80.0, 30.0, 1.2) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z11-002 | Auto Carton Erector — Small (Lantech CST) | — | 1 | (85.0, 30.0, 1.2) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z11-003 | Carton Sealer Top/Bottom (×2) | — | 2 | (100.0, 30.0, 1.2) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z11-004 | Inline Label Printer/Applicator (Zebra ZT620) (×2) | — | 2 | (108.0, 30.0, 1.5) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z11-005 | Checkweigher (Mettler Toledo C35) (×2) | — | 2 | (112.0, 30.0, 1.0) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-Z11-006 | Pallet Wrapper (Robopac Rotoplat) (×2) | — | 2 | (116.0, 26.0, 1.0) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 9. Energy & Utilities Infrastructure

| Asset ID | Asset Name | DT ID | Qty | Anchor (X, Y, Z) | Orientation | IFC GUID | IFC Status |
|----------|-----------|-------|-----|------------------|-------------|----------|-----------|
| CCK-EN-001 | Solar PV Array — Rooftop (700 kWp) | DT-EN-01 | — | (60.0, 62.5, 11.0) | Roof centroid | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-EN-002 | LFP BESS Container (800 kWh) | DT-EN-02 | 1 | (115.0, 45.0, 1.5) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-EN-003 | Hybrid Grid-Tied Inverter (Sungrow SH250HX) (×4) | — | 4 | (113.0, 45.0, 1.5) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-EN-004 | Diesel Standby Generator (Perkins 500 kVA) | DT-EN-04 | 1 | (118.0, 57.0, 1.2) | Facing East | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-EN-005 | Compressed Air Compressor (Atlas Copco GA55+) (×2) | DT-EN-05 | 2 | (116.0, 62.0, 1.0) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-EN-006 | Nitrogen Generator (Parker NGP 30) | — | 1 | (118.0, 66.0, 1.0) | Facing North | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-EN-007 | Central HVAC Air Handling Unit (Daikin/Carrier) | — | 1 | (115.0, 90.0, 3.5) | Roof plant | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-EN-008 | MV/LV Main Distribution Panel (MDB) | — | 1 | (112.0, 118.0, 1.5) | N wall | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 10. Material Handling — AMR Fleet Anchor Points

AMR anchor points define the designated pick/drop locations and charging dock positions.

| Anchor ID | Type | Location Description | Anchor (X, Y, Z) | Zone | IFC Status |
|-----------|------|---------------------|------------------|------|-----------|
| AMR-DOCK-01 to 10 | Charging dock | AMR charging bay — Z1 east wall | (48.0, 97.0–110.0, 0.0) | Z1 | **[IFC-PENDING]** |
| AMR-PICK-Z1-A | Pick point | Z1 outbound — component kits for Z4 | (45.0, 100.0, 0.0) | Z1 | **[IFC-PENDING]** |
| AMR-DROP-Z4-A | Drop point | Z4 inbound — component kit station | (5.0, 90.0, 0.0) | Z4 | **[IFC-PENDING]** |
| AMR-PICK-Z1-B | Pick point | Z1 outbound — SMT reels for Z2 | (50.0, 105.0, 0.0) | Z1 | **[IFC-PENDING]** |
| AMR-DROP-Z2-A | Drop point | Z2 VLM input station | (52.0, 122.0, 0.0) | Z2 | **[IFC-PENDING]** |
| AMR-PICK-Z1-C | Pick point | Z1 outbound — SDA kitting for Z8 | (45.0, 108.0, 0.0) | Z1 | **[IFC-PENDING]** |
| AMR-DROP-Z8-A | Drop point | Z8 Line A inbound | (5.0, 54.0, 0.0) | Z8 | **[IFC-PENDING]** |
| AMR-PICK-Z9-A | Pick point | Z9 IPQC-passed units | (30.0, 34.0, 0.0) | Z9 | **[IFC-PENDING]** |
| AMR-DROP-Z11-A | Drop point | Z11 packaging inbound | (75.0, 36.0, 0.0) | Z11 | **[IFC-PENDING]** |
| AMR-PICK-Z11-B | Pick point | Z11 finished pallets | (115.0, 22.0, 0.0) | Z11 | **[IFC-PENDING]** |
| AMR-DROP-Z12-A | Drop point | Z12 FGW putaway | (60.0, 16.0, 0.0) | Z12 | **[IFC-PENDING]** |

---

## 11. IT / MES Infrastructure — Zone Z16

| Asset ID | Asset Name | Qty | Anchor (X, Y, Z) | IFC GUID | IFC Status |
|----------|-----------|-----|------------------|----------|-----------|
| CCK-IT-001 | MES Edge Node Server | 2 | (102.0, 105.0, 1.0) | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-IT-002 | AI Platform Inference GPU Node | 1 | (104.0, 105.0, 1.0) | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-IT-003 | InfluxDB Time-Series Server | 2 | (106.0, 105.0, 1.0) | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-IT-004 | MQTT Broker Node | 1 | (108.0, 105.0, 1.0) | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-IT-005 | Core Network Switch Stack | 1 | (108.0, 108.0, 1.8) | [IFC-PENDING] | **[IFC-PENDING]** |
| CCK-IT-006 | Precision CRAC Unit (Stulz/APC) | 1 | (109.5, 112.0, 0.0) | [IFC-PENDING] | **[IFC-PENDING]** |

---

## 12. IFC Delivery & Update Procedure

Upon receipt of the IFC model file from the architect:

1. Smart Factory Core Team uses an IFC viewer (e.g., Solibri, BIMcollab, or IfcOpenShell CLI) to extract IFC GUIDs for each asset listed above.
2. All `[IFC-PENDING]` GUID fields in this document are updated.
3. Anchor coordinates are reconciled against the IFC element centroids (to 3 decimal-place precision) and updated.
4. Asset anchors are imported into the Digital Twin 3D model layer.
5. AMR navigation system updated with precise drop/pick-point coordinates.
6. Document version incremented to 1.1 and committed.

---

*For zone boundary envelopes, refer to [docs/bim/zone-boundaries.md](./zone-boundaries.md).*
*For sensor placements, refer to [docs/sensor-map.md](../sensor-map.md).*
*For digital twin asset IDs, refer to [docs/digital-twin.md](../digital-twin.md).*
