# Kitchen Electronics Factory — Sensor Registry (Design Phase)

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Factory ID:** CCK-EL-KIT
> **Document Version:** 1.0 | **Owner:** Smart Factory Core Team
> **Status:** DESIGN-PHASE COMPLETE — Full commissioning registry (≥ 2,800 data points) to be populated from MES during factory commissioning

---

## 1. Overview

This document is the design-phase sensor registry for the Kitchen Electronics Factory. It defines all sensors, IoT data points, and monitored parameters required by the MES, Digital Twin, and AI Platform, derived from the approved factory design documentation.

**Design-phase registry scope:** All sensors identifiable from architectural drawings, machinery specifications, MES integration design, and the digital twin asset registry.

**Production commissioning registry:** The full production sensor registry (~2,800 data points, including every MES HMI parameter, PLC tag, energy sub-meter channel, and environmental sensor) will be populated into this document during MES commissioning (target: Q3–Q4 2026), using the MES tag export from Siemens Opcenter.

### Sensor ID Convention

```
CCK-[ZoneCode]-[SensorType]-[NNN]

Zone Codes: Z1..Z17, EN (energy/utilities), SF (safety systems)
Sensor Types:
  TMP = Temperature
  HMD = Humidity
  PRS = Pressure
  FLW = Flow
  VBR = Vibration
  PWR = Power (kW/kWh)
  CUR = Current (A)
  VLT = Voltage (V)
  GAS = Gas concentration
  LVL = Level
  SPD = Speed / belt speed
  WGT = Weight / mass
  CNT = Counter / cycle count
  POS = Position (RFID/conveyor carrier)
  OPT = Optical / vision pass/fail
  ENV = Environmental (multi-parameter)
```

---

## 2. Sensor Registry

### 2.1 Zone Z1 — Raw Material & Component Store

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z1-TMP-001 | Cold store sub-zone (ESD area) | Ambient temperature | °C | MQTT | Z1.ESD.Temp | 5 min | EMS module | ESD zone spec: 20–25°C |
| CCK-Z1-HMD-001 | Cold store sub-zone (ESD area) | Relative humidity | %RH | MQTT | Z1.ESD.RH | 5 min | EMS module | ESD zone spec: 40–60% |
| CCK-Z1-ENV-001 | Raw material store — north | Ambient temperature | °C | MQTT | Z1.RMS.Temp.N | 15 min | EMS module | |
| CCK-Z1-ENV-002 | Raw material store — south | Ambient temperature | °C | MQTT | Z1.RMS.Temp.S | 15 min | EMS module | |
| CCK-Z1-WGT-001 | Goods receipt weighbridge | Component batch weight | kg | MQTT | Z1.GR.Weight | Per scan | Goods receipt | Tolerance check per PO |
| CCK-Z1-CNT-001 | Incoming dock — barcode scanner #1 | Component scan count | count | RS-232→MES | Z1.Dock1.Scans | Per scan | MES goods receipt | |
| CCK-Z1-CNT-002 | Incoming dock — barcode scanner #2 | Component scan count | count | RS-232→MES | Z1.Dock2.Scans | Per scan | MES goods receipt | |
| CCK-Z1-ENV-003 | R600a cylinder sub-store | Ambient temperature | °C | MQTT | Z1.CylStore.Temp | 5 min | EHS dashboard | Max 30°C — NESREA limit |

---

