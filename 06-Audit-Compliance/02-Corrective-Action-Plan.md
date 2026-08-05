# Corrective Action Plan – Oracleo Fintech LLC

**Document ID:** CAP‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Next Review Date:** 01 March 2027  
**Owner:** GRC Lead  
**Approved By:** CISO  

---

## 1. Purpose

This Corrective Action Plan (CAP) documents the specific remediation actions required to address the gaps identified in the **Gap Assessment Report (GAP‑001)** . It assigns ownership, establishes target dates, and defines verification evidence for closure. The CAP is the primary tool for tracking remediation progress and will be reviewed weekly by the GRC Lead and monthly by the Security Steering Committee.

All CAP items are tracked as **Remediation Tasks** in ServiceNow:

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. Scope

The CAP covers all findings from the Gap Assessment Report (GAP‑001), including gaps related to:

- Access Control
- Application Security
- Vendor Management
- Compliance Monitoring
- Incident Response
- Data Protection
- SOC Operations

All actions must be completed by their target dates. Extensions require formal approval via the **Exception Management Procedure (PROC‑EXC‑001)** .

---

## 3. Corrective Action Items

| CAP ID | Finding ID | Finding Description | Action Item | Owner | Status | Target Completion | Actual Completion | Verification Evidence | ServiceNow Task Reference |
|--------|------------|---------------------|-------------|-------|--------|-------------------|-------------------|----------------------|---------------------------|
| CAP‑001 | GAP‑AC‑001 | MFA incomplete | Enforce MFA for all remote access (VPN, email, SaaS apps) by updating conditional access policies. | IAM Lead | In Progress | 31 Dec 2026 | – | Entra ID MFA enrollment report showing 100% user enrollment | https://dev269444.service-now.com/task.do?sys_id=CAP-001 |
| CAP‑002 | GAP‑AC‑001 | MFA incomplete | Configure MFA for all privileged accounts (admin access, cloud consoles). | IAM Lead | In Progress | 30 Sep 2026 | – | Privileged access MFA logs | https://dev269444.service-now.com/task.do?sys_id=CAP-002 |
| CAP‑003 | GAP‑AC‑001 | MFA incomplete | Update Access Control Policy to mandate MFA and communicate to all employees. | IAM Lead | Not Started | 31 Oct 2026 | – | Policy update acknowledgment records | https://dev269444.service-now.com/task.do?sys_id=CAP-003 |
| CAP‑004 | GAP‑AC‑002 | Access reviews manual | Implement automated access recertification module in ServiceNow. | IAM Lead | Not Started | 31 Mar 2027 | – | ServiceNow access review workflow live | https://dev269444.service-now.com/task.do?sys_id=CAP-004 |
| CAP‑005 | GAP‑AC‑002 | Access reviews manual | Configure quarterly review campaigns with automated notifications and manager sign-offs. | IAM Lead | Not Started | 31 Mar 2027 | – | Completion of first automated campaign | https://dev269444.service-now.com/task.do?sys_id=CAP-005 |
| CAP‑006 | GAP‑AC‑002 | Access reviews manual | Run first automated access review by Q2 2027 and document evidence. | IAM Lead | Not Started | 30 Jun 2027 | – | Access review reports and sign-offs | https://dev269444.service-now.com/task.do?sys_id=CAP-006 |
| CAP‑007 | GAP‑APP‑001 | SAST/DAST missing | Procure and deploy SAST tool (e.g., SonarQube, Checkmarx) integrated with CI/CD (Azure DevOps). | AppSec Lead | In Progress | 31 Dec 2026 | – | SAST pipeline integration logs | https://dev269444.service-now.com/task.do?sys_id=CAP-007 |
| CAP‑008 | GAP‑APP‑001 | SAST/DAST missing | Procure and deploy DAST tool (e.g., OWASP ZAP, Burp Suite) integrated with CI/CD. | AppSec Lead | Not Started | 31 Dec 2026 | – | DAST pipeline integration logs | https://dev269444.service-now.com/task.do?sys_id=CAP-008 |
| CAP‑009 | GAP‑APP‑001 | SAST/DAST missing | Configure security gates to block builds with critical vulnerabilities. | AppSec Lead | Not Started | 31 Jan 2027 | – | Build failure logs for security violations | https://dev269444.service-now.com/task.do?sys_id=CAP-009 |
| CAP‑010 | GAP‑APP‑002 | No threat modelling | Create threat modelling policy and procedure (STRIDE methodology). | AppSec Lead | Not Started | 31 Jan 2027 | – | Policy document; procedure guide | https://dev269444.service-now.com/task.do?sys_id=CAP-010 |
| CAP‑011 | GAP‑APP‑002 | No threat modelling | Conduct threat modelling for three highest-risk applications (Digital Banking Portal, Payment Gateway, Mobile Wallet). | AppSec Lead | Not Started | 30 Jun 2027 | – | Completed threat models with sign-offs | https://dev269444.service-now.com/task.do?sys_id=CAP-011 |
| CAP‑012 | GAP‑VEN‑001 | Vendor monitoring | Procure vendor risk monitoring solution (e.g., SecurityScorecard, BitSight). | Vendor Risk Mgr | Not Started | 31 Mar 2027 | – | Purchase order and deployment plan | https://dev269444.service-now.com/task.do?sys_id=CAP-012 |
| CAP‑013 | GAP‑VEN‑001 | Vendor monitoring | Implement quarterly automated vendor risk scoring for all critical vendors (Azure, Stripe, AML vendor). | Vendor Risk Mgr | Not Started | 30 Jun 2027 | – | Vendor risk score reports | https://dev269444.service-now.com/task.do?sys_id=CAP-013 |
| CAP‑014 | GAP‑COM‑001 | No compliance register | Build compliance register in ServiceNow with regulatory obligations and mappings. | Compliance Officer | Not Started | 31 Dec 2026 | – | ServiceNow compliance register module live | https://dev269444.service-now.com/task.do?sys_id=CAP-014 |
| CAP‑015 | GAP‑COM‑001 | No compliance register | Schedule automated compliance gap assessments for each regulatory framework (ISO, PCI, DPDP, GDPR). | Compliance Officer | Not Started | 31 Jan 2027 | – | Assessment schedule in ServiceNow | https://dev269444.service-now.com/task.do?sys_id=CAP-015 |
| CAP‑016 | GAP‑IR‑001 | No tabletop exercises | Plan and conduct technical tabletop exercise (target: ransomware scenario). | CISO | Not Started | 31 Dec 2026 | – | Exercise plan; after-action report | https://dev269444.service-now.com/task.do?sys_id=CAP-016 |
| CAP‑017 | GAP‑IR‑001 | No tabletop exercises | Plan and conduct cross-functional tabletop exercise (target: data breach notification). | CISO | Not Started | 31 Mar 2027 | – | Exercise plan; after-action report | https://dev269444.service-now.com/task.do?sys_id=CAP-017 |
| CAP‑018 | GAP‑DP‑001 | Consent manual | Procure consent management platform (e.g., OneTrust, CookieYes). | DPO | Not Started | 30 Nov 2026 | – | Purchase order and deployment plan | https://dev269444.service-now.com/task.do?sys_id=CAP-018 |
| CAP‑019 | GAP‑DP‑001 | Consent manual | Implement consent capture, modification, and withdrawal workflows. | DPO | Not Started | 31 Mar 2027 | – | Live consent portal and logs | https://dev269444.service-now.com/task.do?sys_id=CAP-019 |
| CAP‑020 | GAP‑SOC‑001 | SIEM alerts untuned | Review and tune SIEM rules based on threat models and known attack patterns. | SOC Lead | Not Started | 31 Dec 2026 | – | Tuned rule set; false positive reduction report | https://dev269444.service-now.com/task.do?sys_id=CAP-020 |
| CAP‑021 | GAP‑SOC‑001 | SIEM alerts untuned | Develop playbooks for top 10 alert types (e.g., brute force, malware detection, privilege escalation). | SOC Lead | Not Started | 31 Mar 2027 | – | Playbook documents in ServiceNow | https://dev269444.service-now.com/task.do?sys_id=CAP-021 |
| CAP‑022 | GAP‑SOC‑001 | SIEM alerts untuned | Conduct SOC readiness assessment and staff training on tuned SIEM rules. | SOC Lead | Not Started | 30 Jun 2027 | – | Training completion records | https://dev269444.service-now.com/task.do?sys_id=CAP-022 |

