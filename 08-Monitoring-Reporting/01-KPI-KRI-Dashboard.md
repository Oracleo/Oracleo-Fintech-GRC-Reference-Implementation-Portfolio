# KPI/KRI Dashboard – Oracleo Fintech LLC

| **Document Information** | |
|--------------------------|------------------------------------------------|
| **Document ID** | DASH-001 |
| **Version** | 1.0 |
| **Effective Date** | 01 September 2026 |
| **Next Review Date** | 01 March 2027 |
| **Document Owner** | GRC Lead |
| **Approved By** | CISO |
| **Classification** | Internal |
| **Status** | Approved |

---

# 1. Purpose

This document defines the **Key Performance Indicators (KPIs)** and **Key Risk Indicators (KRIs)** used to measure, monitor, and report the effectiveness of the Information Security Management System (ISMS) at **Oracleo Fintech LLC**.

The dashboard enables executive management, the Security Steering Committee, and the Board of Directors to monitor security performance, identify emerging risks, and support risk-based decision-making.

Dashboard metrics are reviewed according to the governance schedule below:

- **Monthly:** Security Steering Committee
- **Quarterly:** Board of Directors
- **Annually:** Strategic Security Review

---

# 2. Dashboard Platform

**ServiceNow Instance**

https://dev269444.service-now.com

All KPI and KRI data is visualised using ServiceNow dashboards and populated from integrated security and compliance modules.

---

# 3. Key Performance Indicators (KPIs)

| KPI ID | KPI Name | Definition | Target | Current | Status | Frequency | Owner | Dashboard |
|--------|----------|------------|--------|---------|--------|-----------|-------|-----------|
| KPI-001 | Control Implementation | Percentage of applicable controls fully implemented | 90% | 65% | 🟡 Yellow | Monthly | GRC Lead | https://dev269444.service-now.com/dashboard/control |
| KPI-002 | Critical Vulnerability Remediation | Average time to remediate Critical vulnerabilities | ≤ 7 Days | 12 Days | 🔴 Red | Monthly | AppSec Lead | https://dev269444.service-now.com/dashboard/vuln |
| KPI-003 | High Vulnerability Remediation | Average remediation time for High vulnerabilities | ≤ 30 Days | 25 Days | 🟢 Green | Monthly | AppSec Lead | https://dev269444.service-now.com/dashboard/vuln |
| KPI-004 | Access Recertification | Percentage of user access reviews completed on time | 100% | 75% | 🟡 Yellow | Quarterly | IAM Lead | https://dev269444.service-now.com/dashboard/access |
| KPI-005 | Policy Acknowledgement | Percentage of employees acknowledging security policies | 100% | 92% | 🟡 Yellow | Monthly | CISO | https://dev269444.service-now.com/dashboard/policy |
| KPI-006 | Incident Response Time | Average time from detection to containment (Critical incidents) | ≤ 2 Hours | 3.5 Hours | 🔴 Red | Monthly | SOC Lead | https://dev269444.service-now.com/dashboard/incident |
| KPI-007 | Security Awareness Training | Employees completing annual security awareness training | 100% | 88% | 🟡 Yellow | Quarterly | Security Awareness Manager | https://dev269444.service-now.com/dashboard/training |
| KPI-008 | Audit Finding Closure | Percentage of audit findings closed within SLA | 95% | 70% | 🔴 Red | Monthly | GRC Lead | https://dev269444.service-now.com/dashboard/audit |

---

# 4. Key Risk Indicators (KRIs)

