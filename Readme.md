# CST8919 – DevOps Security & Compliance  
## Assignment 2 – Cloud Service Alternatives Report  
## Submitted By : Jaspreet Singh

> **Objective**: Compare Azure services used in the course with AWS and GCP equivalents in terms of features, security/compliance, pricing, and DevSecOps integration.

---

## Quick Reference – Azure -- AWS -- GCP

| Azure Service | AWS Equivalent | GCP Equivalent |
|---|---|---|
| Azure Active Directory (Entra ID) | AWS IAM + IAM Identity Center (SSO) | Cloud IAM + Cloud Identity |
| Managed Identities | IAM Roles for EC2/Lambda + AWS STS | Service Accounts + Workload Identity Federation |
| Azure Monitor | Amazon CloudWatch | Cloud Monitoring |
| Log Analytics | CloudWatch Logs + Logs Insights | Cloud Logging + Logs Explorer |
| Azure Policy | AWS Config + Service Control Policies (SCPs) | Organization Policy Service |
| Microsoft Defender for Cloud | Amazon GuardDuty + AWS Security Hub | Security Command Center |
| Microsoft Sentinel | Security Lake + Partner SIEM (Splunk, Elastic, etc.) | Google Security Operations (Chronicle SIEM) |
| Azure Key Vault | AWS KMS + AWS Secrets Manager | Cloud KMS + Secret Manager |
| Activity Logs | AWS CloudTrail | Cloud Audit Logs |
| Network Security Groups (NSGs) | Security Groups + Network ACLs | VPC Firewall Rules |
| Private Endpoints | AWS PrivateLink | Private Service Connect |
| Microsoft Purview | AWS Glue Data Catalog + Lake Formation | Dataplex + Data Catalog |
| Azure Firewall | AWS Network Firewall | Cloud Firewall Rules / Cloud Armor |
| Azure Blueprints | AWS Service Catalog | Deployment Manager + Config Connector |
| Defender for DevOps | CodeGuru Security + Inspector + Security Hub CI/CD integrations | Security Command Center + Cloud Build security scans |

---

## Consolidated Pricing Overview

| Azure Service | Azure Pricing Model | AWS Pricing Model | GCP Pricing Model |
|---|---|---|---|
| Azure Active Directory (Entra ID) | Free, P1, P2 per user/month | IAM free; Identity Center per user/month | IAM free; Cloud Identity free/paid tiers |
| Managed Identities | No charge | No charge | No charge |
| Azure Monitor | $/GB ingest + retention | CloudWatch per metric, $/GB logs | Cloud Monitoring free tier + overage |
| Log Analytics | $/GB ingest + retention | CloudWatch Logs $/GB ingest/retention | Cloud Logging $0.50/GiB (50 GiB free) |
| Azure Policy | Included | AWS Config per config item/month | Org Policy free |
| Microsoft Defender for Cloud | Free tier + per resource plan pricing | GuardDuty $/GB analyzed; Security Hub per check/finding | SCC Standard free; Premium/Enterprise subscription |
| Microsoft Sentinel | $/GB ingested; commitment tiers | Security Lake storage/scan + partner SIEM licensing | Chronicle SIEM subscription |
| Azure Key Vault | Per transaction + key storage | KMS per key + Secrets Manager per secret/month | Cloud KMS per key + Secret Manager per secret/month |
| Activity Logs | Free (retention billed) | CloudTrail 1 copy free; additional trails per GB | Cloud Audit Logs free for admin; data logs billed per GB |
| Network Security Groups (NSGs) | Included | Included | Included |
| Private Endpoints | $/endpoint/hour + data | $/endpoint/hour + data | $/endpoint/hour + data |
| Microsoft Purview | vCore-hour + data operations | Glue free tier + per DPU-hour; Lake Formation free + API costs | Dataplex + Data Catalog per operation/storage |
| Azure Firewall | Hourly + data processed | Hourly + data processed | Rules free; Cloud Armor per policy/month + data |
| Azure Blueprints | Included | Service Catalog free | Deployment Manager free |
| Defender for DevOps | Included in Defender for Cloud plan | CodeGuru Security + Inspector usage pricing | SCC + Cloud Build scans usage pricing |

---

# Detailed Overview

