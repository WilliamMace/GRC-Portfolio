# Sample Plan of Action and Milestones (POA&M) — Logistics Asset Tracking System (LATS)

**Document Type:** Plan of Action and Milestones (POA&M)
**Framework:** NIST SP 800-53 Rev 5 / NIST RMF
**Author:** William Mace
**Date:** September 2026
**Classification:** Sample / Illustrative — tracks remediation of findings from the [Sample Risk Assessment](../risk-assessments/Sample-Risk-Assessment-LATS.md) for the fictional LATS system.

---

## POA&M Register

| POA&M ID | Weakness Description | Source | Control(s) Affected | Risk Level | Point of Contact | Resources Required | Scheduled Completion | Status |
|---|---|---|---|---|---|---|---|---|
| POAM-001 | Administrative accounts lack multi-factor authentication | Risk Assessment R-001 | IA-2(1) | Critical | IAM Team Lead | Enterprise MFA licensing, 8 staff hours | 30 days from assessment date | Open |
| POAM-002 | Vendor search form vulnerable to SQL injection due to unsanitized input | Risk Assessment R-002 | SI-10, SC-7 | High | Application Dev Lead | Developer time (2 sprints), WAF rule update | 45 days from assessment date | Open |
| POAM-003 | Hub staff share a single generic scanning-application login | Risk Assessment R-003 | AC-2, IA-2 | High | IT Operations Manager | Identity provisioning for ~40 hub users | 60 days from assessment date | In Progress |
| POAM-004 | No redundant network path between distribution hubs and cloud environment | Risk Assessment R-004 | CP-8, SC-7 | Moderate | Network Operations Manager | Secondary ISP contract, router configuration | 90 days from assessment date | Planned |
| POAM-005 | Scanning device firmware updates not verified against vendor signatures | Risk Assessment R-005 | SI-7, CM-3 | Moderate | Logistics IT Support Lead | Device management console configuration | 90 days from assessment date | Open |

## Milestone Detail

### POAM-001 — MFA on Administrative Accounts
- Milestone 1 (Day 10): Select and procure enterprise MFA solution compatible with existing identity provider.
- Milestone 2 (Day 20): Pilot MFA enrollment with IT Operations admin group.
- Milestone 3 (Day 30): Enforce MFA org-wide for all LATS administrative roles; close POA&M upon verification.

### POAM-002 — SQL Injection Remediation
- Milestone 1 (Day 15): Deploy interim WAF rule blocking known SQL injection patterns on the vendor search endpoint.
- Milestone 2 (Day 35): Refactor vendor search query logic to use parameterized queries.
- Milestone 3 (Day 45): Complete regression and penetration testing on the fix; close POA&M upon verification.

### POAM-003 — Individual Hub User Accounts
- Milestone 1 (Day 20): Inventory all hub staff requiring scanning-application access.
- Milestone 2 (Day 45): Provision individual, role-based accounts and disable the shared generic login.
- Milestone 3 (Day 60): Confirm audit logging captures individual user activity; close POA&M upon verification.

### POAM-004 — Network Redundancy
- Milestone 1 (Day 30): Evaluate secondary ISP options for high-volume distribution hubs.
- Milestone 2 (Day 60): Contract and install secondary circuit at the pilot hub.
- Milestone 3 (Day 90): Validate automatic failover; close POA&M upon verification.

### POAM-005 — Firmware Signature Verification
- Milestone 1 (Day 30): Confirm device management console supports signature verification.
- Milestone 2 (Day 60): Enable and test signature verification in a staging environment.
- Milestone 3 (Day 90): Roll out to all production scanning devices; close POA&M upon verification.

---

*This is a worked example following NIST SP 800-53 Rev 5 remediation tracking practices, built to demonstrate how risk assessment findings are converted into a managed POA&M with milestones and accountable owners.*