### 2.2 Zone Z2 — SMT PCB Production

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z2-TMP-001 | SMT zone — HVAC supply air | Supply air temperature | °C | MQTT | Z2.HVAC.TempSupply | 1 min | EMS module | Spec: 22–24°C ±1°C |
| CCK-Z2-TMP-002 | SMT zone — ambient (north) | Ambient temperature | °C | MQTT | Z2.Amb.Temp.N | 5 min | EMS module | |
| CCK-Z2-TMP-003 | SMT zone — ambient (south) | Ambient temperature | °C | MQTT | Z2.Amb.Temp.S | 5 min | EMS module | |
| CCK-Z2-HMD-001 | SMT zone — ambient (north) | Relative humidity | %RH | MQTT | Z2.Amb.RH.N | 5 min | EMS module | Spec: 40–60% |
| CCK-Z2-HMD-002 | SMT zone — ambient (south) | Relative humidity | %RH | MQTT | Z2.Amb.RH.S | 5 min | EMS module | |
| CCK-Z2-TMP-004 | Reflow oven — Zone 1 (preheat) | Oven zone temperature | °C | OPC-UA | Z2.Reflow.Zone1.Temp | 1 sec | AI-SVC-05 (reflow profile) | Profile monitoring |
| CCK-Z2-TMP-005 | Reflow oven — Zone 2 (preheat) | Oven zone temperature | °C | OPC-UA | Z2.Reflow.Zone2.Temp | 1 sec | AI-SVC-05 | |
| CCK-Z2-TMP-006 | Reflow oven — Zone 3 (soak) | Oven zone temperature | °C | OPC-UA | Z2.Reflow.Zone3.Temp | 1 sec | AI-SVC-05 | |
| CCK-Z2-TMP-007 | Reflow oven — Zone 4 (soak) | Oven zone temperature | °C | OPC-UA | Z2.Reflow.Zone4.Temp | 1 sec | AI-SVC-05 | |
| CCK-Z2-TMP-008 | Reflow oven — Zone 5 (reflow) | Oven zone temperature | °C | OPC-UA | Z2.Reflow.Zone5.Temp | 1 sec | AI-SVC-05 | Peak zone |
| CCK-Z2-TMP-009 | Reflow oven — Zone 6 (reflow) | Oven zone temperature | °C | OPC-UA | Z2.Reflow.Zone6.Temp | 1 sec | AI-SVC-05 | Peak zone |
| CCK-Z2-TMP-010 | Reflow oven — Zone 7 (cooling) | Oven zone temperature | °C | OPC-UA | Z2.Reflow.Zone7.Temp | 1 sec | AI-SVC-05 | |
| CCK-Z2-TMP-011 | Reflow oven — Zone 8 (cooling) | Oven zone temperature | °C | OPC-UA | Z2.Reflow.Zone8.Temp | 1 sec | AI-SVC-05 | |
| CCK-Z2-SPD-001 | Reflow oven — belt | Belt speed | m/min | OPC-UA | Z2.Reflow.BeltSpeed | 1 sec | AI-SVC-05 | |
| CCK-Z2-FLW-001 | Reflow oven — N₂ supply | N₂ flow rate | l/min | OPC-UA | Z2.Reflow.N2Flow | 1 min | EMS module | N₂ consumption model |
| CCK-Z2-CNT-001 | JUKI FX-3R P&P — feeder | Components placed per hour (CPH) | CPH | OPC-UA | Z2.PnP1.CPH | 1 min | MES production event | |
| CCK-Z2-CNT-002 | JUKI FX-3R P&P — vision error | Vision error count | count | OPC-UA | Z2.PnP1.VisionErrors | Per event | MES quality result | |
| CCK-Z2-CNT-003 | JUKI RX-7 P&P — feeder | CPH | CPH | OPC-UA | Z2.PnP2.CPH | 1 min | MES production event | |
| CCK-Z2-CNT-004 | Koh Young 3D AOI | Defect count per board | count | OPC-UA | Z2.AOI.DefectCount | Per board | MES quality result | SPC trigger |
| CCK-Z2-CNT-005 | Koh Young SPI | Paste volume deviation count | count | OPC-UA | Z2.SPI.VolumeDeviation | Per board | MES quality result | |
| CCK-Z2-PWR-001 | SMT zone — energy sub-meter | Zone power consumption | kW | MQTT | Z2.Energy.kW | 15 min | EMS + AI-SVC-01 | Energy per unit model |
| CCK-Z2-PRS-001 | SMT zone — HVAC positive pressure | Zone differential pressure | Pa | MQTT | Z2.HVAC.DiffPressure | 5 min | EMS module | Spec: +5 to +15 Pa |

---

