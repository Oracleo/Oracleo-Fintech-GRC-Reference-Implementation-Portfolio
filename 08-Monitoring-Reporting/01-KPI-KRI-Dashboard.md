# KPI/KRI Dashboard – Oracleo Fintech LLC

**Document ID:** DASH‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Next Review Date:** 01 March 2027  
**Owner:** GRC Lead  
**Approved By:** CISO  

---

## 1. Purpose

This document defines the key performance indicators (KPIs) and key risk indicators (KRIs) used to measure and monitor the effectiveness of the Information Security Management System (ISMS) at Oracleo Fintech LLC. Metrics are presented to the Security Steering Committee monthly and to the Board quarterly.

All metrics are visualised in **ServiceNow Dashboards**:

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. KPI Definitions (Security Programme Effectiveness)

| KPI ID | KPI Name | Definition | Target | Current | Status | Frequency | Owner | ServiceNow Dashboard |
|--------|----------|------------|--------|---------|--------|-----------|-------|---------------------|
| KPI‑001 | Control Implementation | Percentage of applicable controls fully implemented | 90% | 65% | 🟡 Yellow | Monthly | GRC Lead | https://dev269444.service-now.com/dashboard/control |
| KPI‑002 | Vulnerability Remediation (Critical) | Average time to remediate Critical vulnerabilities | ≤7 days | 12 days | 🔴 Red | Monthly | AppSec Lead | https://dev269444.service-now.com/dashboard/vuln |
| KPI‑003 | Vulnerability Remediation (High) | Average time to remediate High vulnerabilities | ≤30 days | 25 days | 🟢 Green | Monthly | AppSec Lead | https://dev269444.service-now.com/dashboard/vuln |
| KPI‑004 | Access Recertification | Percentage of access reviews completed on time | 100% | 75% | 🟡 Yellow | Quarterly | IAM Lead | https://dev269444.service-now.com/dashboard/access |
| KPI‑005 | Policy Acknowledgment | Percentage of employees who have acknowledged ISMS policies | 100% | 92% | 🟡 Yellow | Monthly | CISO | https://dev269444.service-now.com/dashboard/policy |
| KPI‑006 | Incident Response Time | Average time from detection to containment (Critical incidents) | ≤2 hours | 3.5 hours | 🔴 Red | Monthly | SOC Lead | https://dev269444.service-now.com/dashboard/incident |
| KPI‑007 | Security Awareness Training | Percentage of employees who completed annual training | 100% | 88% | 🟡 Yellow | Quarterly | Security Awareness | https://dev269444.service-now.com/dashboard/training |
| KPI‑008 | Audit Finding Closure | Percentage of audit findings closed within target | 95% | 70% | 🔴 Red | Monthly | GRC Lead | https://dev269444.service-now.com/dashboard/audit |

---

## 3. KRI Definitions (Risk Exposure Indicators)

| KRI ID | KRI Name | Definition | Threshold (Red) | Threshold (Yellow) | Current | Status | Frequency | Owner | ServiceNow Dashboard |
|--------|----------|------------|-----------------|-------------------|---------|--------|-----------|-------|---------------------|
| KRI‑001 | Critical Risks Open | Number of open risks rated Critical | >3 | 1–3 | 2 | 🟡 Yellow | Monthly | Risk Manager | https://dev269444.service-now.com/dashboard/risk |
| KRI‑002 | High Risks Open | Number of open risks rated High | >10 | 5–10 | 4 | 🟢 Green | Monthly | Risk Manager | https://dev269444.service-now.com/dashboard/risk |
| KRI‑003 | Vendors with High/ Critical Risk | Percentage of vendors with residual risk >12 | >20% | 10–20% | 15% | 🟡 Yellow | Quarterly | Vendor Risk Mgr | https://dev269444.service-now.com/dashboard/vendor |
| KRI‑004 | Systems with Critical Vulnerabilities | Percentage of systems with Critical vulnerabilities unpatched >7 days | >5% | 2–5% | 8% | 🔴 Red | Monthly | AppSec Lead | https://dev269444.service-now.com/dashboard/vuln |
| KRI‑005 | Regulatory Compliance Score | Percentage of compliance obligations met | <80% | 80–90% | 78% | 🔴 Red | Monthly | Compliance Officer | https://dev269444.service-now.com/dashboard/compliance |
| KRI‑006 | Privileged Users | Number of users with privileged access | >50 | 30–50 | 32 | 🟢 Green | Monthly | IAM Lead | https://dev269444.service-now.com/dashboard/access |
| KRI‑007 | Unresolved Audit Findings | Number of audit findings >60 days overdue | >5 | 2–5 | 3 | 🟡 Yellow | Monthly | GRC Lead | https://dev269444.service-now.com/dashboard/audit |
| KRI‑008 | Failed Access Attempts | Number of failed access attempts per week | >1,000 | 500–1,000 | 850 | 🟡 Yellow | Weekly | SOC Lead | https://dev269444.service-now.com/dashboard/siem |
| KRI‑009 | Phishing Click Rate | Percentage of employees who click on simulated phishing emails | >10% | 5–10% | 12% | 🔴 Red | Quarterly | Security Awareness | https://dev269444.service-now.com/dashboard/phishing |
| KRI‑010 | Compliance Audit Findings | Number of findings from external compliance audits | >5 | 2–5 | 0 | 🟢 Green | Annually | Compliance Officer | https://dev269444.service-now.com/dashboard/audit |

---

## 4. RAG Status Definitions

| Status | Definition | Action Required |
|--------|------------|-----------------|
| 🟢 **Green** | Within target or acceptable threshold | Continue monitoring; no action required. |
| 🟡 **Yellow** | Approaching target threshold; above target but not critical | Investigate root cause; develop improvement plan; escalate to CISO if trend continues. |
| 🔴 **Red** | Outside acceptable threshold; requires immediate attention | Escalate to CISO; develop and execute remediation plan within 7 days; report to Steering Committee. |

---

## 5. Sample Dashboard Layout (Mockup)
