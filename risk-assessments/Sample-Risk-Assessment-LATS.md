# Sample Risk Assessment — Logistics Asset Tracking System (LATS)

**Document Type:** Risk Assessment (Worked Example)
**Framework:** NIST Risk Management Framework (RMF), aligned to NIST SP 800-30 Rev 1
**Author:** William Mace
**Date:** September 2026
**Classification:** Sample / Illustrative — fictional system, built to demonstrate application of the [NIST RMF Risk Assessment Template](NIST-RMF-Risk-Assessment-Template.md) to a realistic scenario.

> Note: LATS is a fictional composite system modeled on logistics/asset-tracking environments similar to those I supported as a federal Program Analyst. No real organization, system, or non-public data is referenced.

---

## 1. System Information

| Field | Details |
|---|---|
| System Name | Logistics Asset Tracking System (LATS) |
| System Owner | Director, Logistics Operations Division |
| System Type | Major Application |
| FIPS 199 Impact Level | Moderate |
| Authorization Boundary | Web application, backend database, and mobile scanning clients used to track shipment and equipment assets across regional distribution hubs |
| Operating Environment | Hybrid — application and database hosted in a cloud environment; scanning clients operate on-premises at distribution hubs |

## 2. Asset Inventory

| Asset ID | Asset Name | Asset Type | Location | Criticality |
|---|---|---|---|---|
| A-001 | LATS Web Application | Software | Cloud (IaaS) | High |
| A-002 | Asset Tracking Database | Data | Cloud (IaaS) | High |
| A-003 | Handheld Barcode Scanners | Hardware | Distribution Hubs | Medium |
| A-004 | Hub Network Switches | Hardware | Distribution Hubs | Medium |
| A-005 | Shipment/Vendor Records | Data | Cloud Database | High |

## 3. Threat Identification

| Threat ID | Threat Source | Threat Event | Relevance |
|---|---|---|---|
| T-001 | External/Adversarial | Unauthorized access to the web application via compromised credentials | Confirmed |
| T-002 | Insider/Non-Adversarial | Accidental modification or deletion of shipment records by hub staff | Expected |
| T-003 | External/Adversarial | Data exfiltration of vendor and shipment records via SQL injection | Possible |
| T-004 | Environmental | Regional network outage disrupting hub scanning operations | Possible |
| T-005 | Supply Chain | Compromise via a third-party scanning-device firmware update | Possible |

## 4. Vulnerability Assessment

| Vuln ID | Vulnerability Description | Related Threat | Severity | Remediation Status |
|---|---|---|---|---|
| V-001 | No multi-factor authentication (MFA) on application admin accounts | T-001 | Critical | Open |
| V-002 | Legacy input validation allows unsanitized query parameters on the vendor search form | T-003 | High | Open |
| V-003 | Hub staff share a single generic login for the scanning application | T-002 | High | In Progress |
| V-004 | No redundant network path between hubs and the cloud environment | T-004 | Medium | Planned |
| V-005 | Scanning device firmware updates are not verified against vendor signatures | T-005 | Medium | Open |

## 5. Risk Determination

| Risk ID | Threat/Vuln Pair | Likelihood | Impact | Risk Level | Recommended Action |
|---|---|---|---|---|---|
| R-001 | T-001/V-001 | High | High | Critical | Enforce MFA on all administrative accounts within 30 days |
| R-002 | T-003/V-002 | Moderate | High | High | Remediate input validation / deploy parameterized queries within 45 days |
| R-003 | T-002/V-003 | High | Moderate | High | Issue individual user accounts to all hub staff within 60 days |
| R-004 | T-004/V-004 | Moderate | Moderate | Moderate | Evaluate secondary ISP/failover link within 90 days |
| R-005 | T-005/V-005 | Low | Moderate | Moderate | Implement firmware signature verification within 90 days |

### Risk Matrix

| | Low Impact | Moderate Impact | High Impact |
|---|---|---|---|
| **High Likelihood** | Moderate | High | Critical |
| **Moderate Likelihood** | Low | Moderate | High |
| **Low Likelihood** | Low | Low | Moderate |

## 6. Risk Response

| Risk ID | Response Strategy | Action Plan | Responsible Party | Target Date |
|---|---|---|---|---|
| R-001 | Mitigate | Enforce enterprise MFA on all admin accounts | IAM Team | 30 days from assessment date |
| R-002 | Mitigate | Refactor vendor search to use parameterized queries; add WAF rule as interim compensating control | Application Development Team | 45 days from assessment date |
| R-003 | Mitigate | Migrate shared hub login to individual, role-based accounts | IT Operations | 60 days from assessment date |
| R-004 | Mitigate | Procure and configure secondary network circuit for high-volume hubs | Network Operations | 90 days from assessment date |
| R-005 | Mitigate | Enable firmware signature verification in device management console | Logistics IT Support | 90 days from assessment date |

## 7. Approval

| Role | Name | Signature | Date |
|---|---|---|---|
| System Owner | [Sample — not signed] | | |
| ISSO | [Sample — not signed] | | |
| Authorizing Official | [Sample — not signed] | | |

---

*This is a worked example following NIST SP 800-30 Rev 1 and the NIST RMF process, built to demonstrate risk assessment methodology. See the accompanying [Sample POA&M](../poam/Sample-POAM-LATS.md) for how these findings are tracked to closure.*
