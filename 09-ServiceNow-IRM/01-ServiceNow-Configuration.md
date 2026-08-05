markdown
# ServiceNow IRM Configuration – Oracleo Fintech LLC

**Document ID:** SNOW‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Owner:** GRC Lead  
**Approved By:** CISO  

---

## 1. Purpose

This document details the configuration of the **ServiceNow Integrated Risk Management (IRM)** platform at Oracleo Fintech LLC. It serves as both a configuration guide and a reference for how the GRC programme is operationalised.

All modules are configured to support the ISMS and align with ISO 27001, NIST CSF, COBIT, and regulatory requirements.

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. ServiceNow Instance Details

| Attribute | Value |
|-----------|-------|
| **Instance URL** | https://dev269444.service-now.com |
| **Release** | Zurich |
| **Modules Licensed** | Risk Management, Policy & Compliance, Audit Management, Vendor Risk, Issues & Findings, Exceptions, Control Testing, Dashboards |
| **Integration** | Azure AD (Entra ID), Microsoft Sentinel, Azure DevOps, Qualys |
| **Data Retention** | 7 years (per regulatory requirements) |
| **Access Control** | Role-based (RBAC) with MFA |

---

## 3. Module 1: Risk Management – Configuration

### 3.1 Risk Form – Field Mapping

When a Risk Manager opens a risk record, the form displays the following fields:

| Field Name | Type | Mapping / Business Rule | Example |
|------------|------|-------------------------|---------|
| Risk ID | Auto-generated | RISK-{YYYY}-{XXX} | RISK-2026-001 |
| Risk Statement | Text | Clear description of the event | Unauthorised access to customer PII |
| Category | Dropdown | Access Control, Malware, Regulatory, Vendor, AppSec | Access Control |
| Business Unit | Dropdown | Payments, Lending, Corporate, TechOps | Corporate |
| Inherent Likelihood | 1-5 | 1=Rare, 5=Almost Certain | 5 |
| Inherent Impact | 1-5 | 1=Negligible, 5=Catastrophic | 5 |
| Inherent Score | *Calculated* | Likelihood * Impact | 25 |
| Inherent Rating | *Calculated* | 1-6=Low, 7-12=Med, 13-19=High, 20-25=Critical | Critical |
| Existing Controls | Text | Free text describing current mitigations | MFA for priv. accounts, Quarterly reviews |
| Residual Likelihood | 1-5 | Post-control assessment | 3 |
| Residual Impact | 1-5 | Post-control assessment | 4 |
| Residual Score | *Calculated* | 12 | Medium |
| Treatment Plan | Dropdown | Reduce, Accept, Transfer, Avoid | Reduce |
| Risk Owner | Reference (User) | IAM Lead | – |
| Target Closure Date | Date | When risk should be mitigated | 2026-12-31 |
| State | Dropdown | Open, In Progress, Closed, Accepted | In Progress |

### 3.2 ServiceNow Workflow – Risk Approval
┌────────────────────────────────────────────────────────────────────────────┐
│ RISK APPROVAL WORKFLOW (ServiceNow) │
├────────────────────────────────────────────────────────────────────────────┤
│ │
│ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌───────────┐│
│ │ Risk Owner │───▶│ Risk Manager │───▶│ CISO │───▶│ Board ││
│ │ Creates │ │ Reviews & │ │ Approves │ │ (Critical ││
│ │ Risk Record │ │ Validates │ │ Treatment │ │ only) ││
│ └──────────────┘ └──────────────┘ └──────────────┘ └───────────┘│
│ │ │ │ │
│ ▼ ▼ ▼ │
│ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐ │
│ │ Auto-calc │ │ If Score > │ │ If Accepted │ │
│ │ Inherent │ │ 13 → Escal- │ │ → Notify │ │
│ │ Residual │ │ ate to SC │ │ Owner │ │
│ └──────────────┘ └──────────────┘ └──────────────┘ │
│ │
│ Automated Tasks: │
│ • Email notification when risk is assigned. │
│ • Reminder 7 days before target closure date. │
│ • Escalation if risk remains >30 days overdue. │
│ • Update KRI dashboard automatically on risk status change. │
└────────────────────────────────────────────────────────────────────────────┘

text

