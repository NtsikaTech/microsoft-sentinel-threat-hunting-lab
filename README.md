# Microsoft Sentinel Threat Hunting Lab

**Project status:** Active — Azure cybersecurity learning, detection engineering, threat hunting and SOC investigation lab.

## Overview

This project documents the development of a practical Microsoft Sentinel SOC environment built on Microsoft Azure.

The lab is designed not only to demonstrate the use of Microsoft Sentinel, but to develop practical understanding of Azure from a cybersecurity and Junior SOC Analyst perspective.

The environment currently includes an Azure Arc-enabled Ubuntu Linux machine, Azure Monitor Agent, Data Collection Rules, Log Analytics, Microsoft Sentinel and Microsoft Defender XDR.

The project follows a **learn → build → investigate → document** approach. Each learning session produces a practical artifact, investigation, detection, or piece of technical documentation that is committed to this repository.

## Objectives

- Develop practical Microsoft Azure knowledge relevant to entry level cybersecurity roles
- Understand cloud security architecture and Azure resource management
- Build and operate a Microsoft Sentinel SIEM environment
- Collect and analyse Linux security telemetry
- Develop KQL-based threat hunting queries
- Engineer and tune security detections
- Investigate alerts and incidents
- Apply MITRE ATT&CK concepts to detections and investigations
- Develop practical SOC investigation and response workflows
- Maintain a documented cybersecurity portfolio

## Current Environment

| Component | Status |
|---|---|
| Azure Resource Group |  Configured |
| Log Analytics Workspace |  Configured |
| Microsoft Sentinel |  Enabled |
| Microsoft Defender XDR |  Connected |
| Azure Arc |  Ubuntu machine onboarded |
| Azure Monitor Agent |  Installed |
| Data Collection Rules |  Configured |
| Linux Syslog Ingestion |  Operational |
| KQL Threat Hunting |  Active |
| Detection Engineering |  Active |
| SOC Investigation |  Upcoming |
| SOAR Automation |  Upcoming |

## Architecture

```text
Ubuntu-SOC-VMM
(Azure Arc-enabled Linux machine)
        │
        ▼
Azure Monitor Agent
        │
        ▼
Data Collection Rule
        │
        │ Linux Syslog
        ▼
Log Analytics Workspace
        │
        ▼
Microsoft Sentinel
        │
        ├── KQL Threat Hunting
        ├── Analytics Rules
        ├── Alerts
        └── Incidents
        │
        ▼
SOC Investigation


Learning Roadmap
Phase 1 — Infrastructure & Telemetry Foundation

Status: Completed

- Azure Resource Group created
- Log Analytics Workspace configured
- Microsoft Sentinel enabled
- Microsoft Defender XDR connected
- Data ingestion pipelines configured
- Log sources validated and normalised
- Azure Arc configured
- Ubuntu Linux machine onboarded
- Azure Monitor Agent installed
- Data Collection Rule configured
- Linux Syslog ingestion established
- Telemetry validated in Log Analytics / Sentinel

Phase 2 — Azure Security Fundamentals & Detection Engineering

Status: Active

- Azure Security Fundamentals
- Azure subscriptions and resource groups
- Azure resources and regions
- Azure Arc
- Azure Monitor Agent
- Data Collection Rules
- Log Analytics
- Microsoft Sentinel architecture
- Initial Azure RBAC exploration
- Microsoft Entra ID
- Azure networking fundamentals
- Azure Monitor and telemetry

Detection Engineering

- Initial Linux authentication hunting query
- First Linux authentication analytics rule
- Custom KQL analytic rules
- MITRE ATT&CK–mapped detections
- Alert tuning and false-positive reduction
- Watchlists and threat intelligence integration
- SSH authentication monitoring

Phase 3 — SOC Investigation & Response

Status: Upcoming

- Simulated attack scenarios (e.g. lateral movement, credential access)
- End-to-end incident investigation walkthroughs
- Evidence analysis and attack-chain reconstruction
- Threat intelligence enrichment
- Automated response playbooks (Logic Apps / SOAR)
- Metrics and detection coverage reporting

| Category             | Technology                 |
| -------------------- | -------------------------- |
| Cloud Platform       | Microsoft Azure            |
| SIEM                 | Microsoft Sentinel         |
| Log Management       | Azure Log Analytics        |
| Monitoring           | Azure Monitor              |
| Server Onboarding    | Azure Arc                  |
| Telemetry Collection | Azure Monitor Agent        |
| Data Collection      | Data Collection Rules      |
| XDR                  | Microsoft Defender XDR     |
| Query Language       | KQL (Kusto Query Language) |
| Automation           | Azure Logic Apps           |
| Framework            | MITRE ATT&CK               |


Documentation

Detailed learning sessions, architecture notes, investigations and lessons learned are maintained in the docs/ directory.

Each session documents:

- What was learned
- Why the technology is relevant to cybersecurity
- What was implemented
- How the technology fits into the SOC architecture
-Troubleshooting and observations
-Practical lessons learned


Purpose

This lab demonstrates practical cybersecurity skills across cloud infrastructure, SIEM operations, security monitoring, threat hunting, detection engineering and incident investigation.

The project follows a learn → build → investigate → document approach and is being developed as a hands-on learning environment for entry-level cybersecurity and Junior SOC Analyst roles.



