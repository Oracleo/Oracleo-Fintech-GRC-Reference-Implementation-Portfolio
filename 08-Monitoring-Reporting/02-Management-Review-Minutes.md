# Management Review Minutes – Oracleo Fintech LLC

**Meeting Date:** 01 September 2026  
**Time:** 10:00 AM – 12:00 PM IST  
**Location:** Boardroom, Bengaluru HQ (Hybrid – Teams for remote attendees)  
**Chairperson:** CISO  
**Minutes Prepared By:** Niladri Biswas, GRC Analyst  

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 1. Attendance

| Name | Role | Present |
|------|------|---------|
| [CISO] | Chief Information Security Officer | ✅ Yes |
| [CIO] | Chief Information Officer | ✅ Yes |
| [Compliance Officer] | Compliance Officer | ✅ Yes |
| [Internal Audit Director] | Internal Audit Director | ✅ Yes |
| [Head of Payments] | Head of Payments | ✅ Yes |
| [Head of Lending] | Head of Lending | ✅ Yes |
| [Head of Technology Operations] | Head of Technology Operations | ✅ Yes |
| [Data Protection Officer] | DPO | ✅ Yes |
| [GRC Lead] | GRC Lead | ✅ Yes |
| [IAM Lead] | IAM Lead | ✅ Yes |
| [AppSec Lead] | Application Security Lead | ✅ Yes |
| [Vendor Risk Manager] | Vendor Risk Manager | ✅ Yes |

---

## 2. Agenda

1. Status of actions from previous management review (May 2026)
2. Changes in internal/external context
3. Information security performance (KPIs/KRIs)
4. Compliance status (regulatory and contractual)
5. Risk assessment results
6. Incident trends
7. Audit findings
8. Resource requirements
9. Opportunities for improvement
10. Decisions and action items
11. AOB

---

## 3. Status of Actions from Previous Review (May 2026)

| Action ID | Action Description | Owner | Status | ServiceNow Task Reference | Comments |
|-----------|---------------------|-------|--------|---------------------------|----------|
| MR‑2026‑001 | Develop and deploy MFA policy for all remote access. | IAM Lead | In Progress | https://dev269444.service-now.com/task.do?sys_id=MR-001 | Pilot completed for privileged users; full rollout Q4 2026. |
| MR‑2026‑002 | Procure SAST/DAST tools for CI/CD integration. | AppSec Lead | In Progress | https://dev269444.service-now.com/task.do?sys_id=MR-002 | Tool evaluation completed; procurement in progress. |
| MR‑2026‑003 | Establish compliance register for regulatory obligations. | Compliance Officer | Not Started | https://dev269444.service-now.com/task.do?sys_id=MR-003 | Delayed due to resource constraints; now prioritised for Q4. |
| MR‑2026‑004 | Conduct first incident response tabletop exercise. | CISO | Not Started | https://dev269444.service-now.com/task.do?sys_id=MR-004 | Scheduled for October 2026. |

---

## 4. Changes in Internal/External Context

**Internal Changes:**
- Head of Payments and Head of Lending now report to the newly appointed Chief Product Officer.
- New digital banking application (v2.0) scheduled for launch in January 2027.
- Engineering team expanded by 20 members (now 100+).

**External Changes:**
- India DPDP Act compliance deadline extended to December 2026 (previously March 2026). This provides additional runway.
- RBI issued updated guidelines on data localisation for payment systems (effective October 2026).
- UK GDPR amendments post‑Brexit require updated Data Protection Impact Assessments (DPIAs).

---

## 5. Information Security Performance (KPIs/KRIs)

> Refer to **KPI/KRI Dashboard (DASH‑001)** for full detail. Summary below.

| Metric | Target | Current | Status | Trend | ServiceNow Reference |
|--------|--------|---------|--------|-------|---------------------|
| Control Implementation | 90% | 65% | 🟡 | Improving | https://dev269444.service-now.com/dashboard/control |
| Critical Vulnerability Remediation | ≤7 days | 12 days | 🔴 | Worsening | https://dev269444.service-now.com/dashboard/vuln |
| Access Recertification Completion | 100% | 75% | 🟡 | Stable | https://dev269444.service-now.com/dashboard/access |
| Open Critical Risks | ≤3 | 2 | 🟡 | Stable | https://dev269444.service-now.com/dashboard/risk |
| Open High Risks | ≤5 | 4 | 🟢 | Improving | https://dev269444.service-now.com/dashboard/risk |
| Regulatory Compliance Score | ≥90% | 78% | 🔴 | Stable | https://dev269444.service-now.com/dashboard/compliance |
| Phishing Click Rate | ≤5% | 12% | 🔴 | Worsening | https://dev269444.service-now.com/dashboard/phishing |