### 3.3 Risk Heatmap (Dashboard Widget Mockup)
┌─────────────────────────────────────────────────────────────────────────┐
│ RISK HEATMAP (ServiceNow) │
├─────────────────────────────────────────────────────────────────────────┤
│ │
│ IMPACT │
│ 5 │ [R-001] [R-006] │ [R-003] [R-009] │ [R-002] [R-008] │
│ 4 │ (Unauth PII) │ (DPDP) (PCI) │ (Ransomware) │
│ │ (SQLi) │ │ (Phishing) │
│ 3 │ ──────────────── │ [R-005] [R-004] │ [R-010] │
│ │ │ (Vendor) (Insider) │ (IR) │
│ 2 │ │ ──────────────── │ ──────────────── │
│ 1 │ ──────────────── │ ──────────────── │ ──────────────── │
│ │ 1 2 3 LIKELIHOOD │
├─────────────────────────────────────────────────────────────────────────┤
│ Legend: 🔴 Critical (20-25) 🟠 High (13-19) 🟡 Medium (7-12) 🟢 Low (1-6)│
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/risk

---

## 4. Module 2: Policy & Compliance – Configuration

### 4.1 Control Library (ServiceNow Table)
┌─────────────────────────────────────────────────────────────────────────┐
│ CONTROL LIBRARY (sys_control_library) │
├─────────────────────────────────────────────────────────────────────────┤
│ Search: [___________________________] [Search] [Export] [New] │
├─────────────────────────────────────────────────────────────────────────┤
│ Control ID │ Control Name │ Owner │ Status │ Mappings│
├──────────────┼───────────────────────┼────────────┼───────────┼─────────┤
│ AC-01 │ User Access Provision │ IAM Lead │ Partially │ ISO:3 │
│ │ │ │ Implement │ NIST:2 │
│ │ │ │ │ CIS:3 │
│ AC-02 │ Privileged Access │ IAM Lead │ Implement │ ISO:2 │
│ │ │ │ │ NIST:3 │
│ CR-01 │ Data Encryption │ Cloud Arch │ Implement │ ISO:2 │
│ │ │ │ │ PCI:2 │
│ BD-01 │ Secure SDLC │ AppSec │ Partially │ ISO:3 │
│ │ │ │ Implement │ OWASP:3 │
│ IR-01 │ Incident Response │ CISO │ Implement │ ISO:2 │
│ │ │ │ │ NIST:2 │
├──────────────┴───────────────────────┴────────────┴───────────┴─────────┤
│ Total Controls: 34 │ Implemented: 18 │ In Progress: 12 │ Other: 4 │
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/control

### 4.2 Control Test Plan & Evidence Repository

Each control has a test plan linked to it. Evidence is stored in ServiceNow Document Management.
┌─────────────────────────────────────────────────────────────────────────┐
│ CONTROL TEST PLAN – AC-01 │
├─────────────────────────────────────────────────────────────────────────┤
│ │
│ Test ID: TP-AC-01-001 │
│ Test Description: Verify that user access requests include manager │
│ approval and are documented. │
│ Frequency: Quarterly │
│ Sample Size: 20 random user access records │
│ Evidence Required: │
│ • Access request forms (signed/approved) │
│ • Manager approval emails │
│ • Identity lifecycle logs │
│ Evidence Location: /docs/AC-01/Evidence/ │
│ │
│ ┌─────────────────────────────────────────────────────────────────────┐│
│ │ Test Results: ││
│ │ [PASS] 15 of 20 records had proper approvals. ││
│ │ [FAIL] 5 records had no approval documented. ││
│ │ Finding: IA-2026-001 – Access reviews not documented. ││
│ └─────────────────────────────────────────────────────────────────────┘│
│ │
│ [View Evidence] [Create Finding] [Assign Remediation] │
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/control/test