| KRI ID | KRI Name | Definition | Red Threshold | Yellow Threshold | Current | Status | Frequency | Owner | Dashboard |
|--------|----------|------------|---------------|------------------|---------|--------|-----------|-------|-----------|
| KRI-001 | Critical Risks Open | Number of Critical risks currently open | > 3 | 1–3 | 2 | 🟡 Yellow | Monthly | Risk Manager | https://dev269444.service-now.com/dashboard/risk |
| KRI-002 | High Risks Open | Number of High risks currently open | > 10 | 5–10 | 4 | 🟢 Green | Monthly | Risk Manager | https://dev269444.service-now.com/dashboard/risk |
| KRI-003 | High-Risk Vendors | Vendors with residual risk score above 12 | > 20% | 10–20% | 15% | 🟡 Yellow | Quarterly | Vendor Risk Manager | https://dev269444.service-now.com/dashboard/vendor |
| KRI-004 | Systems with Critical Vulnerabilities | Systems containing Critical vulnerabilities older than seven days | > 5% | 2–5% | 8% | 🔴 Red | Monthly | AppSec Lead | https://dev269444.service-now.com/dashboard/vuln |
| KRI-005 | Regulatory Compliance Score | Percentage of regulatory obligations satisfied | < 80% | 80–90% | 78% | 🔴 Red | Monthly | Compliance Officer | https://dev269444.service-now.com/dashboard/compliance |
| KRI-006 | Privileged Users | Number of privileged accounts | > 50 | 30–50 | 32 | 🟢 Green | Monthly | IAM Lead | https://dev269444.service-now.com/dashboard/access |
| KRI-007 | Overdue Audit Findings | Audit findings overdue by more than 60 days | > 5 | 2–5 | 3 | 🟡 Yellow | Monthly | GRC Lead | https://dev269444.service-now.com/dashboard/audit |
| KRI-008 | Failed Access Attempts | Failed authentication attempts per week | > 1,000 | 500–1,000 | 850 | 🟡 Yellow | Weekly | SOC Lead | https://dev269444.service-now.com/dashboard/siem |
| KRI-009 | Phishing Click Rate | Employees clicking simulated phishing emails | > 10% | 5–10% | 12% | 🔴 Red | Quarterly | Security Awareness Manager | https://dev269444.service-now.com/dashboard/phishing |
| KRI-010 | External Compliance Findings | Findings identified during external audits | > 5 | 2–5 | 0 | 🟢 Green | Annual | Compliance Officer | https://dev269444.service-now.com/dashboard/audit |

---

# 5. RAG Status Definitions

| Status | Meaning | Required Action |
|---------|---------|-----------------|
| 🟢 Green | Performance is within target or acceptable risk threshold. | Continue monitoring. |
| 🟡 Yellow | Performance is approaching threshold or below target. | Investigate root cause, define improvement plan, monitor closely, escalate if trend continues. |
| 🔴 Red | Performance exceeds acceptable risk tolerance. | Immediate management attention required. Escalate to CISO, create remediation plan within seven days, report to Security Steering Committee. |

---

# 6. Executive Dashboard (Mock Layout)

