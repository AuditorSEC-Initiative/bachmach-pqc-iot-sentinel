# Bachmach PQC IoT Sentinel — Financing & Investment Memo

> **Date:** March 2026 · **Location:** Bakhmach, Chernihiv Oblast, Ukraine · **TRL:** 3–4

---

## Executive Summary

Bachmach PQC IoT Sentinel is a post-quantum-hardened IoT monitoring platform designed for Bakhmach Business Hub and the broader Chernihiv Oblast infrastructure corridor. It delivers real-time encrypted telemetry for green energy assets (solar, wind, biomass), civic infrastructure sensors, and defence-adjacent monitoring — all secured with NIST FIPS 203/204 post-quantum cryptography running on low-cost embedded hardware (ESP32-S3, RP2040).

**Funding ask:** €60,000 (seed phase) | **Target programs:** MaJoR FSTP, BRAVE1 Tier-2, EDF COPILOT

---

## Problem

| Issue | Impact |
|-------|--------|
| Critical infrastructure in Chernihiv Oblast lacks tamper-proof monitoring | Vulnerable to physical and cyber sabotage |
| Classical crypto (RSA/ECC) vulnerable to quantum attacks within 5–10 years | Long-lived infrastructure needs quantum-resistant security today |
| Commercial IoT platforms (AWS IoT, Azure) have data sovereignty risks | Sensitive Ukrainian infrastructure data must remain on-premises |
| High cost of commercial embedded security modules | Blocks deployment at scale in budget-constrained regions |

---

## Solution

A **sovereign, open-source PQC IoT stack** built on:

- **Edge nodes:** ESP32-S3 / RP2040 with [liboqs](https://github.com/open-quantum-safe/liboqs) port
  - ML-KEM-768 (FIPS 203): key exchange, 312ms keygen on ESP32
  - ML-DSA-65 (FIPS 204): message signing, 287ms encapsulation on ESP32
- **Gateway:** NATS JetStream for resilient edge-cloud messaging
- **Policy engine:** OPA/Rego for on-device access control
- **Backend:** AuditorSEC K3s stack (Prometheus, Grafana, PostgreSQL)

### Key Differentiators

1. **Post-quantum by default** — only platform with NIST FIPS 203/204 on ESP32-class hardware.
2. **Open source** — no vendor lock-in; fully auditable.
3. **Ukraine-sovereign** — data stays on-premises; compatible with Diia.City infrastructure.
4. **Defence-adjacent** — applicable to BRAVE1 use cases (drone corridor telemetry, perimeter sensing).
5. **Low unit cost** — €15–30 per node vs €200+ for commercial alternatives.

---

## Market

| Segment | TAM | AuditorSEC Share |
|---------|-----|------------------|
| Critical infrastructure IoT security (EU) | €4.2B by 2027 | 0.1–0.5% |
| Defence-adjacent IoT (Ukraine + EU) | €800M (BRAVE1 programs) | 1–2% |
| Green energy monitoring (Chernihiv Oblast) | €12M (regional) | 10–20% |

---

## Traction

- ✔ **Lab benchmarks complete:** ML-KEM-768 and ML-DSA-65 validated on ESP32-S3 and RP2040.
- ✔ **liboqs cross-compilation** to ESP32 toolchain verified.
- ✔ **NATS JetStream** telemetry bridge prototype running.
- ✔ **Bakhmach Hub site** identified for field pilot Q2 2026.
- ✔ **MaJoR FSTP** letter of intent submitted (deadline: 25 March 2026).
- ✔ **BRAVE1 Tier-2** application in preparation.

---

## Use of Funds — €60,000 Seed Round

| Item | Amount | Timeline |
|------|--------|----------|
| Hardware: 50× ESP32-S3 nodes + sensors | €3,500 | Month 1 |
| Engineering: firmware + liboqs port hardening (2 devs × 3 months) | €24,000 | Months 1–3 |
| Field deployment: Bakhmach Hub pilot installation | €6,000 | Month 3 |
| Gateway infra: K3s edge server + NATS setup | €4,500 | Month 2 |
| Security audit: external PQC implementation review | €8,000 | Month 3 |
| Certification prep: FIPS / CE marking groundwork | €5,000 | Month 4 |
| Community + documentation (open source) | €4,000 | Ongoing |
| Contingency (10%) | €5,000 | — |
| **Total** | **€60,000** | **6 months** |

---

## Funding Programs

### 1. MaJoR FSTP (EDF Fast-Track)
- **Amount:** €25,000–€50,000 (cascade funding)
- **Deadline:** 25 March 2026 (⚠️ TODAY)
- **Fit:** Dual-use IoT security, Ukraine reconstruction, PQC hardening
- **Status:** LOI submitted; technical summary ready

### 2. BRAVE1 Tier-2 (Ukraine Defence Innovation)
- **Amount:** Up to €100,000
- **Deadline:** Rolling (Q2 2026 cohort)
- **Fit:** Perimeter sensing, drone corridor monitoring, PQC communications
- **Status:** Preparing application; benchmarks documented

### 3. EDF COPILOT / NEMS
- **Amount:** €2M+ (consortium)
- **Timeline:** 2026–2027
- **Fit:** NEMS sensor reliability, quantum-resistant embedded systems R&D
- **Status:** Partner identification in progress

### 4. Horizon Europe (TRL 4–6 instrument)
- **Amount:** €150,000–€500,000
- **Timeline:** 2027
- **Fit:** Green energy + IoT security + Ukraine reconstruction
- **Status:** Concept note drafted

---

## TRL Progression

| Phase | TRL | Milestone | Timeline |
|-------|-----|-----------|----------|
| Current | 3–4 | Lab demos: PQC on ESP32, NATS bridge | March 2026 |
| Seed | 4–5 | Bakhmach Hub field pilot, 10 nodes | Q2 2026 |
| Growth | 5–6 | 50-node deployment, Chernihiv Oblast | Q3 2026 |
| Scale | 7+ | Regional rollout, commercial product | 2027 |

---

## Team

| Role | Background |
|------|------------|
| Lead Architect | AuditorSEC / Diia.City resident; Audityzer + PQC stack |
| Embedded Engineer | ESP32/RP2040 firmware; liboqs port specialist |
| Security Engineer | NIST PQC, OPA policy-as-code |
| Partnerships | MaJoR / BRAVE1 / EU grant pipeline |

---

## Partnerships & Ecosystem

- **Bakhmach Business Hub** — deployment site partner
- **AuditorSEC Initiative** — parent stack (K3s, NATS, Grafana, LLM-Bridge)
- **Open Quantum Safe (liboqs)** — upstream PQC library
- **Diia.City** — regulatory framework and digital resident status
- **BRAVE1** — defence innovation accelerator

---

## Contact

- **Email:** romanchaa997@auditorsec.com
- **GitHub:** https://github.com/AuditorSEC-Initiative/bachmach-pqc-iot-sentinel
- **Telegram:** @audityzerbot
- **Location:** Bakhmach, Chernihiv Oblast, Ukraine (Diia.City resident)

---

*This financing memo is published under [MIT License](../../LICENSE). For a full technical brief or investor deck, contact the team directly.*
