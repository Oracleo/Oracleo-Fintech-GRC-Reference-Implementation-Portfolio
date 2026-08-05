# Gap Assessment Report – Oracleo Fintech LLC

**Document ID:** GAP‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Next Review Date:** 01 March 2027  
**Owner:** GRC Lead  
**Approved By:** CISO  

---

## 1. Executive Summary

Oracleo Fintech LLC conducted a comprehensive gap assessment against **ISO/IEC 27001:2022**, **NIST CSF 2.0**, **PCI DSS 4.0**, **GDPR**, **India DPDP Act**, and **RBI Cyber Security Guidelines** as of August 2026. The assessment identified **nine (9) material gaps** across access control, application security, vendor management, compliance monitoring, and incident response readiness. Four gaps are classified as **Critical**, three as **High**, and two as **Medium**.

All gaps are recorded as **Issues** in ServiceNow and linked to the remediation plan.

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. Assessment Scope

| Framework/Regulation | Scope | Status |
|----------------------|-------|--------|
| ISO/IEC 27001:2022 | All Annex A controls and management system requirements (Clauses 4–10) | In Progress |
| NIST CSF 2.0 | All five functions (Govern, Identify, Protect, Detect, Respond, Recover) | In Progress |
| PCI DSS 4.0 | Cardholder data environment (payment gateway, merchant dashboard) | Partially Assessed |
| GDPR | Data processing of EU/UK personal data | Partially Assessed |
| India DPDP Act | All processing of Indian personal data | Partially Assessed |
| RBI Cyber Security Guidelines | All applicable guidelines for Indian fintech operations | Partially Assessed |

---

## 3. Methodology

The gap assessment was conducted using the following approach:

1. **Asset Review** – Mapped asset register to control requirements.
2. **Control Library Assessment** – Compared current implementation status (as recorded in the Control Library) against target requirements.
3. **Regulatory Mappings** – Verified that mapped controls meet each regulatory obligation.
4. **Interviews** – Conducted interviews with key process owners (IAM Lead, AppSec Lead, Vendor Risk Manager, DPO).
5. **Evidence Review** – Examined available evidence (policies, logs, test results) to confirm actual compliance.

---

## 4. Gap Summary Table

| Area | Current State | Target State | Gap Severity | Root Cause | Remediation Priority | Owner |
|------|---------------|--------------|--------------|------------|----------------------|-------|
| **Access Control** | MFA partially enforced (privileged only) | MFA enforced for all remote access and privileged accounts | **Critical** | Phased rollout, lack of policy enforcement | P1 | IAM Lead |
| **Access Control** | Quarterly access reviews are manual, incomplete | Automated, auditable recertification | **High** | Process gaps, lack of tooling | P2 | IAM Lead |
| **Application Security** | SAST/DAST not integrated into CI/CD pipeline | Full integration with automated security gates | **Critical** | Tooling procurement in progress | P1 | AppSec Lead |
| **Application Security** | No formal threat modelling for new applications | Structured threat modelling at design phase | **High** | Lack of awareness and resources | P2 | AppSec Lead |
| **Vendor Management** | No continuous monitoring of vendor security posture | Annual reassessments and incident monitoring | **Medium** | Manual processes, no automation | P3 | Vendor Risk Mgr |
| **Compliance Monitoring** | No centralised compliance register or gap tracking | Centralised register with automated gap analysis | **Critical** | No GRC process for regulatory changes | P1 | Compliance Officer |
| **Incident Response** | No tabletop exercises conducted in the last 12 months | Annual tabletop exercises with post‑mortem | **High** | Resource constraints, scheduling issues | P2 | CISO |
| **Data Protection (DPDP/GDPR)** | Consent management not fully automated | Automated consent capture, modification, and withdrawal | **Critical** | Awaiting platform implementation | P1 | DPO |
| **Logging & Monitoring** | SIEM alerts not fully tuned; false positives high | Tuned alerting with defined playbooks | **Medium** | Manual tuning, lack of SOC resources | P3 | SOC Lead |

---

## 5. Detailed Findings

### Finding 1: MFA Enforcement Incomplete
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑AC‑001 |
| **Finding Description** | MFA is only required for privileged accounts; remote access for general staff does not require MFA. |
| **Applicable Framework** | ISO 27001 A.9.4, PCI DSS 8.3, DPDP Sec. 10(2) |
| **Impact** | Credential theft could lead to unauthorised access to customer data and regulatory fines. |
| **Recommended Remediation** | Enforce MFA for all remote access, privileged accounts, and access to Restricted data by Q4 2026. |
| **Target Completion** | 31 December 2026 |
| **Owner** | IAM Lead |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-AC-001 |

### Finding 2: Quarterly Access Reviews Not Automated
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑AC‑002 |
| **Finding Description** | Access reviews are performed manually, resulting in delays and incomplete coverage. |
| **Applicable Framework** | ISO 27001 A.9.2, NIST CSF PR.AC‑1, PCI DSS 7.1 |
| **Impact** | Orphaned accounts and excessive privileges increase insider threat risk. |
| **Recommended Remediation** | Implement automated access recertification in ServiceNow by Q1 2027. |
| **Target Completion** | 31 March 2027 |
| **Owner** | IAM Lead |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-AC-002 |

### Finding 3: SAST/DAST Not Integrated
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑APP‑001 |
| **Finding Description** | Static and dynamic application security testing is not integrated into the CI/CD pipeline; testing is performed ad‑hoc. |
| **Applicable Framework** | ISO 27001 A.14.2, PCI DSS 6.3, NIST CSF PR.IP‑1 |
| **Impact** | Vulnerabilities may reach production, increasing breach risk and PCI non‑compliance. |
| **Recommended Remediation** | Integrate SAST and DAST into the CI/CD pipeline with automated gating by Q4 2026. |
| **Target Completion** | 31 December 2026 |
| **Owner** | AppSec Lead |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-APP-001 |