### 2.3 Zone Z3 — Sheet Metal Fabrication

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z3-CNT-001 | Roll-form line — press cycle counter | Press cycle count | count | MQTT IoT GW | Z3.RollForm.CycleCount | Per cycle | MES CMMS | PM trigger at target cycles |
| CCK-Z3-SPD-001 | Roll-form line — strip speed | Strip feed speed | m/min | MQTT IoT GW | Z3.RollForm.Speed | 10 sec | MES production event | |
| CCK-Z3-CNT-002 | Press brake — stroke counter | Press stroke count | count | MQTT IoT GW | Z3.Press.StrokeCount | Per stroke | MES CMMS | |
| CCK-Z3-TMP-001 | Sheet metal zone — ambient | Ambient temperature | °C | MQTT | Z3.Amb.Temp | 15 min | EMS module | |
| CCK-Z3-PWR-001 | Sheet metal zone — energy sub-meter | Zone power consumption | kW | MQTT | Z3.Energy.kW | 15 min | EMS + AI-SVC-01 | |
| CCK-Z3-VBR-001 | Roll-form line — motor bearing | Bearing vibration (X axis) | mm/s | MQTT | Z3.RollForm.Motor.VibX | 10 sec | MES CMMS (predictive) | PM alert on trend |

---

### 2.4 Zone Z4 — Refrigerator Assembly (Main)

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z4-TMP-001 | PU foam injection — polyol feed | Polyol temperature | °C | MQTT IoT GW | Z4.Foam.Polyol.Temp | 10 sec | AI-SVC-06 (Phase 2) | Foam quality model input |
| CCK-Z4-PRS-001 | PU foam injection — injection | Injection pressure | bar | MQTT IoT GW | Z4.Foam.InjPressure | 1 sec | AI-SVC-06 (Phase 2) | |
| CCK-Z4-FLW-001 | PU foam injection — polyol flow | Polyol volumetric flow | l/min | MQTT IoT GW | Z4.Foam.Polyol.Flow | 1 sec | AI-SVC-06 (Phase 2) | Ratio monitoring |
| CCK-Z4-FLW-002 | PU foam injection — isocyanate flow | Isocyanate volumetric flow | l/min | MQTT IoT GW | Z4.Foam.ISO.Flow | 1 sec | AI-SVC-06 (Phase 2) | Ratio monitoring |
| CCK-Z4-CNT-001 | PU foam injection — cycle count | Injection cycle count | count | MQTT IoT GW | Z4.Foam.CycleCount | Per cycle | MES CMMS | PM trigger |
| CCK-Z4-TMP-002 | Foam curing rack — ambient | Cure ambient temperature | °C | MQTT | Z4.FoamCure.Temp | 5 min | MES production event | |
| CCK-Z4-SPD-001 | Overhead chain conveyor — belt speed | Conveyor speed | m/min | OPC-UA | Z4.Conv.Speed | 1 sec | MES takt event | Takt-linked |
| CCK-Z4-CUR-001 | Overhead chain conveyor — drive motor | Motor current draw | A | OPC-UA | Z4.Conv.MotorCurrent | 10 sec | MES CMMS | Tension / wear indicator |
| CCK-Z4-POS-001 | Overhead conveyor — carrier position (RFID) | Carrier position tag | RFID | OPC-UA | Z4.Conv.Carrier.Pos | Per RFID read | MES WIP tracking | 12 RFID readers on line |
| CCK-Z4-VBR-001 | Overhead conveyor — drive unit | Drive bearing vibration | mm/s | MQTT | Z4.Conv.Drive.Vib | 30 sec | MES CMMS | |
| CCK-Z4-TMP-003 | Refrigerator assembly zone — ambient north | Ambient temperature | °C | MQTT | Z4.Amb.Temp.N | 15 min | EMS module | |
| CCK-Z4-TMP-004 | Refrigerator assembly zone — ambient south | Ambient temperature | °C | MQTT | Z4.Amb.Temp.S | 15 min | EMS module | |
| CCK-Z4-PWR-001 | Refrigerator assembly zone — energy sub-meter | Zone power consumption | kW | MQTT | Z4.Energy.kW | 15 min | EMS + AI-SVC-01 | Foam injection peak: ~45 kW |
| CCK-Z4-CNT-002 | Performance test station — unit counter | Units tested | count | MQTT | Z4.PerfTest.UnitCount | Per unit | MES quality result | |
| CCK-Z4-PWR-002 | Performance test station — power analyser | Unit power draw during test | W | MQTT | Z4.PerfTest.UnitPower | 1 min | MES quality result | IEC 62552 compliance |

---