### 4.3 Compliance Dashboard (Widget)
┌─────────────────────────────────────────────────────────────────────────┐
│ COMPLIANCE DASHBOARD │
├─────────────────────────────────────────────────────────────────────────┤
│ │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ ISO 27001:2022 │ PCI DSS 4.0 │ │
│ │ Progress: 65% │ Progress: 55% │ │
│ │ Status: 🟡 │ Status: 🔴 │ │
│ │ Gap Count: 5 │ Gap Count: 8 │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ DPDP Act (India) │ GDPR │ │
│ │ Progress: 60% │ Progress: 75% │ │
│ │ Status: 🔴 │ Status: 🟡 │ │
│ │ Gap Count: 4 │ Gap Count: 3 │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ RBI Guidelines │ SOC 2 │ │
│ │ Progress: 70% │ Progress: 80% │ │
│ │ Status: 🟡 │ Status: 🟢 │ │
│ │ Gap Count: 3 │ Gap Count: 2 │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ Compliance Score (Weighted Average): 67.5% [ Refresh ] │
│ Last Updated: 01/09/2026 14:30 │
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/dashboard/compliance

---

## 5. Module 3: Audit Management – Configuration

### 5.1 Audit Plan (ServiceNow View)
┌─────────────────────────────────────────────────────────────────────────┐
│ INTERNAL AUDIT PLAN – 2026 │
├─────────────────────────────────────────────────────────────────────────┤
│ Audit ID: AUD-2026-001 │
│ Audit Name: ISO 27001:2022 Stage 1 Readiness │
│ Auditor: Internal Audit Team │
│ Scope: All Annex A controls and Clauses 4-10 │
│ Audit Period: 01/10/2026 – 15/11/2026 │
│ Status: Planned │
│ │
│ ┌──────────────────────────────────────────────────────────────────┐ │
│ │ # │ Control ID │ Control Name │ Status │ Finding ID │ │
│ ├──────────────────────────────────────────────────────────────────┤ │
│ │ 1 │ AC-01 │ User Access Provision │ Not Tested │ – │ │
│ │ 2 │ AC-02 │ Privileged Access │ Not Tested │ – │ │
│ │ 3 │ CR-01 │ Data Encryption │ Not Tested │ – │ │
│ │ 4 │ IR-01 │ Incident Response │ Not Tested │ – │ │
│ └──────────────────────────────────────────────────────────────────┘ │
│ │
│ [Start Audit] [Generate Checklist] [Export to PDF] │
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/audit

### 5.2 Audit Finding (ServiceNow Record)
┌─────────────────────────────────────────────────────────────────────────┐
│ FINDING – IA-2026-001 │
├─────────────────────────────────────────────────────────────────────────┤
│ Finding Title: Access Reviews Not Documented for Q2 2026 │
│ Severity: High │
│ Status: In Progress │
│ Audit: AUD-2026-001 │
│ Control: AC-01 (User Access Provisioning) │
│ Owner: IAM Lead │
│ │
│ DESCRIPTION: │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ Q2 2026 access reviews were not documented or retained. No │ │
│ │ evidence is available to demonstrate that quarterly access │ │
│ │ reviews were conducted for any user group. │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ RECOMMENDATION: │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ Immediately conduct a retrospective review for Q2 2026 and │ │
│ │ document all findings. Implement automated recertification in │ │
│ │ ServiceNow for Q3 2026 onward to prevent recurrence. │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ MANAGEMENT RESPONSE: │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ IAM team will conduct retrospective review by 30/09/2026 and │ │
│ │ implement automated recertification by 31/12/2026. │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ Target Closure: 31/12/2026 │
│ [Upload Evidence] [Request Extension] [Close Finding] │
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/issue

---

## 6. Module 4: Vendor Risk – Configuration

### 6.1 Vendor Assessment Form
┌─────────────────────────────────────────────────────────────────────────┐
│ VENDOR RISK ASSESSMENT – Microsoft Azure │
├─────────────────────────────────────────────────────────────────────────┤
│ Vendor Name: Microsoft Corporation │
│ Service: Cloud Infrastructure (IaaS/PaaS) │
│ Contract Value: ₹40 Crore ($5M) │
│ Assessment Type: New / Renewal / Quarterly Review │
│ Risk Owner: Vendor Risk Manager │
│ │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ 1. Data Sensitivity (Weight: 10) Score: 5/5 │ │
│ │ 2. Business Criticality (Weight: 10) Score: 5/5 │ │
│ │ 3. Regulatory Exposure (Weight: 10) Score: 5/5 │ │
│ │ 4. Past Incidents (Weight: 5) Score: 3/5 │ │
│ │ 5. Reliance on Vendor (Weight: 5) Score: 5/5 │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ INHERENT RISK SCORE: 23/30 (High) │
│ │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ Vendor Controls: │ │
│ │ [PASS] ISO 27001:2022 Certified │ │
│ │ [PASS] SOC 2 Type II Certified │ │
│ │ [PASS] AES-256 Encryption at Rest │ │
│ │ [PASS] TLS 1.3 Encryption in Transit │ │
│ │ [FAIL] Incident Notification SLA (72 hours vs required 24) │ │
│ │ [FAIL] Subcontractor List Not Provided │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ RESIDUAL RISK SCORE: 21/30 (Medium-High) │
│ │
│ RECOMMENDATION: Approved with Conditions │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ 1. Amend contract to 24-hour incident notification SLA │ │
│ │ 2. Request subcontractor list with certifications │ │
│ │ 3. Quarterly review meetings │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ [Submit Assessment] [Request Approval] [Generate Report] │
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/vendor

