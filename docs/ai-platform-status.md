# Kitchen Electronics Factory — AI Platform Status

> **Project Coo-Cah | AI-Powered Manufacturing Ecosystem**
> **Factory:** Coo-Cah Kitchen Electronics Factory | **Factory ID:** CCK-EL-KIT
> **Document Version:** 1.0 | **Owner:** AI Platform Team / Smart Factory Core Team
> **Platform:** Coo-Cah AI-Connected Factory Platform (Group Standard)
> **Status:** Stub endpoints active — Production go-live pending hardware commissioning

---

## 1. Overview

The Kitchen Electronics Factory AI Platform is an instance of the **Coo-Cah AI-Connected Factory Platform**, the group-standard AI services layer deployed at all Coo-Cah factories. The platform provides real-time manufacturing intelligence by consuming telemetry from the MES, IoT sensors, and energy systems, and returning predictions, anomaly alerts, and optimisation schedules.

This document captures the current readiness state of each AI service, its endpoint specification, and the go-live criteria and blockers.

| Attribute | Value |
|-----------|-------|
| Platform | Coo-Cah AI-Connected Factory Platform (group standard) |
| Deployment Architecture | Cloud inference (group) + factory edge GPU node (local resilience) |
| API Framework | FastAPI (Python 3.11); OpenAPI 3.0 specification |
| Telemetry Ingest | MQTT → InfluxDB → AI Platform (event-driven) |
| MES Integration | REST API (`/api/v1/ai/*` — see [mes-integration.md](./mes-integration.md)) |
| Authentication | OAuth 2.0 (client credentials flow); JWT bearer tokens |
| TLS | TLS 1.3 on all endpoints; staging uses self-signed certs; production requires CA-signed |
| Staging Base URL | `https://ai-staging.cck-el-kit.internal/api/v1/` |
| Production Base URL | `https://ai.cck-el-kit.coocah.ng/api/v1/` *(not yet live)* |

---

## 2. Phase 1 AI Services — Status Dashboard

| Service ID | Service Name | Endpoint | Staging Status | Production Status | Blocker |
|------------|-------------|---------|---------------|-----------------|---------|
| AI-SVC-01 | Energy Anomaly Detector | `/ai/energy-anomaly` | ✅ Stub live | ⏳ Pending | GPU node commissioning |
| AI-SVC-02 | R600a Consumption Predictor | `/ai/r600a-forecast` | ✅ Stub live | ⏳ Pending | GPU node commissioning |
| AI-SVC-03 | OEE Trend Analyser | `/ai/oee-trend` | ✅ Stub live | ⏳ Pending | MES live data feed |
| AI-SVC-04 | Solar Generation Forecast | `/ai/solar-forecast` | ✅ Stub live | ⏳ Pending | Solar array energised |
| AI-SVC-05 | Reflow Oven Profile Monitor | `/ai/reflow-profile` | ✅ Stub live | ⏳ Pending | SMT line commissioned |

**Legend:**
- ✅ Stub live — endpoint returns mock/simulated data; schema validated
- ⏳ Pending — live data not yet available; blocked on physical infrastructure
- ❌ Blocked — prerequisite not met; endpoint not deployed

---

## 3. Phase 1 AI Service Specifications

### AI-SVC-01 — Energy Anomaly Detector

**Purpose:** Detects anomalous energy consumption per production zone by comparing real-time sub-meter readings against expected energy per unit of production output.

| Attribute | Value |
|-----------|-------|
| Model type | Isolation Forest (unsupervised anomaly detection) |
| Input data | Per-zone energy sub-meter (kWh, 15-min intervals); MES production takt count per zone |
| Output | Anomaly score (0–1); alert if score > 0.75; zone ID; estimated excess energy (kWh) |
| Trigger | Event-driven — triggered on each 15-min energy meter read |
| Latency target | < 2 seconds from ingest to alert |
| Alert destination | MES `/api/v1/safety/alert` (EHS dashboard) + Grafana dashboard |

**API Specification:**