### 2.5 Zone Z5 — R600a Gas Charging Zone

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z5-GAS-001 | Gas zone — detector position 1 (SW floor) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D01.LEL | 5 sec | EHS alarm; MES gas module | Alarm at 10% LEL; shutdown at 25% LEL |
| CCK-Z5-GAS-002 | Gas zone — detector position 2 (SE floor) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D02.LEL | 5 sec | EHS alarm | |
| CCK-Z5-GAS-003 | Gas zone — detector position 3 (NE floor) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D03.LEL | 5 sec | EHS alarm | |
| CCK-Z5-GAS-004 | Gas zone — detector position 4 (NW floor) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D04.LEL | 5 sec | EHS alarm | |
| CCK-Z5-GAS-005 | Gas zone — detector position 5 (charging station 1) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D05.LEL | 5 sec | EHS alarm; MES gas module | At charging station 1 |
| CCK-Z5-GAS-006 | Gas zone — detector position 6 (charging station 2) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D06.LEL | 5 sec | EHS alarm; MES gas module | At charging station 2 |
| CCK-Z5-GAS-007 | Gas zone — detector position 7 (entry east) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D07.LEL | 5 sec | EHS alarm | Zone entry monitoring |
| CCK-Z5-GAS-008 | Gas zone — detector position 8 (entry west) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D08.LEL | 5 sec | EHS alarm | |
| CCK-Z5-GAS-009 | Gas zone — detector position 9 (cylinder store N) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D09.LEL | 5 sec | EHS alarm | Near cylinder rack |
| CCK-Z5-GAS-010 | Gas zone — detector position 10 (cylinder store S) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D10.LEL | 5 sec | EHS alarm | |
| CCK-Z5-GAS-011 | Gas zone — detector position 11 (vacuum area N) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D11.LEL | 5 sec | EHS alarm | |
| CCK-Z5-GAS-012 | Gas zone — detector position 12 (vacuum area S) | R600a concentration | % LEL | OPC-UA | Z5.Gas.D12.LEL | 5 sec | EHS alarm | 12th Draeger sensor (design count) |
| CCK-Z5-WGT-001 | Gas charging station #1 — charge weight scale | Refrigerant charge weight | g | OPC-UA | Z5.CS1.ChargeWeight | Per charge | MES R600a gas module | Linked to unit serial |
| CCK-Z5-PRS-001 | Gas charging station #1 — cylinder pressure | Cylinder inlet pressure | bar | OPC-UA | Z5.CS1.CylPressure | Per charge | MES R600a gas module | |
| CCK-Z5-WGT-002 | Gas charging station #2 — charge weight scale | Refrigerant charge weight | g | OPC-UA | Z5.CS2.ChargeWeight | Per charge | MES R600a gas module | |
| CCK-Z5-PRS-002 | Gas charging station #2 — cylinder pressure | Cylinder inlet pressure | bar | OPC-UA | Z5.CS2.CylPressure | Per charge | MES R600a gas module | |
| CCK-Z5-PRS-003 | Vacuum pump #1 — vacuum level | Final vacuum level | micron | OPC-UA | Z5.VP1.VacuumLevel | 10 sec | MES R600a gas module | Spec: < 200 microns |
| CCK-Z5-TMP-001 | Vacuum pump #1 — exhaust | Exhaust temperature | °C | MQTT | Z5.VP1.ExhaustTemp | 30 sec | MES CMMS | Pump health |
| CCK-Z5-PRS-004 | Vacuum pump #2 — vacuum level | Final vacuum level | micron | OPC-UA | Z5.VP2.VacuumLevel | 10 sec | MES R600a gas module | |
| CCK-Z5-TMP-002 | Vacuum pump #2 — exhaust | Exhaust temperature | °C | MQTT | Z5.VP2.ExhaustTemp | 30 sec | MES CMMS | |
| CCK-Z5-PRS-005 | Gas zone — pressure decay test (unit-under-test) | Pressure decay | mbar | OPC-UA | Z5.LeakTest.PressDecay | Per test | MES R600a gas module | Leak test pass/fail |
| CCK-Z5-FLW-001 | Gas zone — ventilation fan flow | Air flow rate (ventilation) | m³/h | MQTT | Z5.Vent.AirFlow | 1 min | EHS dashboard | Min 15 ACH required |
| CCK-Z5-TMP-003 | Gas zone — ambient temperature | Zone ambient temperature | °C | MQTT | Z5.Amb.Temp | 1 min | EHS dashboard | |
| CCK-Z5-PWR-001 | Gas zone — energy sub-meter | Zone power consumption | kW | MQTT | Z5.Energy.kW | 15 min | EMS module | |