---

## 7. Module 5: Exceptions – Configuration

### 7.1 Exception Request Form
┌─────────────────────────────────────────────────────────────────────────┐
│ EXCEPTION REQUEST – Oracleo Fintech LLC │
├─────────────────────────────────────────────────────────────────────────┤
│ Exception ID: EXC-2026-001 │
│ Control ID: AC-01 (User Access Provisioning) │
│ Requestor: IAM Lead │
│ Status: Pending Approval │
│ │
│ DESCRIPTION: │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ Due to migration to new identity management system, quarterly │ │
│ │ access reviews for Q3 2026 will be delayed by 30 days. │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ JUSTIFICATION: │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ The new system will automate access reviews; delay is │ │
│ │ necessary to avoid double work. Compensating controls: │ │
│ │ increased logging and monitoring during the transition. │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ COMPENSATING CONTROLS: │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ 1. SIEM alerts for account creations/deletions │ │
│ │ 2. Weekly manual review of privileged account activity │ │
│ │ 3. Immediate access removal on exit │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ Proposed End Date: 31/10/2026 │
│ Approvers: │
│ [ ] IAM Lead (Approved) │
│ [ ] Risk Manager (Pending) │
│ [ ] CISO (Pending) │
│ [ ] Steering Committee (Pending if >30 days) │
│ │
│ [Submit Exception] [Reject] [Request Info] │
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/exception

---

## 8. Module 6: Executive Dashboard (CISO View)

This is the **high-level dashboard** presented to the CISO and Board.
┌─────────────────────────────────────────────────────────────────────────┐
│ EXECUTIVE DASHBOARD – CISO VIEW │
│ Oracleo Fintech LLC – As of 01 Sep 2026 │
├─────────────────────────────────────────────────────────────────────────┤
│ │
│ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ │
│ │ Critical │ │ High │ │ Compliance │ │ Incidents │ │
│ │ Risks │ │ Risks │ │ Score │ │ (YTD) │ │
│ │ 2 │ │ 4 │ │ 67.5% │ │ 12 │ │
│ │ 🔴 │ │ 🟠 │ │ 🟡 │ │ 🟢 │ │
│ └─────────────┘ └─────────────┘ └─────────────┘ └─────────────┘ │
│ │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ CONTROL IMPLEMENTATION PROGRESS │ │
│ │ ┌──────────────────────────────────────────────────────────┐ │ │
│ │ │ ████████████░░░░░░░░░░░░░░░░░░ 65% (Target: 90%) │ │ │
│ │ └──────────────────────────────────────────────────────────┘ │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ COMPLIANCE STATUS (RAG) │ │
│ │ ┌──────────────────────────────────────────────────────────┐ │ │
│ │ │ ISO 27001: 🟡 │ PCI: 🔴 │ DPDP: 🔴 │ GDPR: 🟡 │ RBI: 🟡│ │ │
│ │ └──────────────────────────────────────────────────────────┘ │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ ┌─────────────────────────────────────────────────────────────────┐ │
│ │ TOP 5 RISKS │ │
│ │ 1. R-001: Unauthorised access to PII (Critical) – IAM Lead │ │
│ │ 2. R-006: SQL Injection (Critical) – AppSec Lead │ │
│ │ 3. R-003: DPDP Non-compliance (High) – DPO │ │
│ │ 4. R-009: PCI DSS Gap (High) – Compliance Officer │ │
│ │ 5. R-004: Insider Threat (High) – HR │ │
│ └─────────────────────────────────────────────────────────────────┘ │
│ │
│ [Download Report] [Schedule Review] [Refresh Data] │
└─────────────────────────────────────────────────────────────────────────┘

