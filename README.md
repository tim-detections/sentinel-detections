# Microsoft Sentinel Detections (Detection as Code)

**Author:** Tim A.  
**Role:** Cybersecurity Engineer – Microsoft Sentinel & KQL  
**Focus:** Detection Engineering, Threat Hunting, SOC Enablement  

---

### Overview

This repository contains **Microsoft Sentinel analytic detection rules** developed using a **detection-as-code** approach.

The goal of this lab is to demonstrate:
- Real-world detection engineering practices
- Well-structured and readable KQL
- Version-controlled detection tuning
- Security-relevant logic aligned to attacker behavior

All detections are written, tested, and iteratively improved as they would be in a production SOC environment.

---

## What You’ll Find in This Repository

- 📌 **KQL-based Sentinel analytics rules**
- 🧪 Iterative tuning and false-positive reduction
- 🧱 Versioned detections (`v1.0.0`, `v1.1.0`, etc.)
- 📝 Clear documentation explaining detection intent
- 🎯 Focus on signal quality over alert volume

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