```
POST /ai/energy-anomaly
Content-Type: application/json
Authorization: Bearer {jwt_token}

Request:
{
  "zone_id": "Z4",
  "timestamp_utc": "2026-05-12T14:00:00Z",
  "energy_kwh_15min": 187.3,
  "units_produced_15min": 5,
  "shift_id": "SHIFT-A-2026-05-12"
}

Response (200 OK):
{
  "zone_id": "Z4",
  "anomaly_score": 0.42,
  "alert": false,
  "expected_kwh_per_unit": 18.0,
  "actual_kwh_per_unit": 37.5,
  "recommendation": null,
  "model_version": "v1.2.0"
}
```

**Staging status:** ✅ Mock response active; returns simulated anomaly scores.
**Production blocker:** Factory energy sub-meters must be commissioned and feeding InfluxDB via MES EMS module.

---

### AI-SVC-02 — R600a Consumption Predictor

**Purpose:** Forecasts R600a refrigerant consumption over the next 7 days based on production schedule, charge-weight history, and cylinder inventory. Triggers cylinder reorder when projected stock falls below 3 cylinders (factory safety stock trigger).

| Attribute | Value |
|-----------|-------|
| Model type | Time-series forecasting (Prophet / ARIMA ensemble) |
| Input data | MES R600a gas module daily consumption by model; production order schedule; cylinder inventory |
| Output | 7-day gas consumption forecast (kg/day by fridge model); reorder alert flag; days-to-reorder |
| Trigger | Scheduled — daily at 06:00 WAT; on-demand via API |
| Alert destination | Supply Chain Dashboard; EHS Officer dashboard |

**API Specification:**

```
POST /ai/r600a-forecast
Content-Type: application/json
Authorization: Bearer {jwt_token}

Request:
{
  "request_date": "2026-05-12",
  "production_plan": [
    {"model": "CCK-REF-2D-FF", "units_per_day": 160, "days": 7},
    {"model": "CCK-REF-1D-DC", "units_per_day": 140, "days": 7}
  ],
  "current_cylinder_inventory_kg": 120.0
}

Response (200 OK):
{
  "forecast_date": "2026-05-12",
  "daily_forecast_kg": [42.1, 42.1, 42.1, 42.1, 42.1, 21.0, 21.0],
  "7day_total_kg": 252.6,
  "reorder_alert": false,
  "projected_days_to_reorder": 4.8,
  "reorder_recommended_date": "2026-05-17",
  "model_version": "v1.0.1"
}
```

**Staging status:** ✅ Mock response active; static example payload returned.
**Production blocker:** R600a MES gas module must be live with ≥ 30 days of real consumption data for model training.

---

### AI-SVC-03 — OEE Trend Analyser

**Purpose:** Analyses rolling OEE trends per production line and detects early-warning signs of availability decline before they impact production targets.

| Attribute | Value |
|-----------|-------|
| Model type | Statistical process control (CUSUM / EWMA) + trend regression |
| Input data | MES OEE stream per zone (real-time); downtime codes; shift patterns |
| Output | OEE trend direction (improving / stable / declining); predicted OEE for next 5 shifts; top 3 contributing downtime codes |
| Trigger | End of each production shift (event from MES); on-demand |

**API Specification:**

```
GET /ai/oee-trend?zone_id=Z4&lookback_shifts=20
Authorization: Bearer {jwt_token}

Response (200 OK):
{
  "zone_id": "Z4",
  "zone_name": "Refrigerator Assembly",
  "lookback_shifts": 20,
  "current_oee": 0.71,
  "trend": "stable",
  "oee_prediction_next_5_shifts": [0.70, 0.71, 0.72, 0.71, 0.73],
  "target_oee": 0.68,
  "top_downtime_codes": [
    {"code": "DT-FOAM-01", "description": "PU foam injection cycle overtime", "minutes_last_20_shifts": 145},
    {"code": "DT-CONV-02", "description": "Overhead conveyor tension alarm", "minutes_last_20_shifts": 82},
    {"code": "DT-CHGOVER", "description": "Model changeover — unplanned extension", "minutes_last_20_shifts": 60}
  ],
  "model_version": "v1.1.0"
}
```