### Finding 4: No Formal Threat Modelling
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑APP‑002 |
| **Finding Description** | Threat modelling is not performed for new applications or major changes. |
| **Applicable Framework** | ISO 27001 A.14.1, NIST CSF ID.RA‑1 |
| **Impact** | Security requirements are missed early in design, increasing cost and risk. |
| **Recommended Remediation** | Adopt STRIDE threat modelling for all new applications and major changes. |
| **Target Completion** | 31 March 2027 |
| **Owner** | AppSec Lead |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-APP-002 |

### Finding 5: Vendor Continuous Monitoring Missing
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑VEN‑001 |
| **Finding Description** | No process for continuous monitoring of vendor security posture beyond annual assessments. |
| **Applicable Framework** | ISO 27001 A.15.2, NIST CSF ID.SC‑1 |
| **Impact** | Changes in vendor security posture could expose Oracleo to supply chain attacks. |
| **Recommended Remediation** | Implement automated vendor monitoring (e.g., SecurityScorecard) by Q2 2027. |
| **Target Completion** | 30 June 2027 |
| **Owner** | Vendor Risk Mgr |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-VEN-001 |

### Finding 6: No Centralised Compliance Register
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑COM‑001 |
| **Finding Description** | Regulatory obligations are tracked in spreadsheets, not a centralised register with automated gap tracking. |
| **Applicable Framework** | ISO 27001 A.18.1, COBIT APO12 |
| **Impact** | Risk of non‑compliance due to missed regulatory changes and lack of accountability. |
| **Recommended Remediation** | Build a compliance register in ServiceNow by Q4 2026, with scheduled gap assessments. |
| **Target Completion** | 31 December 2026 |
| **Owner** | Compliance Officer |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-COM-001 |

### Finding 7: No Tabletop Exercises Conducted
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑IR‑001 |
| **Finding Description** | No incident response tabletop exercises have been conducted in the past 12 months. |
| **Applicable Framework** | ISO 27001 A.16.1, NIST CSF RS‑IM‑1 |
| **Impact** | Response team may be unprepared for a major incident, increasing impact. |
| **Recommended Remediation** | Conduct two tabletop exercises annually (one technical, one cross‑functional) starting Q4 2026. |
| **Target Completion** | 31 December 2026 (first exercise) |
| **Owner** | CISO |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-IR-001 |

### Finding 8: Consent Management Not Automated
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑DP‑001 |
| **Finding Description** | Consent capture and withdrawal are manual; no automated system for tracking and managing consent. |
| **Applicable Framework** | DPDP Act Sec. 8(5), GDPR Art. 7 |
| **Impact** | Non‑compliance with consent requirements, risk of regulatory action and customer complaints. |
| **Recommended Remediation** | Implement a consent management platform by Q1 2027. |
| **Target Completion** | 31 March 2027 |
| **Owner** | DPO |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-DP-001 |

### Finding 9: SIEM Alerts Not Tuned
| Attribute | Details |
|-----------|---------|
| **Finding ID** | GAP‑SOC‑001 |
| **Finding Description** | SIEM generates high volumes of false positives due to untuned rules and lack of playbooks. |
| **Applicable Framework** | ISO 27001 A.11.1, NIST CSF DE.AE‑1 |
| **Impact** | Real threats may be missed; response teams waste time on false positives. |
| **Recommended Remediation** | Tune SIEM rules based on threat models and implement playbooks for common alerts. |
| **Target Completion** | 31 December 2026 |
| **Owner** | SOC Lead |
| **ServiceNow Issue Reference** | https://dev269444.service-now.com/issue.do?sys_id=GAP-SOC-001 |

---

## 6. Remediation Roadmap

| Quarter | Milestone | Key Actions | Owner |
|---------|-----------|-------------|-------|
| **Q3 2026** | Immediate fixes | – Begin MFA rollout (GAP‑AC‑001) – Procure SAST/DAST tools (GAP‑APP‑001) – Establish compliance register (GAP‑COM‑001) | IAM Lead, AppSec Lead, Compliance Officer |
| **Q4 2026** | Critical remediations | – Complete MFA rollout – Integrate SAST/DAST (pilot) – Conduct first tabletop exercise – Implement automated consent management (kickoff) | IAM Lead, AppSec Lead, CISO, DPO |
| **Q1 2027** | High priority remediations | – Implement automated access recertification – Full SAST/DAST integration – Complete consent management platform – Adopt threat modelling process | IAM Lead, AppSec Lead, DPO |
| **Q2 2027** | Medium priority remediations | – Implement vendor continuous monitoring – Complete SIEM tuning – Post‑remediation gap assessment | Vendor Risk Mgr, SOC Lead, GRC Lead |

---

## 7. ServiceNow Integration

All gaps identified in this report are recorded as **Issues** in ServiceNow:

| Activity | ServiceNow Reference |
|----------|---------------------|
| Issues and findings | https://dev269444.service-now.com/issue |
| Gap tracking dashboard | https://dev269444.service-now.com/dashboard/gap |
| Remediation tasks | https://dev269444.service-now.com/task |

Each issue is linked to a control, assigned to an owner, and tracked through to closure.

---

## 8. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial release | CISO |

---

## 9. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Policy | Information Security Policy | POL‑001 |
| Register | Risk Register | – |
| Library | Control Library | 01-Control-Library.csv |
| Methodology | Risk Assessment Methodology | RISK‑METH‑001 |
| Policy | Data Classification Policy | POL‑DATA‑001 |
| Plan | Corrective Action Plan | CAP‑001 |

---

**End of Report**
