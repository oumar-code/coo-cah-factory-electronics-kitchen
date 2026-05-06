# Kitchen Electronics Factory — Energy Profile

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Location:** Agbara Industrial Estate, Lagos State | **Phase:** Phase 1
> **Document Version:** 1.0 | **Owner:** Facilities & Energy Management Team

---

## 1. Executive Summary

| Energy System Metric | Value |
|---------------------|-------|
| Facility Area | ~15,000 m² |
| Estimated Peak Load (Phase 1) | ~500 kW |
| Daily Energy Consumption | ~3,500 kWh/day (16h operational) |
| Solar PV System | 700 kWp — rooftop monocrystalline PERC |
| BESS | 800 kWh LFP (Lithium Iron Phosphate) |
| Daily Solar Generation (average) | ~3,360 kWh/day at 4.8 PSH |
| Target Solar Self-Sufficiency | ≥ 80% of operational energy |
| Grid Role | Supplementary + overnight critical loads |
| Backup Generator | 1 × Perkins 500 kVA diesel; 2,000 L tank (~72 h at 40% load) |
| Estimated Annual CO₂ Avoidance | ~700 tonnes CO₂/year vs. 100% grid |

---

## 2. Power Demand Analysis

### 2.1 Major Load Categories

| Load Category | Equipment | Connected Load (kW) | Demand Factor | Operational Load (kW) |
|---------------|-----------|---------------------|---------------|----------------------|
| Production — SMT Line | Reflow oven (8-zone), screen printer, P&P, AOI | 85 | 0.75 | 64 |
| Production — Refrigerator Assembly | PU foam injection (45 kW), overhead conveyor, assembly tools | 120 | 0.65 | 78 |
| Production — Microwave Assembly | Spot welder, test stations, tooling | 40 | 0.60 | 24 |
| Production — Cooker Assembly | Induction coil winder, glass bonding, test rigs | 35 | 0.60 | 21 |
| Production — SDA Lines (A, B, C) | 3 conveyor lines, motor assembly, test stations | 45 | 0.70 | 31.5 |
| Production — Packaging Line | Carton erector, sealer, pallet wrapper, labeller | 30 | 0.70 | 21 |
| Compressed Air System | 2 × Atlas Copco GA55+ (55 kW each) | 110 | 0.60 | 66 |
| HVAC System | Daikin VRV + Carrier AHU | 120 | 0.80 | 96 |
| Lighting (LED) | Factory + office + warehouse LED | 35 | 0.90 | 31.5 |
| IT / MES / Servers | Edge servers, panel PCs, APs, CCTV, network | 15 | 0.95 | 14.25 |
| AMR Charging | 10 × MiR200 chargers (1.5 kW each) | 15 | 0.40 | 6 |
| Office, Cafeteria, Utilities | Air conditioning, kitchen, general | 30 | 0.80 | 24 |
| **Total Connected Load** | | **680 kW** | — | |
| **Estimated Peak Demand** | | | | **~500 kW** |

> **Design basis:** 500 kW peak demand. Diversity factor = 0.74. Load-shedding can reduce demand to 350 kW (non-production zones curtailed) when operating on BESS only.

### 2.2 Daily Load Profile

| Time Window | Mode | Grid Dependency | Load (kW) |
|-------------|------|-----------------|-----------|
| 06:00–07:00 | Morning start-up | Solar ramp + BESS | 280–350 |
| 07:00–13:00 | Full production | Solar primary + BESS buffer | 450–500 |
| 13:00–14:00 | Lunch break | Solar + BESS charges | 200–250 |
| 14:00–18:00 | Full production (afternoon) | Solar primary | 450–500 |
| 18:00–20:00 | Wind-down + cleaning | BESS primary + grid backup | 150–200 |
| 20:00–06:00 | Overnight — servers + security only | BESS + grid | 30–50 |

---

## 3. Solar PV System Design — 700 kWp

### 3.1 System Specifications

| Parameter | Value |
|-----------|-------|
| Installed Capacity | 700 kWp |
| Panel Technology | Monocrystalline PERC, 550W panels (approx. 1,273 panels) |
| Preferred OEM | Longi Solar / Risen Energy (Group-approved) |
| Mounting | Rooftop on factory main building and warehouse roof |
| Roof Area Required | ~4,550 m² (6.5 m²/kWp) |
| Available Roof Area | ~7,800 m² usable |
| System Voltage | 1,000V DC string voltage |
| Tilt Angle | 5° (low-tilt for roof loading; optimal for Lagos 6.4° latitude) |
| Panel Orientation | South-facing where roof orientation allows; east-west split on remaining area |

### 3.2 Lagos Solar Resource

| Parameter | Value |
|-----------|-------|
| Site Latitude | 6.4° N (Agbara, Lagos State) |
| Annual Average PSH | 4.8 PSH/day (Peak Sun Hours) |
| Worst Month (August) | 3.9 PSH/day (harmattan + cloud cover) |
| Best Month (November) | 6.2 PSH/day |
| Performance Ratio | 0.82 (soiling losses, temperature, inverter efficiency, wiring) |

### 3.3 Energy Generation Estimate

| Calculation Parameter | Value |
|----------------------|-------|
| Installed capacity | 700 kWp |
| Annual average PSH | 4.8 h/day |
| Performance ratio | 0.82 |
| **Annual generation** | **700 × 4.8 × 0.82 × 365 = ~1,005,000 kWh/year** |
| **Daily average** | ~2,753 kWh/day (annual average) |
| **Daily average (best month, Nov)** | ~3,540 kWh/day |
| **Daily average (worst month, Aug)** | ~2,235 kWh/day |