**Staging status:** ✅ Stub returns static payload.
**Production blocker:** MES Siemens Opcenter must be live and OEE stream API active.

---

### AI-SVC-04 — Solar Generation Forecast

**Purpose:** Forecasts the factory's solar PV generation for the next 24 hours using weather API data and historical panel performance. Output is used by the BESS Energy Management System to plan charge/discharge cycles.

| Attribute | Value |
|-----------|-------|
| Model type | Gradient boosting (XGBoost) — weather + irradiance → generation |
| Input data | Open-Meteo or similar weather API (Lagos irradiance forecast); historical PV generation (InfluxDB); panel SoH estimate |
| Output | Hourly solar generation forecast (kW) for next 24 hours; self-sufficiency confidence score; BESS dispatch recommendation |
| Trigger | Daily at 04:30 WAT; re-triggered on weather alert (cloud-cover > 70%) |

**API Specification:**

```
GET /ai/solar-forecast?forecast_date=2026-05-13&site=CCK-EL-KIT
Authorization: Bearer {jwt_token}

Response (200 OK):
{
  "site": "CCK-EL-KIT",
  "forecast_date": "2026-05-13",
  "forecast_hours": [
    {"hour_utc": "05:00", "generation_kw": 0.0, "irradiance_wm2": 0},
    {"hour_utc": "07:00", "generation_kw": 145.2, "irradiance_wm2": 210},
    {"hour_utc": "09:00", "generation_kw": 420.5, "irradiance_wm2": 610},
    {"hour_utc": "11:00", "generation_kw": 580.0, "irradiance_wm2": 840},
    {"hour_utc": "13:00", "generation_kw": 610.0, "irradiance_wm2": 885},
    {"hour_utc": "15:00", "generation_kw": 490.3, "irradiance_wm2": 710},
    {"hour_utc": "17:00", "generation_kw": 180.1, "irradiance_wm2": 260},
    {"hour_utc": "19:00", "generation_kw": 0.0, "irradiance_wm2": 0}
  ],
  "daily_total_forecast_kwh": 3420,
  "self_sufficiency_confidence": 0.84,
  "bess_dispatch_recommendation": "Charge BESS 08:00-11:00; discharge 16:00-20:00",
  "model_version": "v1.0.3"
}
```

**Staging status:** ✅ Stub returns mock 24-hour profile.
**Production blocker:** Solar PV array and BESS must be commissioned; weather API subscription active.

---

### AI-SVC-05 — Reflow Oven Profile Monitor

**Purpose:** Monitors the Heller reflow oven's 8 temperature zones in real time, detects profile drift before solder quality is impacted, and generates a solder quality risk score.

| Attribute | Value |
|-----------|-------|
| Model type | Multivariate control chart (Hotelling T²) on 8-zone temperature vector |
| Input data | OPC-UA temperature readings from all 8 reflow zones (1-second); belt speed; board type from MES |
| Output | Profile conformance score (0–1); alert if any zone drifts > ±3°C from spec; risk score for solder quality |
| Trigger | Continuous — event-driven on each OPC-UA reading |

**API Specification:**

```
POST /ai/reflow-profile
Content-Type: application/json
Authorization: Bearer {jwt_token}

Request:
{
  "timestamp_utc": "2026-05-12T08:15:00Z",
  "board_type": "CCK-PCB-FRIDGE-V1",
  "belt_speed_m_min": 0.65,
  "zone_temps_c": [155, 165, 175, 195, 215, 230, 210, 185]
}

Response (200 OK):
{
  "conformance_score": 0.97,
  "alert": false,
  "drifting_zones": [],
  "solder_quality_risk": "LOW",
  "recommendation": null,
  "model_version": "v1.0.0"
}
```

**Staging status:** ✅ Stub active; returns static conformance score.
**Production blocker:** SMT line (Heller reflow oven) must be commissioned with OPC-UA connectivity.

---

## 4. Phase 2 AI Services (Planned — 2028–2029)

