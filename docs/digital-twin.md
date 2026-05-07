# Kitchen Electronics Factory — Digital Twin Architecture

> **Group Platform Reference:** [Coo-Kah-Doks — platform/digital-twin-platform-architecture.md](https://github.com/oumar-code/Coo-Kah-Doks/blob/main/platform/digital-twin-platform-architecture.md)
> **Platform decision:** Hybrid Coo-Cah DT Engine (InfluxDB + FastAPI + Grafana + MQTT + OPC-UA connectors), with factory edge node + Rwanda cloud hub.
>
> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Location:** Agbara Industrial Estate, Lagos State | **Phase:** Phase 1
> **Document Version:** 1.0 | **Owner:** Smart Factory Core Team / Coo-Cah AI Platform Team

---

## 1. Overview

The Kitchen Electronics Factory Digital Twin (DT) is a live synchronised virtual model
of the physical factory, enabling real-time production visibility, predictive
maintenance, energy optimisation, and simulation of process changes before physical
implementation.

The DT is an instance of the **Coo-Cah AI-Connected Factory Platform**
(group-standard), aligned to the master DT platform document in Coo-Kah-Doks
([platform/digital-twin-platform-architecture.md](https://github.com/oumar-code/Coo-Kah-Doks/blob/main/platform/digital-twin-platform-architecture.md))
and hosted as a cloud service with a factory-edge node providing resilience against
internet outages. The same DT engine is deployed at all Coo-Cah factories to enable
group-wide benchmarking.

| Attribute | Value |
|-----------|-------|
| Platform | Coo-Cah Digital Twin Engine (group-standard platform) |
| Deployment Model | Cloud (group visibility) + factory edge node (local resilience) |
| MES Integration | REST API + event stream; OT/DT write-back restricted by group architecture |
| Telemetry Rate | Key machines: 1-second; energy meters: 1-minute; environment: 5-minute |
| Assets in Phase 1 DT | SMT line, Refrigerator assembly, Gas charging zone, Energy systems |
| Phase 2 Additions | Robot cells, AI QC camera feeds, all assembly line machines |
| 3D Model | Factory building + production zone modelled in Unity/Unreal Engine |

---

## 2. Digital Twin Asset Registry — Phase 1

### 2.1 SMT PCB Line Assets

| DT Asset ID | Physical Asset | Key Sensors | DT Use Case |
|-------------|----------------|-------------|-------------|
| DT-SMT-01 | Solder paste screen printer (DEK) | Paste volume sensor, squeegee pressure, stencil ID | SPI prediction; paste life model |
| DT-SMT-02 | JUKI FX-3R P&P (High Speed) | Feeder status, CPH, vision error rate | Feeder depleted alert; component planning |
| DT-SMT-03 | JUKI RX-7 P&P (Flexible) | Feeder status, CPH, error events | |
| DT-SMT-04 | Heller reflow oven | Zone temperatures (8 zones), belt speed, N₂ consumption | Profile drift detection; N₂ cost model |
| DT-SMT-05 | Koh Young 3D AOI | Defect counts by category, throughput, fail serial | Yield trend; SPC trigger |
| DT-SMT-06 | SMT Line — Overall | Takt, WIP count, OEE | Line-level simulation |

### 2.2 Refrigerator Assembly Assets

| DT Asset ID | Physical Asset | Key Sensors | DT Use Case |
|-------------|----------------|-------------|-------------|
| DT-REF-01 | PU foam injection machine | Polyol/isocyanate ratio, injection pressure, cure temp, cycle time | Foam density quality prediction; preventive maintenance |
| DT-REF-02 | Overhead chain conveyor | Position of carriers (RFID), speed, tension, motor current | Takt alignment; maintenance prediction |
| DT-REF-03 | Gas charging station (×2) | Charge weight, cylinder pressure, charge rate, cycle count | Gas consumption model; leak test rate prediction |
| DT-REF-04 | Vacuum pump (×2) | Final vacuum level (microns), pump-down time, exhaust temp | Pump service life model |
| DT-REF-05 | Performance test station | Unit serial, compressor on-time, final temp, power draw | Energy efficiency compliance; yield quality model |
| DT-REF-06 | Refrigerator Line — Overall | Takt, WIP throughput, OEE, R600a consumption | Line planning; capacity simulation |

### 2.3 Energy System Assets

| DT Asset ID | Physical Asset | Key Sensors | DT Use Case |
|-------------|----------------|-------------|-------------|
| DT-EN-01 | Solar PV Array (700 kWp) | Generation (kW), irradiance, panel temperature | Daily generation forecast; soiling loss model |
| DT-EN-02 | BESS (800 kWh LFP) | SoC (%), charge/discharge rate, cell temperatures, cycle count | Dispatch optimisation; SoH (State of Health) model |
| DT-EN-03 | Grid Connection | Import/export (kW), grid voltage, frequency | Grid cost model; self-sufficiency KPI |
| DT-EN-04 | Diesel Generator | Runtime hours, load (kW), fuel level, run hours to service | Predictive service scheduling; fuel cost model |
| DT-EN-05 | Compressed Air System | Pressure, flow, compressor run hours, leak rate | Air leak alert; efficiency model |
| DT-EN-06 | Factory-wide EMS | Total consumption, per-zone sub-meter, energy intensity per unit | Energy KPI dashboard; cost-per-unit model |

---

## 3. DT Architecture

```
┌─────────────────────────────────────────────────────────────────────────┐
│                     CLOUD — Coo-Cah DT Engine                           │
│                                                                         │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  ┌────────────┐  │
│  │ Factory      │  │ AI Models    │  │ 3D Visual    │  │ Group      │  │
│  │ Virtual Model│  │ Pred Maint.  │  │ Dashboard    │  │ Benchmarks │  │
│  │ (Unity/UE5)  │  │ Energy Opt.  │  │ (Web + App)  │  │            │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  └────────────┘  │
└────────────────────────────┬────────────────────────────────────────────┘
                             │ HTTPS REST + Event Stream (MQTT/WebSocket)
                             │
┌────────────────────────────▼────────────────────────────────────────────┐
│                    FACTORY EDGE NODE (Agbara Site)                      │
│                  Coo-Cah DT Edge Server (local resilience)              │
│                                                                         │
│  ┌───────────────┐  ┌──────────────┐  ┌───────────────┐                │
│  │ MES Interface │  │ OPC-UA       │  │ IoT Gateway   │                │
│  │ (Opcenter API)│  │ Aggregator   │  │ (MQTT broker) │                │
│  └───────┬───────┘  └──────┬───────┘  └───────┬───────┘                │
└──────────┼─────────────────┼──────────────────┼─────────────────────── ┘
           │                 │                  │
    ┌──────▼──────┐  ┌──────▼──────┐  ┌────────▼────────┐
    │ MES Panel   │  │ SMT Machines│  │ Gas Ctrl PLCs   │
    │ PCs (HMIs)  │  │ Reflow Oven │  │ Energy Meters   │
    │ Workstations│  │ AOI System  │  │ BESS BMS        │
    └─────────────┘  └─────────────┘  └─────────────────┘
```

**Gate 1 note:** DT edge/cloud is read-only toward OT in Phase 1 and Phase 2. Any future write-back requires Phase 3 approval and safety review.

---

## 4. AI Models Deployed in the Digital Twin

### 4.1 Phase 1 AI Models

| Model ID | Model Name | Input Data | Output / Action | Phase |
|----------|-----------|-----------|----------------|-------|
| AI-DT-01 | Energy Anomaly Detector | Per-zone energy sub-meter; production takt | Alert on anomalous energy per unit; notify EMS | Phase 1 |
| AI-DT-02 | R600a Consumption Predictor | Daily gas charge weights; model mix; cylinder levels | 7-day gas consumption forecast; cylinder reorder trigger | Phase 1 |
| AI-DT-03 | OEE Trend Analyser | MES OEE stream per zone | Weekly OEE trend; early detection of availability decline | Phase 1 |
| AI-DT-04 | Solar Generation Forecast | Weather API; historical irradiance; panel SoH | Daily generation forecast; BESS dispatch schedule | Phase 1 |
| AI-DT-05 | Reflow Oven Profile Monitor | 8-zone temperatures; board type; production throughput | Profile drift alert; solder quality risk score | Phase 1 |

### 4.2 Phase 2 AI Models (Planned)

| Model ID | Model Name | Input Data | Output / Action | Phase |
|----------|-----------|-----------|----------------|-------|
| AI-DT-06 | PU Foam Quality Predictor | Foam injection ratio, pressure, cure temp, ambient temp | Foam density quality score; reject risk flag | Phase 2 |
| AI-DT-07 | Compressor Vibration Analyser (PM) | Accelerometer data on compressor test rigs | MTBF prediction; maintenance scheduling | Phase 2 |
| AI-DT-08 | Cabinet Dimensional Inspector (AI Vision) | Camera feeds from AI QC station | Defect type + location; auto pass/fail to MES | Phase 2 |
| AI-DT-09 | Supply Chain Demand Forecaster | Sales data; MES consumption; lead time API | Compressor/magnetron reorder alerts; safety stock optimisation | Phase 2 |

---

## 5. Digital Twin Use Cases — Phase 1

### 5.1 Use Case: R600a Gas Zone Monitoring

The gas charging zone is the highest-risk zone in the factory. The DT continuously:

1. Monitors gas sensor readings from 12 electrochemical detectors
2. Models R600a concentration in air across the zone using computational fluid dynamics (simplified)
3. Tracks daily consumption vs. production orders
4. Alerts EHS officer if consumption per unit deviates from spec by > 5 grams
5. Generates NESREA monthly compliance report automatically

### 5.2 Use Case: Energy Self-Sufficiency Management

The BESS dispatch algorithm uses DT AI-DT-04 (solar forecast) + production schedule to:

1. Forecast solar generation for the next 24 hours
2. Plan BESS charge/discharge cycles to avoid grid import during peak production
3. Alert factory manager if grid dependency > 25% in any 2-hour window
4. Generate daily and monthly solar self-sufficiency KPI report

### 5.3 Use Case: Refrigerator Line Takt Simulation

Before a model changeover (e.g., switching from single-door to 2-door line), production engineers can:

1. Load the new production order into the DT model
2. Simulate the takt time and expected throughput
3. Identify bottleneck stations (typically foam injection cure time)
4. Optimise changeover sequence before physical execution

---

## 6. DT Data Governance

| Parameter | Policy |
|-----------|--------|
| Data Retention | Production telemetry: 2 years rolling (MES); quality test data: 7 years |
| Encryption | All DT telemetry encrypted in transit (TLS 1.3) and at rest (AES-256) |
| Access Control | Role-based: Line technicians read-only; engineers read/write; admins full |
| Data Sovereignty | All data stored in-country (Nigeria-hosted edge) + EU cloud (GDPR-compliant) |
| Disaster Recovery | Edge node can operate standalone ≥ 72 hours without cloud connectivity |

---

*For MES integration enabling the DT data feed, refer to [mes-integration.md](./mes-integration.md).*
*For energy system configuration referenced in DT models, refer to [energy-profile.md](./energy-profile.md).*
*For the authoritative group DT platform decision, refer to [Coo-Kah-Doks — platform/digital-twin-platform-architecture.md](https://github.com/oumar-code/Coo-Kah-Doks/blob/main/platform/digital-twin-platform-architecture.md).*