```text
┌───────────────────────────────────────────────────────────────────────────────┐
│                    ORACLEO FINTECH LLC – SECURITY DASHBOARD                   │
│                         Reporting Date: 01 September 2026                     │
│              ServiceNow: https://dev269444.service-now.com                    │
├───────────────────────────────────────────────────────────────────────────────┤
│                                                                               │
│ OVERALL SECURITY POSTURE                                                      │
│                                                                               │
│ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐             │
│ │Controls  │ │ Risks    │ │ Vendors  │ │ Audit    │ │Incidents │             │
│ │65% 🟡    │ │2 Crit🟡  │ │15% 🟡    │ │3 Open🟡  │ │2 Open🟢  │             │
│ └──────────┘ └──────────┘ └──────────┘ └──────────┘ └──────────┘             │
│                                                                               │
├───────────────────────────────────────────────────────────────────────────────┤
│ TOP 5 OPEN RISKS                                                              │
│                                                                               │
│ 1. R-001  Unauthorised Access to PII          Critical   IAM Lead             │
│ 2. R-006  SQL Injection                       Critical   AppSec Lead          │
│ 3. R-003  DPDP Non-Compliance                 High       DPO                  │
│ 4. R-009  PCI DSS Gap                         High       Compliance Officer   │
│ 5. R-004  Insider Threat                      High       HR                  │
│                                                                               │
├───────────────────────────────────────────────────────────────────────────────┤
│ COMPLIANCE STATUS                                                             │
│                                                                               │
│ Framework            Progress      Status      Open Gaps                      │
│ ---------------------------------------------------------------------------   │
│ ISO 27001              65%           🟡            5                           │
│ PCI DSS 4.0            55%           🔴            8                           │
│ DPDP Act               60%           🔴            4                           │
│ GDPR                   75%           🟡            3                           │
│ RBI Guidelines         70%           🟡            3                           │
│                                                                               │
├───────────────────────────────────────────────────────────────────────────────┤
│ KEY METRIC TRENDS                                                             │
│                                                                               │
│ Critical Vulnerability Remediation : 12 Days (Target 7)       🔴              │
│ Access Recertification             : 75% (Target 100%)        🟡              │
│ High-Risk Vendors                  : 15% (Target <10%)        🟡              │
│ Phishing Click Rate                : 12% (Target <5%)         🔴              │
│                                                                               │
├───────────────────────────────────────────────────────────────────────────────┤
│ CISO COMMENTARY                                                               │
│                                                                               │
│ Two Critical risks remain open (R-001 and R-006).                             │
│ Mitigation activities are progressing with planned closure in Q4 2026.        │
│ PCI DSS and DPDP compliance require additional focus.                         │
│ Phishing click rate remains above tolerance; mandatory awareness training     │
│ has been scheduled for October 2026.                                          │
│                                                                               │
└───────────────────────────────────────────────────────────────────────────────┘
```

---

# 7. Dashboard Refresh Schedule

| Frequency | Activity | Owner |
|-----------|----------|-------|
| Daily | Automated SIEM, vulnerability and control data synchronisation to ServiceNow | SOC Lead |
| Weekly | Review Failed Access Attempts KRI | SOC Lead |
| Monthly | Review and update all KPIs and KRIs; Security Steering Committee reporting | GRC Lead |
| Quarterly | Update Vendor Risk, Compliance Score and Phishing Metrics; Board reporting | GRC Lead, Compliance Officer |
| Annually | Review KPI/KRI definitions, thresholds and targets | CISO |

---

# 8. ServiceNow Integration

| Metric Category | ServiceNow Module | Reference |
|-----------------|------------------|-----------|
| Control Implementation | Control Library | https://dev269444.service-now.com/control |
| Enterprise Risks | Risk Management | https://dev269444.service-now.com/risk |
| Vendor Risk | Vendor Risk Management | https://dev269444.service-now.com/vendor |
| Audit Findings | Audit Management | https://dev269444.service-now.com/audit |
| Vulnerability Management | Qualys Integration | https://dev269444.service-now.com/vuln |
| Policy Acknowledgement | Policy & Compliance | https://dev269444.service-now.com/policy |
| Security Incidents | Security Incident Response | https://dev269444.service-now.com/incident |
| SIEM Metrics | Security Operations | https://dev269444.service-now.com/siem |

---

# 9. Document Control

| Version | Date | Author | Description | Approver |
|---------|------|--------|-------------|----------|
| 1.0 | 01 September 2026 | Niladri Biswas | Initial Release | CISO |

---

# 10. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Register | Enterprise Risk Register | RISK-001 |
| Register | Asset Register | AST-001 |
| Register | Vendor Register | VEN-001 |
| Register | Audit Register | AUD-001 |
| Library | Security Control Library | CTRL-001 |
| Report | ISMS Gap Assessment Report | GAP-001 |
| Plan | Corrective Action Plan | CAP-001 |
| Policy | Information Security Policy | POL-001 |
| Standard | Risk Management Standard | STD-001 |

---

# End of Document