| Service ID | Service Name | Endpoint | Phase | Status |
|------------|-------------|---------|-------|--------|
| AI-SVC-06 | PU Foam Quality Predictor | `/ai/foam-quality` | 2 | 📋 Planned |
| AI-SVC-07 | Compressor Vibration Analyser (PdM) | `/ai/compressor-pdm` | 2 | 📋 Planned |
| AI-SVC-08 | Cabinet Dimensional Inspector (AI Vision) | `/ai/cabinet-vision` | 2 | 📋 Planned |
| AI-SVC-09 | Supply Chain Demand Forecaster | `/ai/demand-forecast` | 2 | 📋 Planned |

---

## 5. Infrastructure Requirements

### 5.1 Staging Environment (Current)

| Component | Specification | Status |
|-----------|--------------|--------|
| Cloud inference node | Group Coo-Cah AI cluster (Rwanda hub) | ✅ Shared — available |
| FastAPI application containers | Docker; 4 vCPU / 16 GB RAM per service | ✅ Deployed (staging) |
| InfluxDB (staging) | InfluxDB OSS 2.7; 500 GB storage | ✅ Deployed (staging) |
| MQTT broker (staging) | HiveMQ Community; staging topics | ✅ Deployed (staging) |
| TLS certificates (staging) | Self-signed (staging only) | ✅ Active |

### 5.2 Production Environment (Pending Commissioning)

| Component | Specification | Status | Blocker |
|-----------|--------------|--------|---------|
| On-site GPU inference node | NVIDIA RTX 4090 or A10G; 64 GB RAM; NVMe | ⏳ Pending | Hardware procurement + data centre room (Z16) |
| Production InfluxDB | InfluxDB Enterprise; 2 TB NVMe; replication | ⏳ Pending | Server room (Z16) commissioned |
| CA-signed TLS certificates | Issued by Coo-Cah internal CA | ⏳ Pending | PKI infrastructure setup |
| Production MQTT broker | HiveMQ Enterprise; clustering | ⏳ Pending | Server room (Z16) |
| Load balancer | HAProxy or NGINX Plus | ⏳ Pending | Server room (Z16) |

---

## 6. Go-Live Criteria (Production)

All of the following must be met before the AI Platform is promoted to production status:

| Criterion | Verification Method |
|-----------|-------------------|
| GPU inference node physically commissioned in Z16 | Facilities acceptance certificate |
| CA-signed TLS certificates issued and installed | Certificate inspection (`openssl verify`) |
| All Phase 1 AI services passing health-check endpoints | `GET /health` → HTTP 200 for all 5 services |
| MES live data feed validated (OEE stream active ≥ 24h) | InfluxDB query showing live data |
| Solar PV generation data feeding AI-SVC-04 in real time | InfluxDB solar generation metric present |
| Pentest Phase 1 findings remediated (Critical + High) | Digital Encode closing certificate |
| Load test passed (≥ 500 concurrent requests, p99 < 500ms) | Load test report (k6 or Locust) |
| Disaster recovery test passed (edge node standalone ≥ 72h) | DR drill report |

---

## 7. Security Controls

| Control | Implementation |
|---------|---------------|
| Authentication | OAuth 2.0 client credentials; per-service API keys for MES |
| Authorisation | Role-based: MES read-only; Smart Factory engineer read/write; Admin full |
| Data in transit | TLS 1.3 mandatory on all endpoints |
| Data at rest | AES-256 on InfluxDB storage volumes |
| Network | AI platform VLAN isolated from shopfloor OT network; no write-back to OT |
| Audit logging | All API calls logged with JWT subject, IP, timestamp, response code |
| Vulnerability scanning | Monthly automated scan via Coo-Cah InfoSec tooling |
| Pentest | Annually; Digital Encode Limited (see [pentest-scoping.md](./pentest-scoping.md)) |

---

*For MES API endpoints that feed the AI platform, refer to [docs/mes-integration.md](./mes-integration.md).*
*For digital twin models that consume AI platform outputs, refer to [docs/digital-twin.md](./digital-twin.md).*
*For pentest engagement details, refer to [docs/pentest-scoping.md](./pentest-scoping.md).*