---

## 4. Tracking Process

| Activity | Frequency | Owner | Description |
|----------|-----------|-------|-------------|
| **CAP Review** | Weekly | GRC Lead | Review status of all open CAP items; identify blockers; escalate where needed. |
| **Status Update** | Weekly | All Owners | Update status in ServiceNow with notes on progress. |
| **Steering Committee Report** | Monthly | GRC Lead | Report CAP status to Security Steering Committee (RAG status, blockers, risks). |
| **Verification** | On closure | Internal Audit | Verify evidence before closing CAP; confirm remediation is effective. |

### Escalation Triggers

| Condition | Escalation Path |
|-----------|-----------------|
| CAP overdue by >30 days | Risk Owner → CISO |
| CAP overdue by >60 days | CISO → Security Steering Committee |
| CAP blocked due to budget/resource | CISO → Steering Committee → Board (for major funding) |

---

## 5. ServiceNow Integration

All CAP items are tracked as **Remediation Tasks** in ServiceNow:

| Activity | ServiceNow Reference |
|----------|---------------------|
| CAP task list | https://dev269444.service-now.com/task |
| CAP dashboard | https://dev269444.service-now.com/dashboard/cap |
| Escalation workflows | https://dev269444.service-now.com/workflow |

Status updates are recorded weekly. Escalation workflows are configured to notify managers when tasks are overdue by more than 30 days.

---

## 6. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial release | CISO |

---

## 7. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Report | Gap Assessment Report | GAP‑001 |
| Policy | Information Security Policy | POL‑001 |
| Procedure | Exception Management Procedure | PROC‑EXC‑001 |
| Register | Risk Register | – |
| Library | Control Library | 01-Control-Library.csv |

---

**End of Corrective Action Plan**