---

### 2.6 Zone Z6 — Microwave Oven Assembly

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z6-CNT-001 | Microwave leak test station #1 | RF leakage test result | mW/cm² | MQTT | Z6.LeakTest1.Leakage | Per unit | MES quality result | IEC 60335-2-25: ≤ 5 mW/cm² |
| CCK-Z6-CNT-002 | Microwave leak test station #2 | RF leakage test result | mW/cm² | MQTT | Z6.LeakTest2.Leakage | Per unit | MES quality result | |
| CCK-Z6-CNT-003 | Functional test station — power test | Measured cooking power | W | MQTT | Z6.FuncTest.CookPower | Per unit | MES quality result | |
| CCK-Z6-CNT-004 | Hipot test station #1 — hipot voltage | Dielectric test voltage | V | MQTT | Z6.Hipot1.Voltage | Per unit | MES quality result | IEC 60335-1 Cl.16 |
| CCK-Z6-TMP-001 | Microwave assembly zone — ambient | Ambient temperature | °C | MQTT | Z6.Amb.Temp | 15 min | EMS module | |
| CCK-Z6-PWR-001 | Microwave zone — energy sub-meter | Zone power consumption | kW | MQTT | Z6.Energy.kW | 15 min | EMS + AI-SVC-01 | |

---

### 2.7 Zone Z7 — Electric Cooker Assembly

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z7-CNT-001 | Induction efficiency test (Fluke 1760) | Coil efficiency | % | MQTT | Z7.IndEff.Efficiency | Per unit | MES quality result | |
| CCK-Z7-CNT-002 | Cooker function test — element temp calibration | Element temperature accuracy | °C | MQTT | Z7.FuncTest.ElemTemp | Per unit | MES quality result | |
| CCK-Z7-CNT-003 | Hipot & earth continuity — hipot result | Test result (pass/fail) | bool | MQTT | Z7.Hipot.Result | Per unit | MES quality result | IEC 60335-2-6 |
| CCK-Z7-TMP-001 | Cooker assembly zone — ambient | Ambient temperature | °C | MQTT | Z7.Amb.Temp | 15 min | EMS module | |
| CCK-Z7-PWR-001 | Cooker zone — energy sub-meter | Zone power consumption | kW | MQTT | Z7.Energy.kW | 15 min | EMS + AI-SVC-01 | |

---

### 2.8 Zone Z8 — SDA Assembly Lines A, B, C

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z8-CNT-001 | SDA Line A — blender output counter | Units completed (Line A) | count | MQTT | Z8.LineA.UnitsOut | Per unit | MES production event | |
| CCK-Z8-CNT-002 | SDA Line A — blender function test result | Function test pass/fail | bool | MQTT | Z8.LineA.FuncTest | Per unit | MES quality result | Motor run + speed test |
| CCK-Z8-CNT-003 | SDA Line B — kettle output counter | Units completed (Line B) | count | MQTT | Z8.LineB.UnitsOut | Per unit | MES production event | |
| CCK-Z8-CNT-004 | SDA Line B — kettle auto-boil test result | Boil-to-shutoff pass/fail | bool | MQTT | Z8.LineB.BoilTest | Per unit | MES quality result | Auto-shutoff at 100°C |
| CCK-Z8-CNT-005 | SDA Line C — rice cooker output counter | Units completed (Line C) | count | MQTT | Z8.LineC.UnitsOut | Per unit | MES production event | |
| CCK-Z8-CNT-006 | SDA hipot test — all lines | Hipot test result | bool | MQTT | Z8.Hipot.Result | Per unit | MES quality result | IEC 60335 series |
| CCK-Z8-TMP-001 | SDA zone — ambient north | Ambient temperature | °C | MQTT | Z8.Amb.Temp.N | 15 min | EMS module | |
| CCK-Z8-TMP-002 | SDA zone — ambient south | Ambient temperature | °C | MQTT | Z8.Amb.Temp.S | 15 min | EMS module | |
| CCK-Z8-PWR-001 | SDA zone — energy sub-meter | Zone power consumption | kW | MQTT | Z8.Energy.kW | 15 min | EMS + AI-SVC-01 | |

