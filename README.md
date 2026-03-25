# Bachmach PQC IoT Sentinel

> **Post-quantum green energy + civic IoT for Bakhmach Business Hub, Chernihiv oblast, Ukraine**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![TRL](https://img.shields.io/badge/TRL-3--4-blue)](#roadmap)
[![BRAVE1](https://img.shields.io/badge/BRAVE1-Tier2-red)](#grants)

---

## Overview

Bachmach PQC IoT Sentinel is a post-quantum hardened edge IoT platform designed for:
- Green-energy and critical-infrastructure telemetry in Bakhmach Hub.
- Defence-adjacent resilience monitoring (BRAVE1 Tier2 / MaJoR EDF programme).
- Civic IoT data integrity for Chernihiv oblast recovery and reconstruction.

Built on top of the **AuditorSEC** security stack with NATS JetStream as the messaging backbone.

---

## Features

- NEMS / ESP32 / RP2040 sensor nodes with ML-KEM-768 and ML-DSA-65 (NIST FIPS 203/204).
- MQTT to NATS JetStream bridge with OPA policy-as-code at the edge.
- Causal-AI anomaly detection running on constrained hardware.
- NEMS stiction mitigation: surface treatment protocols for reliable MEMS operation.
- Zephyr RTOS and MicroPython firmware support.
- End-to-end encrypted telemetry: keygen 312ms, encaps 287ms on ESP32.

---

## Architecture

```
Edge Layer
  ESP32 / RP2040  |  Zephyr RTOS / MicroPython  |  liboqs PQC port
        |
Gateway Layer
  MQTT broker  ->  NATS JetStream  |  OPA policy engine
        |
Core Layer (AuditorSEC Stack)
  PostgreSQL  |  Prometheus / Grafana  |  ArgoCD / K3s
```

---

## Hardware BOM (Bill of Materials)

| Component | Model | Role |
|-----------|-------|------|
| MCU board | ESP32-S3 DevKit | Edge compute + ML-KEM |
| Alt MCU | RP2040 (Raspberry Pi Pico W) | Low-power telemetry |
| Sensor | MAX30102 | Bio/environmental sensing |
| Radio | nRF52840 dongle | BLE mesh backbone |
| Gateway | Raspberry Pi 4 | MQTT/NATS bridge |

---

## Quick Start

### Flash PQC firmware (RP2040 / MicroPython)

```python
# pqcedgenode.py
from liboqs import KeyEncapsulation

kem = KeyEncapsulation('ML-KEM-768')
public_key = kem.generate_keypair()

# Encrypt and publish telemetry to NATS
import mqtt_client
mqtt_client.publish('bachmach/telemetry', kem.encapsulate(public_key))
```

### Connect to test NATS instance

```bash
docker run -p 4222:4222 nats:latest
nats sub bachmach.telemetry
```

---

## PQC Benchmarks (ESP32-S3)

| Operation | Time |
|-----------|------|
| ML-KEM-768 keygen | 312 ms |
| ML-KEM-768 encaps | 287 ms |
| ML-DSA-65 sign | 418 ms |
| ML-DSA-65 verify | 195 ms |

---

## Use Cases

- Green-energy resilience monitoring (solar panels, micro-grids, generators).
- Water and heat infrastructure telemetry for Bakhmach Hub.
- Civic integrity sensors: tamper-evident environmental data for reconstruction grants.
- Defence-adjacent BRAVE1 Tier2 pilot: field telemetry with PQC comms.
- MaJoR EDF NEMS-COPILOT: MEMS/NEMS reliability in harsh environments.

---

## Roadmap

- [x] NEMS stiction mitigation protocols (lab, TRL 3).
- [x] ESP32 ML-KEM/ML-DSA port and benchmark.
- [ ] Q2 2026: Field tests in Bakhmach Hub (TRL 4).
- [ ] Q3 2026: Whitepaper + first external pilots.
- [ ] Q4 2026: Integration with AuditorSEC Grafana monitoring.
- [ ] 2027: MaJoR EDF cascade funded deployment.

---

## Grants & Programmes

- **BRAVE1 Tier2**: Defence-adjacent IoT security.
- **MaJoR FSTP NEMS-COPILOT**: MEMS/NEMS reliability (25 Mar 2026 deadline).
- **EDF MaJoR**: European Defence Fund IoT resilience.
- **Bachmach Hub**: Local green-energy and civic reconstruction.

---

## Financing

Target: EUR 60,000 via EDF cascade + BRAVE1 Tier2.
- Phase 1 (EUR 20k): Lab PoC, firmware, liboqs port.
- Phase 2 (EUR 25k): Field deployment, Bakhmach Hub installation.
- Phase 3 (EUR 15k): Whitepaper, grant reporting, dissemination.

---

## Contact

- Email: romanchaa997@auditorsec.com
- Telegram: [@audityzerbot](https://t.me/audityzerbot)
- Notion workspace: [AuditorSEC Hub](https://www.notion.so/auditorsec)
- Location: Bakhmach, Chernihivska oblast, Ukraine

---

## License

MIT License. See [LICENSE](LICENSE).
