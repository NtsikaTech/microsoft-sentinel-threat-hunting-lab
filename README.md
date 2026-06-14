# Microsoft Sentinel Threat Hunting Lab

> **Repo status:** Infrastructure & configuration documentation — actively evolving into a full detection engineering and SOC investigation lab.

## Overview

This project documents the end-to-end build-out of a Microsoft Sentinel SOC environment on Azure. The current phase focuses on infrastructure provisioning, log ingestion configuration, and validation of telemetry from an Azure Arc-enabled Linux machine. Ubuntu-based Syslog data is now actively flowing into Microsoft Sentinel via Azure Monitor Agent and Data Collection Rules. Upcoming phases will introduce KQL-based detection rules, custom analytic rules, threat hunting workflows, and simulated SOC investigations.

## Environment

| Component | Status |
|---|---|
| Azure Resource Group | ✅ Provisioned |
| Log Analytics Workspace | ✅ Configured |
| Microsoft Sentinel | ✅ Enabled |
| Microsoft Defender XDR | ✅ Connected |
| Data Connectors & Ingestion | ✅ Connected |
| Detection Rules (Analytic Rules) | ✅ Connected |
| Threat Hunting Queries (KQL) | 🔜 Upcoming |
| SOC Investigation Playbooks | 🔜 Upcoming |

## Roadmap

### Phase 1 — Infrastructure (Completed)
- [x] Azure Resource Group created
- [x] Log Analytics Workspace configured
- [x] Microsoft Sentinel enabled
- [x] Microsoft Defender XDR connected
- [x] Data ingestion pipelines configured
- [x] Log sources validated and normalised
- [x] Ubuntu integration

### Phase 2 — Detection Engineering (Upcoming)
- [ ] Custom KQL analytic rules
- [ ] MITRE ATT&CK–mapped detections
- [ ] Alert tuning and false-positive reduction
- [ ] Watchlists and threat intelligence integration

### Phase 3 — SOC Investigation Simulation (Upcoming)
- [ ] Simulated attack scenarios (e.g. lateral movement, credential access)
- [ ] End-to-end incident investigation walkthroughs
- [ ] Automated response playbooks (Logic Apps / SOAR)
- [ ] Metrics and detection coverage reporting

## Tech Stack

- **SIEM:** Microsoft Sentinel
- **Cloud:** Microsoft Azure
- **XDR:** Microsoft Defender XDR
- **Query Language:** KQL (Kusto Query Language)
- **Automation:** Azure Logic Apps
- **Frameworks:** MITRE ATT&CK

## Purpose

This lab demonstrates practical SOC engineering skills including detection rule development, threat hunting, and incident investigation using Microsoft Sentinel and Microsoft Defender XDR in a cloud-native environment. Each phase is documented with configuration notes, rationale, and lessons learned — with SOAR automation and MITRE ATT&CK coverage built in throughout.

---

*Part of the [cybersecurity portfolio](https://github.com/your-username) — see also: Windows Security Log Analyzer · IOC Enrichment & Threat Intelligence Engine · Network Security Monitoring & SOC Simulation Engine*