## 1. Azure Active Directory (Microsoft Entra ID)

**Overview**  
Cloud-based identity and access management (IAM) platform for users, apps, and devices with SSO, Conditional Access, and MFA.

**Core Features**  
- SSO for SaaS and on-prem apps  
- RBAC and custom roles  
- Conditional Access policies  
- B2B and B2C identity models  

**Security & Compliance**  
ISO 27001, SOC 2, FedRAMP High, HIPAA, GDPR compliant.

**Pricing Model**  
Free tier; P1 and P2 editions with feature-based licensing.

**DevSecOps Integration**  
OIDC federation with CI/CD tools; Managed Identity for Azure services; role-based gating of pipeline actions.

**Comparison Table**

| Feature | Azure Active Directory (Entra ID) | AWS IAM + Identity Center | GCP Cloud IAM + Cloud Identity |
|---|---|---|---|
| Service Type | Identity & Access Mgmt | Identity & Access Mgmt | Identity & Access Mgmt |
| Core Features | SSO, RBAC, Conditional Access, MFA | SSO, Roles, Policies, MFA | SSO, Roles, Policies, MFA |
| Security & Compliance | ISO, SOC, FedRAMP, HIPAA, GDPR | ISO, SOC, FedRAMP, HIPAA | ISO, SOC, FedRAMP, HIPAA |
| Pricing | Free, P1, P2 per user/mo | IAM free, Identity Center per user/mo | IAM free, Cloud Identity free/paid |
| DevSecOps Integration | OIDC federation, role-based gates | OIDC federation, policy enforcement | OIDC federation, policy enforcement |

---

## 2. Managed Identities

**Overview**  
Provides Azure-hosted identities for workloads to access resources without storing credentials.

**Core Features**  
- System-assigned or user-assigned identities  
- Automatic rotation of credentials  
- Direct integration with Azure Key Vault, Storage, SQL Database

**Security & Compliance**  
Removes secret storage from app code; inherits Azure compliance.

**Pricing Model**  
No additional cost.

**DevSecOps Integration**  
Secure pipeline-to-resource authentication without secrets in repos.

**Comparison Table**

| Feature | Azure Managed Identities | AWS IAM Roles + STS | GCP Service Accounts + Workload Identity Federation |
|---|---|---|---|
| Service Type | Workload Identity Mgmt | Workload Identity Mgmt | Workload Identity Mgmt |
| Core Features | System/User assigned IDs, auto rotation | Roles for EC2/Lambda, STS tokens | Service Accounts, federation |
| Security & Compliance | Credential-free, ISO/SOC/FedRAMP | Credential-free, ISO/SOC/FedRAMP | Credential-free, ISO/SOC/FedRAMP |
| Pricing | Free | Free | Free |
| DevSecOps Integration | Pipeline auth w/o secrets | Pipeline auth w/o secrets | Pipeline auth w/o secrets |

---

## 3. Azure Monitor

**Overview**  
Unified telemetry platform for metrics, logs, and alerts.

**Core Features**  
- Metrics collection  
- Alerts and action groups  
- Dashboarding  
- Integration with Log Analytics

**Security & Compliance**  
ISO 27001, SOC, HIPAA.

**Pricing Model**  
Pay-as-you-go per GB of data ingested and retained.

**DevSecOps Integration**  
Monitors pipeline deployments, application performance, and infrastructure health.

**Comparison Table**

| Feature | Azure Monitor | AWS CloudWatch | GCP Cloud Monitoring |
|---|---|---|---|
| Service Type | Observability platform | Observability platform | Observability platform |
| Core Features | Metrics, alerts, dashboards | Metrics, logs, dashboards | Metrics, alerts, dashboards |
| Security & Compliance | ISO, SOC, HIPAA | ISO, SOC, HIPAA | ISO, SOC, HIPAA |
| Pricing | $/GB ingest + retention | Per metric, $/GB logs | Free tier + overage |
| DevSecOps Integration | CI/CD telemetry hooks | CI/CD telemetry hooks | CI/CD telemetry hooks |

---

## 4. Log Analytics

**Overview**  
Log query and analytics engine for data in Azure Monitor workspaces.