---

### 2.9 Zones Z9 & Z10 — In-Process QC & Final QC

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z9-CNT-001 | Noise test booth #1 — fridge noise | Operating noise level | dBA | MQTT | Z9.NoiseTest1.dBA | Per test | MES quality result | |
| CCK-Z9-CNT-002 | Noise test booth #2 — fridge noise | Operating noise level | dBA | MQTT | Z9.NoiseTest2.dBA | Per test | MES quality result | |
| CCK-Z9-CNT-003 | IPQC hipot station — result | Hipot pass/fail | bool | MQTT | Z9.Hipot.Result | Per unit | MES quality result | |
| CCK-Z10-PWR-001 | Final QC energy test bench (Yokogawa WT333) | Unit energy consumption | kWh/24h | MQTT | Z10.EnergyTest.kWh24h | Per test | MES quality result | IEC 62552 compliance |
| CCK-Z10-CNT-001 | OBA inspection station — sample result | OBA sample pass/fail | bool | MQTT | Z10.OBA.SampleResult | Per sample | MES quality result | |
| CCK-Z9-TMP-001 | IPQC zone — ambient | Ambient temperature | °C | MQTT | Z9.Amb.Temp | 15 min | EMS module | |
| CCK-Z10-TMP-001 | Final QC zone — ambient | Ambient temperature | °C | MQTT | Z10.Amb.Temp | 15 min | EMS module | |

---

### 2.10 Zones Z11 & Z12 — Packaging & Finished Goods Warehouse

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z11-WGT-001 | Checkweigher #1 — packed fridge carton | Packed carton weight | kg | MQTT | Z11.CW1.Weight | Per carton | MES quality result | Reject on ± spec |
| CCK-Z11-WGT-002 | Checkweigher #2 — packed SDA carton | Packed carton weight | kg | MQTT | Z11.CW2.Weight | Per carton | MES quality result | |
| CCK-Z11-OPT-001 | Barcode verifier #1 — label quality | Barcode grade | grade | MQTT | Z11.BCV1.Grade | Per label | MES label control | Min grade: B (ISO 15415) |
| CCK-Z11-OPT-002 | Barcode verifier #2 — label quality | Barcode grade | grade | MQTT | Z11.BCV2.Grade | Per label | MES label control | |
| CCK-Z11-PWR-001 | Packaging zone — energy sub-meter | Zone power consumption | kW | MQTT | Z11.Energy.kW | 15 min | EMS module | |
| CCK-Z12-TMP-001 | FGW — ambient north | Ambient temperature | °C | MQTT | Z12.Amb.Temp.N | 30 min | EMS module | Refrigerator storage temp |
| CCK-Z12-TMP-002 | FGW — ambient south | Ambient temperature | °C | MQTT | Z12.Amb.Temp.S | 30 min | EMS module | |
| CCK-Z12-ENV-001 | FGW — ESFR sprinkler system | Water flow alarm | bool | MQTT | Z12.Sprinkler.FlowAlarm | On event | Safety / EHS dashboard | |

---