**CISO Commentary:**
- Critical vulnerability remediation time has increased from 9 days to 12 days. This requires immediate attention.
- Phishing click rate remains a concern; additional training and simulated phishing campaigns scheduled.
- Overall control implementation is progressing but slower than planned.

---

## 6. Compliance Status

| Framework | Progress | Status | Comment |
|-----------|----------|--------|---------|
| ISO/IEC 27001:2022 | 65% | 🟡 | Gap remediation on track; target certification Q3 2027. |
| PCI DSS 4.0 | 55% | 🔴 | Significant gaps remain; need dedicated resource allocation. |
| India DPDP Act | 60% | 🔴 | Consent management platform required; procurement in progress. |
| GDPR (UK/EU) | 75% | 🟡 | DPIAs for new applications required. |
| RBI Cyber Security Guidelines | 70% | 🟡 | Data localisation compliance underway. |

**Compliance Officer Comment:**
- DPDP Act compliance is now the top priority. Consent management platform procurement must be accelerated.
- PCI DSS remediation requires dedicated engineering resource. Recommend creating a PCI working group.

---

## 7. Risk Assessment Results

> Refer to **Risk Register (02-Risk-Management/02-Risk-Register.csv)** for full detail.

**Top 5 Risks:**

| Risk ID | Description | Rating | Treatment | Status | ServiceNow Risk Reference |
|---------|-------------|--------|-----------|--------|---------------------------|
| R‑001 | Unauthorised access to PII | Critical | Reduce | In Progress | https://dev269444.service-now.com/risk.do?sys_id=R-001 |
| R‑006 | SQL Injection in customer portal | Critical | Reduce | In Progress | https://dev269444.service-now.com/risk.do?sys_id=R-006 |
| R‑003 | DPDP Non‑compliance | High | Reduce | In Progress | https://dev269444.service-now.com/risk.do?sys_id=R-003 |
| R‑009 | PCI DSS Gap | High | Reduce | In Progress | https://dev269444.service-now.com/risk.do?sys_id=R-009 |
| R‑004 | Insider Threat | High | Reduce | Open | https://dev269444.service-now.com/risk.do?sys_id=R-004 |

**Risk Manager Comment:**
- Two Critical risks remain open. Remediation plans are in place.
- No new risks identified this quarter.
- Risk appetite for Critical risks requires escalation to the Board.

---

## 8. Incident Trends

| Incident Type | Q1 2026 | Q2 2026 | Q3 2026 (YTD) | Trend |
|---------------|---------|---------|---------------|-------|
| Phishing (Reported) | 12 | 18 | 15 | Increasing |
| Malware Detections | 8 | 6 | 4 | Decreasing |
| Unauthorised Access Attempts | 45 | 38 | 29 | Decreasing |
| DDoS Attempts | 3 | 2 | 1 | Decreasing |
| User‑Reported Incidents | 22 | 28 | 31 | Increasing |

**SOC Lead Comment:**
- Phishing incidents are increasing; user awareness training needs to be intensified.
- User‑reported incidents are up, which indicates improved reporting culture.
- No breaches or major security events this quarter.

---

## 9. Audit Findings

**Internal Audit (June 2026):**

| Finding ID | Finding | Severity | Status | ServiceNow Issue Reference |
|------------|---------|----------|--------|---------------------------|
| IA‑2026‑001 | Access reviews not documented for Q2 2026. | High | In Progress | https://dev269444.service-now.com/issue.do?sys_id=IA-001 |
| IA‑2026‑002 | Patch management process not followed for 15% of servers. | Medium | In Progress | https://dev269444.service-now.com/issue.do?sys_id=IA-002 |
| IA‑2026‑003 | Security awareness training completion not tracked. | Low | Closed | https://dev269444.service-now.com/issue.do?sys_id=IA-003 |

**External Audit (None this quarter):**

No external audits conducted in Q3 2026. Next scheduled ISO 27001 stage 1 audit: Q1 2027.

---

## 10. Resource Requirements

**Immediate Needs (Q3‑Q4 2026):**

