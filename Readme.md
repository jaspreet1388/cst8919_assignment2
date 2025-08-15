# CST8919 – DevOps Security & Compliance  
## Assignment 2 – Cloud Service Alternatives Report
## Submitted By : Jaspreet Singh

> **Objective**: Compare Azure services used in the course with AWS and GCP equivalents in terms of features, security/compliance, pricing, and DevSecOps integration.

---

## Quick Reference – Azure → AWS → GCP

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

**AWS Equivalent**: AWS IAM + IAM Identity Center  
**GCP Equivalent**: Cloud IAM + Cloud Identity

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

**AWS Equivalent**: IAM Roles + AWS STS  
**GCP Equivalent**: Service Accounts + Workload Identity Federation

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

**AWS Equivalent**: CloudWatch  
**GCP Equivalent**: Cloud Monitoring

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

**AWS Equivalent**: CloudWatch Logs + Logs Insights  
**GCP Equivalent**: Cloud Logging + Logs Explorer

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

**AWS Equivalent**: AWS Config + SCPs  
**GCP Equivalent**: Organization Policy Service

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

**AWS Equivalent**: GuardDuty + Security Hub  
**GCP Equivalent**: Security Command Center

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

**AWS Equivalent**: Security Lake + Partner SIEM  
**GCP Equivalent**: Google Security Operations (Chronicle SIEM)

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

**AWS Equivalent**: AWS KMS + Secrets Manager  
**GCP Equivalent**: Cloud KMS + Secret Manager

---

## 9. Activity Logs

**Overview**  
Tracks subscription-level changes and actions.

**Core Features**  
- Audit trail  
- Administrative and operational events

**Security & Compliance**  
Supports forensic investigation and compliance audits.

**Pricing Model**  
No direct cost; storage/retention billed separately.

**DevSecOps Integration**  
Audits deployment changes in pipelines.

**AWS Equivalent**: CloudTrail  
**GCP Equivalent**: Cloud Audit Logs

---

## 10. Network Security Groups (NSGs)

**Overview**  
Control inbound/outbound traffic at subnet and NIC levels.

**Core Features**  
- Rule-based filtering  
- Stateful inspection

**Security & Compliance**  
Implements network segmentation and least privilege.

**Pricing Model**  
Included with VNet.

**DevSecOps Integration**  
Defines security as code for network boundaries.

**AWS Equivalent**: Security Groups + NACLs  
**GCP Equivalent**: VPC Firewall Rules

---

## 11. Private Endpoints

**Overview**  
Secure service access via private IP in a VNet.

**Core Features**  
- Restrict public access  
- Integrates with Key Vault, Storage, SQL

**Security & Compliance**  
Prevents data exfiltration over public internet.

**Pricing Model**  
Billed per endpoint/hour + data processed.

**DevSecOps Integration**  
Private-only pipelines for secure deployments.

**AWS Equivalent**: PrivateLink  
**GCP Equivalent**: Private Service Connect

---

## 12. Microsoft Purview

**Overview**  
Data governance and catalog service.

**Core Features**  
- Data discovery  
- Classification  
- Lineage tracking

**Security & Compliance**  
Helps meet GDPR, HIPAA.

**Pricing Model**  
Pay-as-you-go per vCore-hour and data operations.

**DevSecOps Integration**  
Classifies sensitive data early in data pipelines.

**AWS Equivalent**: Glue Data Catalog + Lake Formation  
**GCP Equivalent**: Dataplex + Data Catalog

---

## 13. Azure Firewall

**Overview**  
Stateful, managed network firewall.

**Core Features**  
- Layer 3–7 filtering  
- Threat intelligence-based rules

**Security & Compliance**  
Supports regulatory segmentation requirements.

**Pricing Model**  
Hourly instance cost + data processed.

**DevSecOps Integration**  
Firewall rules deployed as code via CI/CD.

**AWS Equivalent**: Network Firewall  
**GCP Equivalent**: Cloud Firewall Rules / Cloud Armor

---

## 14. Azure Blueprints

**Overview**  
Package of governance artifacts (policies, RBAC, ARM templates).

**Core Features**  
- Standardized deployments  
- Version control

**Security & Compliance**  
Ensures compliance at deployment time.

**Pricing Model**  
No extra charge.

**DevSecOps Integration**  
Blueprints applied automatically in IaC pipelines.

**AWS Equivalent**: Service Catalog  
**GCP Equivalent**: Deployment Manager + Config Connector

---

## 15. Defender for DevOps

**Overview**  
Secures development environments, repos, and pipelines.

**Core Features**  
- Code scanning  
- Secrets detection  
- Pipeline risk assessment

**Security & Compliance**  
Aligns with OWASP and DevSecOps best practices.

**Pricing Model**  
Integrated into Defender for Cloud subscription.

**DevSecOps Integration**  
Integrates directly with GitHub, Azure DevOps, and pipelines.

**AWS Equivalent**: CodeGuru Security + Inspector + Security Hub  
**GCP Equivalent**: SCC + Cloud Build security scans
