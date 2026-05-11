# Microsoft Sentinel Detection Engineering Repository

**Author:** Tim A.  
**Role:** Cybersecurity Engineer | Microsoft Sentinel | Microsoft XDR | Cloud Security  
**Specialization:** Detection Engineering, Threat Hunting, SOC Engineering, Security Automation, and Cloud Threat Detection

---

# Overview

This repository contains a collection of Microsoft Sentinel analytic rules, KQL detections, threat hunting queries, and SOC-focused detection engineering workflows developed using a modern **Detection-as-Code (DaC)** methodology.

The repository is designed to reflect how mature enterprise SOC teams build, validate, tune, and operationalise detections within real-world Microsoft security environments.

The primary focus of this project is not alert volume, but the development of:

- High-confidence detections
- Behaviour-based analytics
- Attacker-centric detection logic
- Cross-domain threat correlation
- Scalable and maintainable KQL engineering
- SOC-operationally actionable detections

All detections are version-controlled, documented, tested, and iteratively refined to simulate production-grade detection engineering practices used in modern cloud and hybrid enterprise environments.

---

# Repository Objectives

This repository demonstrates practical and enterprise-aligned approaches to:

- Microsoft Sentinel Detection Engineering
- KQL-based analytic rule development
- Threat hunting and anomaly detection
- Detection tuning and false-positive reduction
- MITRE ATT&CK-aligned detection logic
- Cross-domain attack-path correlation
- SOC investigation enablement
- Detection validation and attack simulation
- Detection-as-Code CI/CD workflows

---

# What This Repository Demonstrates

- Real-world detection engineering practices aligned to modern cloud threats
- Structured, readable, and maintainable KQL development
- Version-controlled detection lifecycle management
- Detection tuning and operational maturity
- Correlation-based analytics across identity, endpoint, cloud, and data layers
- SOC-focused detections designed to improve analyst confidence and reduce alert fatigue
- Detection engineering methodologies aligned to enterprise SOC operations

---

# Detection Engineering Philosophy

This repository follows several core detection engineering principles:

## Behaviour Over Indicators
Detections are designed around attacker behaviour, attack paths, and anomalous activity rather than relying solely on static indicators of compromise (IOCs).

## Signal Quality Over Alert Volume
Detection logic prioritises actionable, high-confidence alerts while reducing operational noise and false positives.

## Readable & Maintainable KQL
Queries are structured to remain understandable, reusable, and maintainable for long-term SOC operations and collaborative engineering.

## Detection Lifecycle Management
Every detection supports iterative tuning, validation, and version tracking to reflect ongoing operational maturity.

## SOC-Centric Engineering
Detections are developed with investigation workflows in mind, including enrichment opportunities, triage usability, and analyst context.

---

# Repository Structure

The repository is organised by security domain and attack surface to support scalability, operational clarity, and structured detection engineering workflows.

```text
sentinel-detections/
│
├── README.md
├── LICENSE
├── CHANGELOG.md
├── CONTRIBUTING.md
├── ROADMAP.md
│
├── docs/
│   ├── detection-development-lifecycle.md
│   ├── rule-naming-standard.md
│   ├── tuning-methodology.md
│   ├── testing-strategy.md
│   ├── deployment-guide.md
│   ├── mitre-mapping-guide.md
│   └── data-source-requirements.md
│
├── rules/
│   │
│   ├── identity/
│   │   ├── impossible-travel/
│   │   │   ├── README.md
│   │   │   ├── rule.yaml
│   │   │   ├── test-data.json
│   │   │   ├── validation-query.kql
│   │   │   ├── investigation-guide.md
│   │   │   └── attack-simulation.md
│   │   │
│   │   ├── password-spray/
│   │   ├── mfa-fatigue/
│   │   ├── token-abuse/
│   │   ├── service-principal-abuse/
│   │   └── privileged-access-abuse/
│   │
│   ├── endpoint/
│   │   ├── defense-evasion/
│   │   ├── persistence/
│   │   ├── credential-access/
│   │   ├── ransomware/
│   │   └── powershell-abuse/
│   │
│   ├── cloud/
│   │   ├── azure/
│   │   ├── aws/
│   │   ├── gcp/
│   │   ├── kubernetes/
│   │   └── containers/
│   │
│   ├── email/
│   │   ├── phishing/
│   │   ├── bEC/
│   │   ├── suspicious-forwarding/
│   │   └── mailbox-compromise/
│   │
│   ├── data-protection/
│   │   ├── insider-threat/
│   │   ├── exfiltration/
│   │   ├── purview-label-abuse/
│   │   └── mass-download/
│   │
│   └── cross-domain/
│       ├── identity-to-cloud/
│       ├── endpoint-to-cloud/
│       ├── email-to-endpoint/
│       └── identity-to-data/
│
├── hunting/
│   ├── advanced-hunting-queries/
│   ├── threat-hunts/
│   └── anomaly-baselines/
│
├── utilities/
│   ├── enrichment-functions/
│   ├── watchlists/
│   ├── lookup-tables/
│   ├── parsers/
│   └── reusable-kql-functions/
│
├── templates/
│   ├── detection-template.yaml
│   ├── investigation-template.md
│   └── simulation-template.md
│
├── ci/
│   ├── yaml-validation.yml
│   ├── linting.yml
│   └── deployment-pipeline.yml
│
├── screenshots/
│   ├── dashboards/
│   ├── workbooks/
│   └── incidents/
│
└── lab/
    ├── attack-emulation/
    ├── purple-team/
    └── detection-validation/