| Resource | Requirement | Justification | Cost Estimate |
|----------|-------------|---------------|---------------|
| Consent Management Platform | OneTrust or equivalent | Required for DPDP and GDPR compliance. | ₹15L ($18K) |
| SAST/DAST Tools | Integrated into CI/CD | Required for application security and PCI compliance. | ₹20L ($25K) |
| Additional SOC Analyst | 1 FTE | Manage SIEM tuning and incident response. | ₹12L ($15K) annually |
| Security Awareness Platform | Phishing simulation and training | Address high phishing click rate. | ₹5L ($6K) |

**Approval:**
- Budget request approved for consent management platform and SAST/DAST tools.
- SOC Analyst request deferred to Q1 2027 for review.

---

## 11. Opportunities for Improvement

1. **Automate access recertification** – Currently manual; ServiceNow module can automate.
2. **Integrate SAST/DAST into CI/CD** – Will reduce vulnerability remediation time significantly.
3. **Implement vendor continuous monitoring** – Currently annual only; quarterly monitoring would reduce vendor risk.
4. **Enhance phishing simulation programme** – Monthly campaigns with targeted training for repeat clickers.

---

## 12. Decisions Made

| Decision ID | Decision | Rationale | Approved By | ServiceNow Reference |
|-------------|----------|-----------|-------------|---------------------|
| MR‑2026‑D001 | Expedite consent management platform procurement (OneTrust). | Critical for DPDP compliance; target go‑live Q1 2027. | CISO, CFO | https://dev269444.service-now.com/task.do?sys_id=D001 |
| MR‑2026‑D002 | Establish PCI DSS working group with dedicated engineering resource. | PCI gaps are significant; dedicated focus is required. | Security Steering Committee | https://dev269444.service-now.com/task.do?sys_id=D002 |
| MR‑2026‑D003 | Increase phishing simulation frequency from quarterly to monthly. | Phishing click rate is worsening; more frequent training is needed. | CISO | https://dev269444.service-now.com/task.do?sys_id=D003 |
| MR‑2026‑D004 | Escalate R‑001 and R‑006 to the Board for risk acceptance. | Residual risk remains Critical; Board must formally accept or approve additional funding. | CISO | https://dev269444.service-now.com/task.do?sys_id=D004 |
| MR‑2026‑D005 | Allocate ₹10L for additional security awareness training platform. | Improve phishing resilience and overall security culture. | Steering Committee | https://dev269444.service-now.com/task.do?sys_id=D005 |

---

## 13. Action Items

| Action ID | Action Description | Owner | Deadline | Status | ServiceNow Task Reference |
|-----------|---------------------|-------|----------|--------|---------------------------|
| MR‑2026‑A001 | Finalise consent management platform procurement (OneTrust). | DPO | 30 Sep 2026 | In Progress | https://dev269444.service-now.com/task.do?sys_id=A001 |
| MR‑2026‑A002 | Form PCI DSS working group and schedule first meeting. | Compliance Officer | 30 Sep 2026 | Not Started | https://dev269444.service-now.com/task.do?sys_id=A002 |
| MR‑2026‑A003 | Increase phishing simulation frequency to monthly. | Security Awareness | 1 Oct 2026 | Not Started | https://dev269444.service-now.com/task.do?sys_id=A003 |
| MR‑2026‑A004 | Prepare Board pack for R‑001 and R‑006 escalation. | CISO | 30 Sep 2026 | In Progress | https://dev269444.service-now.com/task.do?sys_id=A004 |
| MR‑2026‑A005 | Procure security awareness training platform. | Security Awareness | 31 Oct 2026 | Not Started | https://dev269444.service-now.com/task.do?sys_id=A005 |
| MR‑2026‑A006 | Update PCI DSS remediation plan with dedicated resources. | Compliance Officer | 30 Sep 2026 | Not Started | https://dev269444.service-now.com/task.do?sys_id=A006 |

---

## 14. Any Other Business (AOB)

- Next management review scheduled for **01 December 2026**.
- CISO requested all action items be updated in ServiceNow for tracking.
- Meeting adjourned at 11:50 AM IST.

---

## 15. ServiceNow Integration

All management review action items are tracked in ServiceNow:

| Activity | ServiceNow Reference |
|----------|---------------------|
| Action item list | https://dev269444.service-now.com/task |
| Dashboard | https://dev269444.service-now.com/dashboard/mr |
| Minutes and records | https://dev269444.service-now.com/meeting |

---

## 16. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial release | CISO |

---

## 17. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Dashboard | KPI/KRI Dashboard | DASH‑001 |
| Register | Risk Register | – |
| Report | Gap Assessment Report | GAP‑001 |
| Plan | Corrective Action Plan | CAP‑001 |

---

**End of Minutes**