> **Conclusion:** The 700 kWp system generates an average of 2,753 kWh/day versus a factory demand of ~3,500 kWh/day. The gap is bridged by BESS carry-over from high-irradiance periods and overnight grid import for critical loads.

---

## 4. Battery Energy Storage System (BESS) — 800 kWh LFP

### 4.1 BESS Specifications

| Parameter | Value |
|-----------|-------|
| Nominal Capacity | 800 kWh |
| Usable Capacity | 720 kWh (90% DoD) |
| Chemistry | Lithium Iron Phosphate (LFP) — cycle-stable, thermally safe |
| DC Bus Voltage | 400V DC |
| Preferred OEM | CATL / BYD (containerised BESS, 250 kWh per container) |
| Configuration | 3 × 250 kWh + 1 × 50 kWh modules (or 4 × 200 kWh blocks) |
| Cycle Life | ≥ 6,000 cycles at 80% DoD (LFP advantage) |
| Round-Trip Efficiency | ≥ 93% |
| BMS | Integrated BMS with SCADA/Modbus integration to EMS |
| Thermal Management | Liquid-cooled container with HVAC |

### 4.2 BESS Dispatch Strategy

| Dispatch Mode | Trigger | Action |
|---------------|---------|--------|
| Peak Shaving | Grid demand > 50 kW | BESS discharges at up to 200 kW to limit grid import |
| Solar Firming | Solar generation < 200 kW (morning/evening) | BESS fills gap to sustain production |
| Overnight Critical Loads | After 20:00 h | BESS supplies MES servers, security (30–50 kW) from SoC > 50% |
| Minimum SoC Reserve | Continuous | BESS maintains ≥ 20% SoC (160 kWh) as generator-start buffer |
| Grid Outage Mode | Grid failure detected by ATS | BESS island mode; generator start if SoC < 30% |

### 4.3 Grid Outage Autonomy

| Load Scenario | BESS Discharge Rate | Autonomy Duration |
|---------------|--------------------|--------------------|
| Full production (500 kW peak) | 500 kW | ~1.44 hours |
| Reduced production (350 kW) | 350 kW | ~2.06 hours |
| Critical loads only (50 kW) | 50 kW | ~14.4 hours |
| Combined solar + BESS (full production) | Solar provides 350 kW + BESS 150 kW | ~4.8 hours (daytime) |

---

## 5. Backup Generator

| Parameter | Value |
|-----------|-------|
| Make / Model | Perkins 500 kVA (400 kW output) |
| Fuel | Diesel (low-sulphur) |
| Tank Capacity | 2,000 L |
| Runtime at 40% Load | ~72 hours (160 kW load) |
| Runtime at Full Load | ~22 hours (400 kW load) |
| Start Mode | Auto-start via ATS (SOCOMEC SIRCO AC) |
| Planned Start Test | Weekly unloaded test; monthly loaded test |
| Enclosure | Weatherproof canopy; acoustic enclosure (≤ 75 dBa at 7m) |
| Exhaust | Vertical stack; exhaust away from loading bay and staff areas |

---

## 6. Grid Connection

| Parameter | Value |
|-----------|-------|
| Grid Supply Authority | Ikeja Electric / Eko Electric (Lagos State) |
| Estimated Daily Grid Hours | 8–12 h/day (typical for Lagos industrial areas) |
| Connection Type | 11 kV / 33 kV dedicated feeder (negotiated for large factory sites) |
| Metering | Smart meter with 15-minute interval logging; auto-export tracking |
| Grid Import Purpose | Overnight critical loads; supplementary when solar insufficient |
| Demand Tariff | Negotiate tariff band based on committed demand (≤ 150 kW grid peak target) |

---

## 7. Energy Cost Model

| Scenario | Grid Import (kWh/day) | Grid Cost (₦/kWh × 80) | Daily Grid Cost (₦) | Annual Grid Cost (₦M) |
|----------|----------------------|------------------------|--------------------|-----------------------|
| No Solar/BESS (baseline) | 3,500 | 80 | 280,000 | 102M |
| With Solar + BESS (target) | 700 (20% of demand) | 80 | 56,000 | 20M |
| **Saving (annual)** | | | | **₦82M/year** |

> **Solar Payback Contribution:** Energy savings of ₦82M/year contribute directly to the solar + BESS CapEx payback of ~₦1.14B, giving a **5-year energy cost payback** on the energy system investment alone.

---

## 8. Phase 2 & 3 Energy Upgrades

| Upgrade | Phase | Expected Benefit |
|---------|-------|-----------------|
| Roof cleaning robot for soiling loss reduction | Phase 2 | +3% generation recovery |
| BESS capacity expansion to 1,200 kWh | Phase 2 | Extended autonomy for night SDA lights-out |
| EV charging infrastructure (factory fleet) | Phase 2 | Replace diesel forklifts fully; reduce diesel cost |
| ISO 50001 energy management certification | Phase 2 | Group standard; benchmarking |
| Green tariff agreement / RECs | Phase 3 | Supporting Scope 2 net-zero reporting |

---

*For BESS digital twin monitoring, refer to [digital-twin.md](./digital-twin.md).*
*For energy CapEx details, refer to [capex-opex.md](./capex-opex.md).*