**Core Features**  
- Kusto Query Language (KQL)  
- Cross-resource querying  
- Log-based alerts

**Security & Compliance**  
Audit logging for security investigations.

**Pricing Model**  
Charged by data ingested and retention duration.

**DevSecOps Integration**  
Log-driven quality gates in CI/CD.

**Comparison Table**

| Feature | Azure Log Analytics | AWS CloudWatch Logs + Insights | GCP Cloud Logging + Logs Explorer |
|---|---|---|---|
| Service Type | Log analysis platform | Log analysis platform | Log analysis platform |
| Core Features | KQL, cross-resource queries | Logs Insights queries | Logs Explorer queries |
| Security & Compliance | ISO, SOC, HIPAA | ISO, SOC, HIPAA | ISO, SOC, HIPAA |
| Pricing | $/GB ingest + retention | $/GB ingest + retention | $/GB ingest + retention |
| DevSecOps Integration | Quality gates in CI/CD | Quality gates in CI/CD | Quality gates in CI/CD |

---

## 5. Azure Policy

**Overview**  
Governance tool to enforce organizational compliance at scale.

**Core Features**  
- Built-in and custom policy definitions  
- Initiative groupings  
- Automatic remediation

**Security & Compliance**  
Aligns with CIS, NIST, and ISO frameworks.

**Pricing Model**  
Included in Azure subscription.

**DevSecOps Integration**  
Policy-as-code enforcement in pipelines and IaC templates.

**Comparison Table**

| Feature | Azure Policy | AWS Config + SCPs | GCP Organization Policy |
|---|---|---|---|
| Service Type | Governance & Compliance | Governance & Compliance | Governance & Compliance |
| Core Features | Built-in/custom policies, remediation | Rules, remediation, SCPs | Constraints, policy rules |
| Security & Compliance | CIS, NIST, ISO | CIS, NIST, ISO | CIS, NIST, ISO |
| Pricing | Included | Per item/month | Free |
| DevSecOps Integration | Policy-as-code | Policy-as-code | Policy-as-code |

---

## 6. Microsoft Defender for Cloud

**Overview**  
Cloud security posture management (CSPM) and workload protection.

**Core Features**  
- Secure score  
- Threat detection  
- Recommendations and remediation

**Security & Compliance**  
Covers CIS, ISO, NIST, PCI DSS.

**Pricing Model**  
Free tier for posture; paid plans for workloads.

**DevSecOps Integration**  
Integration with CI/CD for vulnerability scanning and compliance gates.

**Comparison Table**

| Feature | Microsoft Defender for Cloud | AWS GuardDuty + Security Hub | GCP Security Command Center |
|---|---|---|---|
| Service Type | CSPM + CWPP | Threat detection + posture mgmt | Threat detection + posture mgmt |
| Core Features | Secure score, threat detection | Threat detection, findings | Threat detection, findings |
| Security & Compliance | CIS, ISO, NIST, PCI DSS | CIS, ISO, NIST, PCI DSS | CIS, ISO, NIST, PCI DSS |
| Pricing | Free tier + paid plans | Usage-based pricing | Free standard, paid premium |
| DevSecOps Integration | CI/CD scanning | CI/CD scanning | CI/CD scanning |

---

## 7. Microsoft Sentinel

**Overview**  
Cloud-native SIEM + SOAR platform.

**Core Features**  
- Security log ingestion  
- Analytics rules  
- Automated playbooks

**Security & Compliance**  
Supports compliance auditing, GDPR, ISO, SOC.

**Pricing Model**  
Pay per GB ingested with commitment tiers.

**DevSecOps Integration**  
Automates incident response triggered from CI/CD logs.

**Comparison Table**

| Feature | Microsoft Sentinel | AWS Security Lake + Partner SIEM | GCP Google Security Operations |
|---|---|---|---|
| Service Type | SIEM + SOAR | SIEM + SOAR | SIEM + SOAR |
| Core Features | Analytics, automation | Analytics, automation | Analytics, automation |
| Security & Compliance | ISO, SOC, GDPR | ISO, SOC, GDPR | ISO, SOC, GDPR |
| Pricing | $/GB ingest | Storage + scan costs | Subscription |
| DevSecOps Integration | Automated response | Automated response | Automated response |

---

