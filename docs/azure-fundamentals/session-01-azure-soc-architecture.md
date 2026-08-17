\# # Azure Fundamentals — Session 01

\## Understanding the Architecture of a Microsoft Sentinel SOC



\*\*Session focus:\*\* Azure fundamentals and SOC architecture  

\*\*Environment:\*\* Microsoft Azure / Microsoft Sentinel  

\*\*Lab machine:\*\* Ubuntu-SOC-VMM  

\*\*Date:\*\* June 2026



\---



\## 1. Session Objective



The objective of this session was to understand the basic structure of Microsoft Azure and how the Azure services used in the Microsoft Sentinel SOC lab work together.



Rather than only following configuration instructions, this session focused on understanding what each Azure component does, why it exists, and how it contributes to the security monitoring pipeline.



\---



\## 2. Azure Management Hierarchy



The Azure environment is organised using a hierarchy:



```text

Microsoft Azure

└── Subscription

&#x20;   └── Resource Group

&#x20;       └── Resources



\## In this lab:



Azure subscription 1

└── Azure-Sentinel-SOC-Lab

&#x20;   ├── sentinel-law-lab

&#x20;   │   └── Log Analytics Workspace

&#x20;   │

&#x20;   ├── Ubuntu-SOC-VMM

&#x20;   │   └── Azure Arc-enabled machine

&#x20;   │

&#x20;   ├── ubuntu-syslog-dcr

&#x20;   │   └── Data Collection Rule

&#x20;   │

&#x20;   └── SecurityInsights(sentinel-law-lab)

&#x20;       └── Microsoft Sentinel solution

Key concepts learned



Subscription



A subscription provides a management and billing boundary for Azure resources.



Resource Group



A resource group is a logical container used to organise related Azure resources.



Resource



A resource is an individual Azure service or component, such as a Log Analytics workspace, Data Collection Rule or Azure Arc-enabled machine.





\## 3. Azure Arc



The Ubuntu SOC machine runs externally in VirtualBox rather than as an Azure-native virtual machine.



Azure Arc allows the external machine to be connected to Azure and represented as an Azure-managed resource.



The machine appears in Azure as:



Ubuntu-SOC-VMM



with the resource type:



Machine - Azure Arc



This demonstrates that Azure can manage and monitor infrastructure that is not physically running inside Azure.



Cybersecurity relevance



In a real organisation, infrastructure may exist across:



Azure

Other cloud providers

On-premises environments

Physical servers

Virtual machines



Azure Arc can provide a way to bring external infrastructure into Azure management and monitoring.





\##4. Azure Monitor Agent



The Azure Monitor Agent (AMA) is installed on the Ubuntu machine.



Its role is to collect monitoring and security telemetry from the machine.



The agent is different from Azure Arc.



Azure Arc connects the external machine to Azure management.

Azure Monitor Agent collects telemetry from the machine.



This distinction is important when understanding Azure monitoring architecture.





\## 5. Data Collection Rules



The Data Collection Rule used in the lab is:



ubuntu-syslog-dcr



The DCR defines what telemetry should be collected and where the collected data should be sent.



The configured Linux Syslog facilities include:



LOG\_AUTH

LOG\_AUTHPRIV

LOG\_SYSLOG

LOG\_KERN



The DCR Visualizer showed the relationship between:



Ubuntu-SOC-VMM

&#x20;       │

&#x20;       ▼

Linux Syslog

&#x20;       │

&#x20;       ▼

sentinel-law-lab



This demonstrated that the DCR connects the source of telemetry with the destination where the telemetry is stored.





\## 6. Log Analytics Workspace



The Log Analytics workspace is:



sentinel-law-lab



The workspace provides a central location where collected telemetry can be stored and queried.



Kusto Query Language (KQL) can be used to search and analyse the collected data.



For example:



Syslog

| sort by TimeGenerated desc

| take 20



This allows an analyst to inspect the most recent Syslog events.





\## 7. Microsoft Sentinel



Microsoft Sentinel provides the security analytics and SIEM layer of the environment.



The Sentinel workspace is associated with the sentinel-law-lab Log Analytics workspace.



Sentinel can use the telemetry stored in the workspace for:



Security monitoring

Threat hunting

Detection engineering

Alert generation

Incident management

Investigation



The lab has already demonstrated this by creating a Linux authentication failure detection that generated an alert and incident.





\## 8. Telemetry Architecture



The current security monitoring pipeline can be represented as:



Ubuntu-SOC-VMM

(Azure Arc-enabled Linux machine)

&#x20;       │

&#x20;       │ Generates system/security events

&#x20;       ▼

Azure Monitor Agent

&#x20;       │

&#x20;       │ Collects telemetry

&#x20;       ▼

Data Collection Rule

&#x20;       │

&#x20;       │ Defines required Syslog data

&#x20;       ▼

Linux Syslog

&#x20;       │

&#x20;       ▼

Log Analytics Workspace

&#x20;       │

&#x20;       │ KQL querying

&#x20;       ▼

Microsoft Sentinel

&#x20;       │

&#x20;       ├── Analytics Rules

&#x20;       ├── Alerts

&#x20;       ├── Incidents

&#x20;       └── Threat Hunting

&#x20;       │

&#x20;       ▼

SOC Analyst





\## 9. Azure RBAC



The Azure subscription was also explored to understand access control.



The Owner role was observed in Azure RBAC.



The Owner role provides full access to manage resources and allows the assignment of Azure RBAC roles.



This introduced the principle of least privilege:



Users and services should receive only the permissions required to perform their responsibilities.



RBAC will be explored in greater depth in a future Azure security session.





\## 10. What I Learned



The main lesson from this session was that Microsoft Sentinel is not an isolated application.



The SOC environment consists of several interconnected Azure services.



I learned to distinguish between:



Azure Arc — connects and manages the external machine

Azure Monitor Agent — collects telemetry

Data Collection Rules — control what telemetry is collected and where it is sent

Log Analytics — stores and provides query access to telemetry

Microsoft Sentinel — provides the security analytics and SIEM capabilities



I also learned that Azure has a separate management hierarchy:



Subscription

&#x20;   ↓

Resource Group

&#x20;   ↓

Resources



Understanding both the Azure management hierarchy and the security telemetry pipeline is important when working with Azure as a cybersecurity analyst.





\## 11. SOC Analyst Perspective



From a SOC analyst perspective, understanding where a security event originates and how it reaches the SIEM is important.



For example, a Linux authentication failure can follow this path:



Linux authentication event

&#x20;       ↓

Azure Monitor Agent

&#x20;       ↓

Data Collection Rule

&#x20;       ↓

Log Analytics

&#x20;       ↓

Microsoft Sentinel

&#x20;       ↓

KQL investigation

&#x20;       ↓

Analytics Rule

&#x20;       ↓

Alert

&#x20;       ↓

Incident

&#x20;       ↓

SOC investigation



This provides the foundation for future work involving threat hunting, detection engineering and incident response.





\## 12. Next Learning Areas



Future Azure learning sessions will build on this foundation and explore:



Azure RBAC and least privilege

Microsoft Entra ID

Azure networking fundamentals

Azure Monitor and telemetry

KQL threat hunting

Detection engineering

MITRE ATT\&CK mapping

Incident investigation

Automation and SOAR

Session Outcome



This session established a foundational understanding of how the Azure services in the SOC lab relate to one another.



The next stage will move from understanding the architecture toward using Azure and Microsoft Sentinel to perform practical security analysis and detection engineering.



