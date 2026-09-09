# Incident Response Plan — Logistics Asset Tracking System (LATS)

**Document Type:** Incident Response Plan
**Framework:** NIST SP 800-61 Rev 2 (Computer Security Incident Handling Guide)
**Author:** William Mace
**Date:** September 2026
**Classification:** Sample / Illustrative — built for the fictional LATS system introduced in the [Sample Risk Assessment](../risk-assessments/Sample-Risk-Assessment-LATS.md).

---

## 1. Purpose and Scope

This plan defines how the LATS support team detects, responds to, and recovers from security incidents affecting the application, database, and distribution-hub scanning infrastructure. It applies to all LATS system components identified in the system's authorization boundary.

## 2. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| Incident Response Lead | Coordinates overall response, declares incident severity, communicates with the Authorizing Official |
| ISSO | Confirms security control impact, documents the incident for RMF continuous monitoring records |
| IT Operations | Executes containment and recovery actions on affected systems |
| Application Development Team | Investigates and remediates application-layer causes (e.g., injection vulnerabilities) |
| Logistics Operations Division | Business owner point of contact; assesses operational impact to hub activity |
| Communications/Legal | Manages any required breach notification obligations |

## 3. Incident Classification

| Severity | Definition | Example |
|---|---|---|
| Critical | Confirmed unauthorized access or data exfiltration affecting shipment/vendor records | Exploited SQL injection resulting in database access |
| High | Active exploitation attempt or confirmed compromise of a single account/device | Compromised hub scanning-device credentials |
| Moderate | Suspicious activity requiring investigation but no confirmed compromise | Repeated failed admin logins from unusual location |
| Low | Policy violation or minor anomaly with no security impact | Isolated user error, non-security related outage |

## 4. Incident Response Lifecycle

### 4.1 Preparation
- Maintain updated asset inventory and network diagrams for LATS (see [Home-Lab](https://github.com/WilliamMace/Home-Lab) for supporting lab documentation practices).
- Ensure logging is enabled on the web application, database, and hub network switches, with retention sufficient for post-incident analysis.
- Maintain current contact list for the Incident Response Lead, ISSO, IT Operations, and Application Development Team.

### 4.2 Detection and Analysis
- Monitor authentication logs for anomalous admin login patterns (tied to POAM-001 in the [Sample POA&M](../poam/Sample-POAM-LATS.md)).
- Monitor database query logs for injection-pattern anomalies (tied to POAM-002).
- Triage alerts against the severity table in Section 3 and assign an incident ticket.

### 4.3 Containment
- **Short-term:** Disable the affected account or isolate the affected hub device/network segment; apply or verify the WAF rule blocking known injection patterns.
- **Long-term:** Rotate credentials for all accounts with equivalent access; patch or reconfigure the exploited vulnerability before restoring full access.

### 4.4 Eradication
- Remove any unauthorized access mechanism (e.g., web shells, rogue accounts, malicious firmware).
- Confirm the root-cause vulnerability is remediated (cross-reference the relevant POA&M item) before returning the system to normal operation.

### 4.5 Recovery
- Restore affected systems from known-good backups or configurations.
- Re-enable access incrementally, monitoring closely for recurrence.
- Confirm with the Logistics Operations Division that hub scanning operations are fully restored.

### 4.6 Post-Incident Activity
- Complete a lessons-learned review within 5 business days of incident closure.
- Update the risk assessment and POA&M with any new or accelerated remediation items.
- Report the incident and resolution to the Authorizing Official as part of continuous monitoring.

## 5. Communication Plan

| Trigger | Notify | Timeframe |
|---|---|---|
| Critical or High severity declared | Incident Response Lead, ISSO, Authorizing Official | Within 1 hour of declaration |
| Confirmed data exposure involving vendor/shipment records | Legal/Communications for breach-notification assessment | Within 24 hours |
| Incident closed | All stakeholders, with summary and POA&M updates | Within 5 business days |

## 6. Approval

| Role | Name | Signature | Date |
|---|---|---|---|
| System Owner | [Sample — not signed] | | |
| ISSO | [Sample — not signed] | | |
| Authorizing Official | [Sample — not signed] | | |

---

*This is a worked example following NIST SP 800-61 Rev 2, built to demonstrate incident response planning tied to the risk assessment and POA&M artifacts in this portfolio.*