## 8. Azure Key Vault

**Overview**  
Secure storage for secrets, keys, and certificates.

**Core Features**  
- RBAC and policy integration  
- HSM-backed key management  
- Secret versioning

**Security & Compliance**  
FIPS 140-2 Level 2 validated HSM.

**Pricing Model**  
Per-operation cost + storage.

**DevSecOps Integration**  
Stores CI/CD pipeline secrets securely.

**Comparison Table**

| Feature | Azure Key Vault | AWS KMS + Secrets Manager | GCP Cloud KMS + Secret Manager |
|---|---|---|---|
| Service Type | Secrets & key management | Secrets & key management | Secrets & key management |
| Core Features | HSM, RBAC, versioning | HSM, IAM, versioning | HSM, IAM, versioning |
| Security & Compliance | FIPS 140-2, ISO, SOC | FIPS 140-2, ISO, SOC | FIPS 140-2, ISO, SOC |
| Pricing | Per op + storage | Per key + per secret | Per key + per secret |
| DevSecOps Integration | Secure secrets in CI/CD | Secure secrets in CI/CD | Secure secrets in CI/CD |

---
## 9. Activity Logs

**Overview**  
Centralized log of all control-plane operations within Azure.

**Core Features**  
- Resource-level change tracking  
- Role-based access to logs  
- Export to Log Analytics or SIEM

**Security & Compliance**  
Enables audit and forensic investigations.

**Pricing Model**  
Free for 90 days; extended retention billed.

**DevSecOps Integration**  
Monitors IaC deployments and changes in real time.

**Comparison Table**

| Feature | Azure Activity Logs | AWS CloudTrail | GCP Cloud Audit Logs |
|---|---|---|---|
| Service Type | Audit logging | Audit logging | Audit logging |
| Core Features | Control-plane ops, export | API activity, export | Admin/data activity |
| Security & Compliance | ISO, SOC, FedRAMP | ISO, SOC, FedRAMP | ISO, SOC, FedRAMP |
| Pricing | Free 90 days, paid extended | 1 free copy, extra billed | Admin logs free, data logs billed |
| DevSecOps Integration | Deployment monitoring | Deployment monitoring | Deployment monitoring |

---

## 10. Network Security Groups (NSGs)

**Overview**  
Stateful firewall rules controlling inbound/outbound VM and subnet traffic.

**Core Features**  
- Rule-based filtering  
- Priority ordering  
- Service tags for Azure services

**Security & Compliance**  
Implements network segmentation and least privilege.

**Pricing Model**  
Included with Azure subscription.

**DevSecOps Integration**  
Automated deployment of NSG rules via IaC templates.

**Comparison Table**

| Feature | Azure NSG | AWS Security Groups + NACLs | GCP VPC Firewall Rules |
|---|---|---|---|
| Service Type | Network firewall | Network firewall | Network firewall |
| Core Features | Inbound/outbound rules, stateful | Inbound/outbound rules, stateful | Inbound/outbound rules, stateful |
| Security & Compliance | ISO, SOC, CIS | ISO, SOC, CIS | ISO, SOC, CIS |
| Pricing | Included | Included | Included |
| DevSecOps Integration | IaC-defined rules | IaC-defined rules | IaC-defined rules |

---

## 11. Private Endpoints

**Overview**  
Enables private IP access to Azure services over the Azure backbone.

**Core Features**  
- Service-specific private IPs  
- DNS integration  
- Removes public exposure

**Security & Compliance**  
Prevents data exfiltration via public endpoints.

**Pricing Model**  
Hourly per endpoint + data processed.

**DevSecOps Integration**  
Secure service-to-service communication in CI/CD test environments.

**Comparison Table**

| Feature | Azure Private Endpoint | AWS PrivateLink | GCP Private Service Connect |
|---|---|---|---|
| Service Type | Private service access | Private service access | Private service access |
| Core Features | Private IPs, DNS integration | Private IPs, DNS integration | Private IPs, DNS integration |
| Security & Compliance | ISO, SOC, CIS | ISO, SOC, CIS | ISO, SOC, CIS |
| Pricing | Per endpoint/hour + data | Per endpoint/hour + data | Per endpoint/hour + data |
| DevSecOps Integration | Secure pipelines | Secure pipelines | Secure pipelines |