### 2.11 Energy & Utilities — Cross-Zone

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-EN-PWR-001 | Solar PV array — inverter output #1 | DC generation power | kW | SCADA/MQTT | EN.Solar.Inv1.kW | 1 min | EMS + AI-SVC-04 | |
| CCK-EN-PWR-002 | Solar PV array — inverter output #2 | DC generation power | kW | SCADA/MQTT | EN.Solar.Inv2.kW | 1 min | EMS + AI-SVC-04 | |
| CCK-EN-PWR-003 | Solar PV array — inverter output #3 | DC generation power | kW | SCADA/MQTT | EN.Solar.Inv3.kW | 1 min | EMS + AI-SVC-04 | |
| CCK-EN-PWR-004 | Solar PV array — inverter output #4 | DC generation power | kW | SCADA/MQTT | EN.Solar.Inv4.kW | 1 min | EMS + AI-SVC-04 | |
| CCK-EN-TMP-001 | Solar PV array — panel temperature (sample) | Panel surface temperature | °C | SCADA/MQTT | EN.Solar.PanelTemp | 5 min | AI-SVC-04 | Sample of 4 panel strings |
| CCK-EN-LVL-001 | BESS — state of charge | Battery SoC | % | BMS/MQTT | EN.BESS.SoC | 1 min | EMS + AI-SVC-04 | BMS: CATL/BYD native |
| CCK-EN-PWR-005 | BESS — charge/discharge power | Charge (+) / Discharge (−) rate | kW | BMS/MQTT | EN.BESS.ChargePower | 1 min | EMS dispatch | |
| CCK-EN-TMP-002 | BESS — cell temperature (average) | Cell pack average temperature | °C | BMS/MQTT | EN.BESS.CellTemp.Avg | 5 min | EMS + DT-EN-02 | |
| CCK-EN-CNT-001 | BESS — cycle count | Full equivalent charge cycles | count | BMS/MQTT | EN.BESS.CycleCount | Daily | DT-EN-02 (SoH model) | |
| CCK-EN-PWR-006 | Grid connection — import/export | Grid import (+) / export (−) | kW | SCADA/MQTT | EN.Grid.Power | 1 min | EMS | Self-sufficiency KPI |
| CCK-EN-VLT-001 | Grid connection — voltage | Grid voltage | V | SCADA/MQTT | EN.Grid.Voltage | 1 min | EMS | Power quality |
| CCK-EN-FRQ-001 | Grid connection — frequency | Grid frequency | Hz | SCADA/MQTT | EN.Grid.Freq | 1 min | EMS | |
| CCK-EN-PWR-007 | Diesel generator — output | Generator output power | kW | MQTT | EN.Gen.OutputkW | 1 min | EMS + DT-EN-04 | |
| CCK-EN-LVL-002 | Diesel generator — fuel tank | Fuel tank level | L | MQTT | EN.Gen.FuelLevel | 5 min | EMS + DT-EN-04 | Reorder < 500 L |
| CCK-EN-CNT-002 | Diesel generator — runtime hours | Accumulated run hours | h | MQTT | EN.Gen.RunHours | On start/stop | MES CMMS | Service at 500 h |
| CCK-EN-PRS-001 | Compressed air — main header pressure | System pressure | bar | MQTT | EN.CA.Pressure | 1 min | EMS + DT-EN-05 | Spec: 6.5–7.5 bar |
| CCK-EN-FLW-001 | Compressed air — flow (main header) | Compressed air flow rate | m³/h | MQTT | EN.CA.Flow | 5 min | EMS (leak rate model) | |
| CCK-EN-CNT-003 | Compressed air — compressor run hours | Run hours (Compressor 1) | h | MQTT | EN.CA.Comp1.RunH | On start/stop | MES CMMS | Service at 4,000 h |
| CCK-EN-CNT-004 | Compressed air — compressor run hours | Run hours (Compressor 2) | h | MQTT | EN.CA.Comp2.RunH | On start/stop | MES CMMS | |
| CCK-EN-PWR-008 | Factory total — main energy meter (MDB) | Total factory power | kW | SCADA/MQTT | EN.Factory.TotalPower | 15 min | EMS / MES energy module | Overall energy intensity KPI |
| CCK-EN-PWR-009 | Factory total — daily energy | Daily factory energy | kWh | SCADA/MQTT | EN.Factory.DailykWh | Daily | EMS | |

---

### 2.12 Zone Z16 — IT / MES Server Room

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-Z16-TMP-001 | Server room — CRAC supply | Server room temperature | °C | SNMP/MQTT | Z16.ServerRoom.Temp | 2 min | IT monitoring | Spec: 18–24°C |
| CCK-Z16-HMD-001 | Server room — ambient | Server room humidity | %RH | SNMP/MQTT | Z16.ServerRoom.RH | 5 min | IT monitoring | Spec: 40–60% |
| CCK-Z16-PWR-001 | Server room — UPS input | Server room power consumption | kW | SNMP/MQTT | Z16.UPS.InputkW | 5 min | EMS module | |
| CCK-Z16-ENV-001 | Server room — FM-200 system | FM-200 discharge alarm | bool | SNMP/MQTT | Z16.FM200.DischargeAlarm | On event | EHS + IT dashboard | |