text

**ServiceNow Reference:** https://dev269444.service-now.com/now/dashboard/executive

---

## 9. Integration Points

### 9.1 Integration Architecture
┌─────────────────────────────────────────────────────────────────────────┐
│ SERVICENOW INTEGRATION ARCHITECTURE │
├─────────────────────────────────────────────────────────────────────────┤
│ │
│ ┌────────────────────┐ ┌────────────────────┐ ┌───────────────┐ │
│ │ Azure AD │───▶│ ServiceNow IRM │───▶│ Azure DevOps │ │
│ │ (Entra ID) │ │ (Risk, Policy, │ │ (CI/CD) │ │
│ │ Identity Data │ │ Audit, Vendor) │ │ (SAST/DAST) │ │
│ └────────────────────┘ └────────────────────┘ └───────────────┘ │
│ │ │ │ │
│ ▼ ▼ ▼ │
│ ┌────────────────────┐ ┌────────────────────┐ ┌───────────────┐ │
│ │ Microsoft │ │ Microsoft │ │ Qualys │ │
│ │ Sentinel (SIEM) │ │ Defender for │ │ Vulnerability│ │
│ │ Alerts → Issues │ │ Cloud (Findings) │ │ Scans → │ │
│ └────────────────────┘ └────────────────────┘ │ Vulnerabilities│
│ └───────────────┘ │
│ │
│ Data Sync: │
│ • Users and groups: Sync from Azure AD to ServiceNow every 4 hours. │
│ • Vulnerability scans: Import Qualys findings as Issues daily. │
│ • SIEM alerts: Forward critical alerts as Incidents in ServiceNow. │
│ • CI/CD: SAST/DAST findings automatically created as Issues. │
└─────────────────────────────────────────────────────────────────────────┘

text

### 9.2 API Endpoints Configured

| Integration | Endpoint | Purpose | Frequency |
|-------------|----------|---------|-----------|
| Azure AD | `https://graph.microsoft.com/v1.0/users` | User identity sync | Every 4 hours |
| Sentinel | `https://management.azure.com/.../alerts` | SIEM alert import | Real-time |
| Qualys | `https://qualysapi.qualys.com/api/v2/` | Vulnerability scan import | Daily |
| Azure DevOps | `https://dev.azure.com/.../_apis/build/` | SAST/DAST findings | On build |

**ServiceNow Reference:** https://dev269444.service-now.com/now/integration

---

## 10. Role-Based Access Control (RBAC)

| Role | Access Level | Modules | ServiceNow Reference |
|------|--------------|---------|---------------------|
| **CISO** | Full Read/Write | All modules, approvals, dashboards | https://dev269444.service-now.com/role/ciso |
| **Risk Manager** | Full Read/Write | Risk Management, Issues | https://dev269444.service-now.com/role/risk_mgr |
| **GRC Analyst** | Read/Write (limited) | Risk, Policy, Audit (no approvals) | https://dev269444.service-now.com/role/grc_analyst |
| **Auditor** | Read Only | Audit Management, Findings | https://dev269444.service-now.com/role/auditor |
| **Risk Owner** | Read/Write (owned risks) | Risk Management (assigned) | https://dev269444.service-now.com/role/risk_owner |
| **Vendor Risk Manager** | Full Read/Write | Vendor Risk | https://dev269444.service-now.com/role/vendor_mgr |
| **Viewer** | Read Only | Dashboards only | https://dev269444.service-now.com/role/viewer |

---

## 11. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial release | CISO |

---

## 12. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Charter | Governance Charter | GOV‑001 |
| Policy | Information Security Policy | POL‑001 |
| Register | Risk Register | – |
| Library | Control Library | 01-Control-Library.csv |
| Report | Gap Assessment Report | GAP‑001 |
| Plan | Corrective Action Plan | CAP‑001 |
| Dashboard | KPI/KRI Dashboard | DASH‑001 |

---

**End of ServiceNow Configuration Guide**