---

## 12. Microsoft Purview

**Overview**  
Data governance and cataloging platform.

**Core Features**  
- Data discovery and lineage  
- Classification and labeling  
- Integration with security/compliance services

**Security & Compliance**  
Supports data privacy and sovereignty compliance.

**Pricing Model**  
Pay per vCore-hour and per operation.

**DevSecOps Integration**  
Ensures data assets used in pipelines are compliant and cataloged.

**Comparison Table**

| Feature | Microsoft Purview | AWS Glue + Lake Formation | GCP Dataplex + Data Catalog |
|---|---|---|---|
| Service Type | Data catalog + governance | Data catalog + governance | Data catalog + governance |
| Core Features | Discovery, lineage, classification | Discovery, lineage, classification | Discovery, lineage, classification |
| Security & Compliance | GDPR, ISO, SOC | GDPR, ISO, SOC | GDPR, ISO, SOC |
| Pricing | vCore-hour + ops | DPU-hour + ops | Per op/storage |
| DevSecOps Integration | Catalog compliance checks | Catalog compliance checks | Catalog compliance checks |

---

## 13. Azure Firewall

**Overview**  
Cloud-native firewall as a service.

**Core Features**  
- Layer 3–7 filtering  
- Threat intelligence filtering  
- DNAT/SNAT

**Security & Compliance**  
Built-in threat intelligence feeds.

**Pricing Model**  
Hourly + per GB processed.

**DevSecOps Integration**  
Automated rule deployment for ephemeral test environments.

**Comparison Table**

| Feature | Azure Firewall | AWS Network Firewall | GCP Cloud Firewall / Cloud Armor |
|---|---|---|---|
| Service Type | Managed firewall | Managed firewall | Managed firewall |
| Core Features | L3–L7 rules, threat intel | L3–L7 rules, threat intel | L3–L7 rules, WAF |
| Security & Compliance | ISO, SOC, CIS | ISO, SOC, CIS | ISO, SOC, CIS |
| Pricing | Hourly + data | Hourly + data | Free rules, paid WAF |
| DevSecOps Integration | Rule automation | Rule automation | Rule automation |

---

## 14. Azure Blueprints

**Overview**  
Infrastructure and governance-as-code templates.

**Core Features**  
- Deploy policies, RBAC, resources together  
- Version control of blueprints  
- Continuous compliance

**Security & Compliance**  
Ensures repeatable compliant environments.

**Pricing Model**  
Included with subscription.

**DevSecOps Integration**  
Blueprints as part of CI/CD provisioning stages.

**Comparison Table**

| Feature | Azure Blueprints | AWS Service Catalog | GCP Deployment Manager + Config Connector |
|---|---|---|---|
| Service Type | Governance-as-code | Governance-as-code | Governance-as-code |
| Core Features | Policies + RBAC + infra | Catalog of approved templates | YAML-based infra + policies |
| Security & Compliance | ISO, SOC, CIS | ISO, SOC, CIS | ISO, SOC, CIS |
| Pricing | Included | Free | Free |
| DevSecOps Integration | Provisioning automation | Provisioning automation | Provisioning automation |

---

## 15. Defender for DevOps

**Overview**  
Security posture management for CI/CD pipelines.

**Core Features**  
- Secret scanning in repos  
- Dependency vulnerability detection  
- Pipeline policy enforcement

**Security & Compliance**  
Integrates with industry-standard scanning tools.

**Pricing Model**  
Included in Defender for Cloud plan.

**DevSecOps Integration**  
Shifts security left in development lifecycle.

**Comparison Table**

| Feature | Defender for DevOps | AWS CodeGuru Security + Inspector | GCP SCC + Cloud Build Security |
|---|---|---|---|
| Service Type | DevOps security | DevOps security | DevOps security |
| Core Features | Secret scan, dep scan, policies | Code scan, vuln detect | Code scan, vuln detect |
| Security & Compliance | ISO, SOC, CIS | ISO, SOC, CIS | ISO, SOC, CIS |
| Pricing | Included | Usage-based | Included |
| DevSecOps Integration | Security in CI/CD | Security in CI/CD | Security in CI/CD |

---

