# Microsoft Sentinel Detections (Detection as Code)

**Author:** Tim A.  
**Role:** Cybersecurity Engineer – (Microsoft Sentinel, KQL & Microsoft XDR)

**Specialization:** Detection Engineering, Threat Hunting, SOC Enablement  

---

### Overview

This repository contains Microsoft Sentinel analytic detection rules developed using a **detection-as-code** approach and organised by security domain and attack chain.
The purpose of this repository is to demonstrate how detection engineering is performed in a production SOC environment, with an emphasis on maintainability, signal quality, and attacker-centric detection logic rather than alert volume.

All detections are written, tested, and iteratively refined as they would be in a real-world Microsoft Sentinel deployment.

---

## **What This Repository Demonstrates:**
Real-world detection engineering practices aligned to modern cloud threats
Structured, readable, and maintainable KQL
Version-controlled detection development and tuning
Detections mapped to attacker behaviour and attack paths
Practical SOC-ready analytics designed to reduce noise and increase confidence

---

## Detection Engineering Philosophy

This lab follows a few core principles:

- **Behavior > Indicators**  
  Focus on attacker techniques, not just IOCs.

- **Readable KQL matters**  
  Queries should be understandable by other analysts.

- **Version everything**  
  Every tuning change is tracked and documented.

- **SOC-friendly detections**  
  Alerts should be actionable, not noisy.

---


Repository Structure:
Detections are organised by security domain and, where applicable, attack-chain alignment to support scalability and iterative improvement:
**Identity** – Entra ID sign-ins, authentication abuse, MFA and account compromise
**Cloud** – Azure, Kubernetes, and workload-level attack paths
**Endpoint** – Host-based attacker behaviour and execution patterns
**Data Protection** – Exfiltration, sensitive data access, and insider risk
**Cross-Domain** – Correlated detections spanning identity, cloud, endpoint, and data

Each detection family supports versioning (v1 → v2 → v3) to reflect ongoing tuning and maturity.

## Repository Intended Structure (still in progress)

```text
sentinel-detections/
├── README.md                     # Executive overview (what, why, impact)
├── CONTRIBUTING.md               # Optional: how detections are structured
├── detections/
│   ├── identity/
│   │   ├── impossible-travel/
│   │   │   ├── README.md
│   │   │   ├── impossible_travel_v1_distance_speed.yaml
│   │   │   └── impossible_travel_v2_new_device_context.yaml
│   │   ├── suspicious-signin-email/
│   │   │   ├── README.md
│   │   │   └── suspicious_signin_high_risk_email_activity.yaml
│   │   ├── mfa-abuse/             # future
│   │   ├── privileged-access/     # future (PIM, admin abuse)
│   │
│   ├── endpoint/
│   │   ├── persistence/
│   │   ├── credential-access/
│   │   └── defense-evasion/
│   │
│   ├── cloud/
│   │   ├── kubernetes/
│   │   │   ├── README.md
│   │   │   └── aks_exec_followed_by_sensitive_blob_access.yaml
│   │   ├── azure-resource-abuse/
│   │   └── service-principal/
│   │
│   ├── data-protection/
│   │   ├── exfiltration/
│   │   ├── insider-threat/
│   │   └── label-abuse/
│   │
│   └── cross-domain/
│       ├── identity-to-cloud/
│       ├── endpoint-to-cloud/
│       └── identity-to-data/
│
└── utilities/
    ├── baseline-queries/
    ├── enrichment-functions/
    └── lookup-tables/

