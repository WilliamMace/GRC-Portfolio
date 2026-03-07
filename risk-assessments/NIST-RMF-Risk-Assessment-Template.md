# NIST RMF Risk Assessment Template

**Document Type:** Risk Assessment
**Framework:** NIST Risk Management Framework (RMF)
**Author:** William Mace
**Date:** March 2026
**Classification:** Template / Sample

---

## 1. System Information

| Field | Details |
|---|---|
| System Name | [System Name] |
| System Owner | [Owner Name] |
| System Type | Major Application / General Support System |
| FIPS 199 Impact Level | Low / Moderate / High |
| Authorization Boundary | [Description] |
| Operating Environment | Cloud / On-Premises / Hybrid |

## 2. Asset Inventory

| Asset ID | Asset Name | Asset Type | Location | Criticality |
|---|---|---|---|---|
| A-001 | [Asset] | Hardware/Software/Data | [Location] | High/Medium/Low |
| A-002 | [Asset] | Hardware/Software/Data | [Location] | High/Medium/Low |

## 3. Threat Identification

| Threat ID | Threat Source | Threat Event | Relevance |
|---|---|---|---|
| T-001 | External/Adversarial | Unauthorized access to system | Confirmed |
| T-002 | Environmental | Natural disaster affecting data center | Possible |
| T-003 | Insider/Non-Adversarial | Accidental data disclosure | Expected |

## 4. Vulnerability Assessment

| Vuln ID | Vulnerability Description | Related Threat | Severity | Remediation Status |
|---|---|---|---|---|
| V-001 | Unpatched operating system | T-001 | High | Open |
| V-002 | Lack of MFA on admin accounts | T-001 | Critical | In Progress |
| V-003 | No offsite backup | T-002 | Medium | Planned |

## 5. Risk Determination

| Risk ID | Threat/Vuln Pair | Likelihood | Impact | Risk Level | Recommended Action |
|---|---|---|---|---|---|
| R-001 | T-001/V-001 | High | High | Critical | Apply patches within 30 days |
| R-002 | T-001/V-002 | High | High | Critical | Implement MFA immediately |
| R-003 | T-002/V-003 | Low | High | Moderate | Establish offsite backup |

### Risk Matrix

| | Low Impact | Moderate Impact | High Impact |
|---|---|---|---|
| **High Likelihood** | Moderate | High | Critical |
| **Moderate Likelihood** | Low | Moderate | High |
| **Low Likelihood** | Low | Low | Moderate |

## 6. Risk Response

| Risk ID | Response Strategy | Action Plan | Responsible Party | Target Date |
|---|---|---|---|---|
| R-001 | Mitigate | Deploy patch management solution | IT Operations | [Date] |
| R-002 | Mitigate | Deploy enterprise MFA solution | IAM Team | [Date] |
| R-003 | Mitigate | Contract with backup provider | IT Operations | [Date] |

## 7. Approval

| Role | Name | Signature | Date |
|---|---|---|---|
| System Owner | | | |
| ISSO | | | |
| Authorizing Official | | | |

---

*This template follows NIST SP 800-30 Rev 1 (Guide for Conducting Risk Assessments) and aligns with the NIST RMF process.*