---

### 2.13 Safety Systems — All Zones

| Sensor ID | Asset / Location | Measurement | Unit | Protocol | Tag Name | Sample Rate | MES Integration | Notes |
|-----------|-----------------|-------------|------|----------|----------|-------------|----------------|-------|
| CCK-SF-GAS-001 | R600a zone — composite alarm | Highest zone gas alarm state | % LEL | OPC-UA | SF.R600a.MaxLEL | 5 sec | EHS dashboard; MES safety alert | Computed max of Z5.Gas.D01–D12 |
| CCK-SF-ENV-001 | Factory-wide — fire alarm panel | Fire alarm state | bool | Modbus/MQTT | SF.Fire.AlarmState | On event | MES safety alert; EHS | Notifier addressable panel |
| CCK-SF-ENV-002 | Z5 — gas zone ESD button | Emergency stop state | bool | OPC-UA | SF.Z5.ESDButton | On event | MES safety alert; EHS | Big red button — gas zone |
| CCK-SF-ENV-003 | Z2 — SMT zone FM-200 | FM-200 discharge alarm | bool | MQTT | SF.Z2.FM200.Alarm | On event | MES safety alert; EHS | SMT zone suppression |
| CCK-SF-ENV-004 | Z16 — server room FM-200 | FM-200 discharge alarm | bool | MQTT | SF.Z16.FM200.Alarm | On event | IT + EHS dashboard | |
| CCK-SF-ENV-005 | Factory-wide — muster point status (×3) | Evacuation muster count | count | MQTT | SF.Muster.P1/P2/P3.Count | On event | EHS dashboard | RFID badge scan at muster |

---

## 3. Design-Phase Registry Summary

| Zone / Area | Sensor Count (Design Phase) |
|-------------|----------------------------|
| Z1 — Raw Material Store | 8 |
| Z2 — SMT PCB Production | 22 |
| Z3 — Sheet Metal Fabrication | 6 |
| Z4 — Refrigerator Assembly | 15 |
| Z5 — R600a Gas Charging | 25 |
| Z6 — Microwave Assembly | 6 |
| Z7 — Cooker Assembly | 5 |
| Z8 — SDA Lines | 9 |
| Z9 + Z10 — QC Zones | 7 |
| Z11 + Z12 — Packaging / FGW | 8 |
| Energy & Utilities (EN) | 22 |
| Z16 — IT / Server Room | 4 |
| Safety Systems (SF) | 6 |
| **Total (Design Phase)** | **143** |

> **Production commissioning note:** The design-phase registry above defines 143 primary measurement points. The full production sensor registry is expected to reach **≥ 2,800 data points** once all MES HMI station parameters, individual PLC I/O tags, energy sub-channel readings, and AMR telemetry points are exported from Siemens Opcenter during commissioning. This document will be updated in-place with the full commissioning export.

---

## 4. Sensor Protocols Summary

| Protocol | Systems Using It | Notes |
|----------|-----------------|-------|
| OPC-UA | SMT machines (DEK, JUKI, Heller, Koh Young); gas charging PLCs; overhead conveyor PLC | Industry standard for machine-MES integration |
| MQTT (factory broker) | All IoT sensors; energy meters; environmental sensors; safety systems | HiveMQ Enterprise broker in Z16 |
| RS-232 / RS-485 → MQTT GW | Legacy barcode scanners; older test equipment | IoT gateway converts to MQTT |
| SCADA (Modbus / DNP3) | Solar inverters; BESS BMS; generator | SCADA integrates to EMS |
| SNMP | Server room environment sensors; UPS | IT standard monitoring |
| Modbus TCP | Fire alarm panel; selected energy meters | Factory automation standard |

---

*For asset locations (anchor coordinates), refer to [docs/bim/asset-anchors.md](./bim/asset-anchors.md).*
*For zone boundary envelopes, refer to [docs/bim/zone-boundaries.md](./bim/zone-boundaries.md).*
*For MES API endpoints consuming sensor data, refer to [docs/mes-integration.md](./mes-integration.md).*
*For AI services consuming sensor streams, refer to [docs/ai-platform-status.md](./ai-platform-status.md).*
