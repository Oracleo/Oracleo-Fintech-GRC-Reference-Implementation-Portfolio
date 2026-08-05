# Governance Charter – Oracleo Fintech LLC

**Document ID:** GOV‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Next Review Date:** 01 September 2027  
**Owner:** Chief Information Security Officer (CISO)  
**Approved By:** Board of Directors  

---

## 1. Purpose

This Charter establishes the governance framework for the Information Security Management System (ISMS) and the broader Governance, Risk, and Compliance (GRC) programme at Oracleo Fintech LLC. It defines the roles, responsibilities, decision rights, and escalation paths necessary to ensure that information security and risk management are aligned with business strategy, regulatory obligations, and stakeholder expectations.

All GRC activities are operationalised through **ServiceNow Integrated Risk Management (IRM)** , which serves as the single source of truth for risks, policies, controls, audits, and vendor assessments.

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. Scope

This Charter applies to:

- All employees, contractors, consultants, and temporary staff of Oracleo Fintech LLC.
- All information assets, systems, applications, networks, and data, regardless of location (on‑premises, cloud, or mobile).
- All business processes and third‑party services that process, store, or transmit Oracleo Fintech data.
- All regions of operation: **India**, **Singapore**, and the **United Kingdom**.

---

## 3. Governance Structure

| Governance Body | Composition | Accountability | Meeting Cadence |
|----------------|-------------|----------------|-----------------|
| **Board of Directors** | Full Board | Ultimate accountability for security and risk appetite; approves the ISMS, major investments, and accepts residual risks above appetite. | Quarterly |
| **Audit Committee** | Non‑executive directors, Internal Audit Director | Oversees internal audit activities, reviews audit findings, and ensures management remediation. | Quarterly |
| **Security Steering Committee** | CISO (Chair), CIO, Compliance Officer, Internal Audit Director, Head of Payments, Head of Lending, Head of Technology Operations | Approves security strategy, risk treatments, exceptions, and major GRC initiatives. | Monthly |
| **CISO** | Chief Information Security Officer | Owns the ISMS, implements security strategy, reports to the Board, and chairs the Security Steering Committee. | Ongoing |
| **GRC Lead** | Full‑time GRC professional (reports to CISO) | Manages the GRC programme, maintains the risk register, control library, and policy lifecycle in ServiceNow; coordinates internal audits. | Ongoing |
| **Risk Owners** | Designated business/IT leaders (e.g., IAM Lead, AppSec Lead, Cloud Architect, DPO) | Accountable for identifying risks in their domain, implementing controls, and reporting on residual risk. | Ongoing |
| **Internal Audit Director** | Independent internal audit function | Plans and executes internal audits, reports findings to the Audit Committee, and tracks remediation. | Ongoing |

---

## 4. Decision Rights – RACI Matrix

| Activity | Board | Audit Committee | Security Steering Committee | CISO | GRC Lead | Risk Owner | Internal Audit |
|----------|-------|-----------------|----------------------------|------|----------|------------|----------------|
| Approve Information Security Policy | A | C | R | R | C | C | I |
| Approve Risk Appetite Statement | A | R | C | R | C | I | I |
| Approve Risk Treatment – Accept (High) | A | C | R | R | C | C | I |
| Approve Risk Treatment – Transfer (High) | A | C | R | R | C | C | I |
| Approve Exceptions (Control deviations) | – | C | A | R | C | C | I |
| Approve Internal Audit Plan | – | A | C | C | C | I | R |
| Approve High‑Risk Vendor Onboarding | – | – | A | R | C | R | I |
| Approve Annual Security Budget | A | C | R | R | C | C | I |
| Declare a Major Incident (Severity 1) | I | I | I | A | C | R | I |
| Escalate Risk Above Appetite | I | I | R | A | R | R | I |

**Key:** R = Responsible (performs the work)  
A = Accountable (ultimately answerable; final decision)  
C = Consulted (must be consulted before decision)  
I = Informed (kept informed after decision)

---

## 5. Meeting Cadence

| Body | Frequency | Agenda |
|------|-----------|--------|
| **Board of Directors** | Quarterly | – ISMS performance report – Top 5 risks – Compliance status (ISO, PCI, DPDP) – Major incidents – Budget and resource requests |
| **Audit Committee** | Quarterly | – Internal audit reports – Open findings and remediation progress – External audit observations |
| **Security Steering Committee** | Monthly | – Risk register review (new, changed, closed) – Exception requests – Vendor risk updates – KPI/KRI dashboards – Project status – Policy approvals |
| **CISO / GRC Team** | Weekly | – Operational updates – Risk treatment task progress – Control testing results – Incident updates |

---

## 6. Escalation Path

| Risk Level | Action | Responsible | Timeframe |
|------------|--------|-------------|-----------|
| **Critical** (Score 20‑25) | Risk owner must notify CISO immediately. CISO convenes Security Steering Committee within 24 hours. If residual risk remains Critical, escalate to Board at next meeting (or emergency meeting if imminent). | Risk Owner → CISO → Steering Committee → Board | 24 hours / next board |
| **High** (Score 13‑19) | Risk owner to develop treatment plan within 5 business days. Escalate to CISO if treatment requires budget > $50K. | Risk Owner → CISO | 5 business days |
| **Medium** (Score 7‑12) | Risk owner to document treatment plan within 15 business days. | Risk Owner | 15 business days |
| **Low** (Score 1‑6) | Risk owner to review annually; can be accepted with minimal documentation. | Risk Owner | Annual review |

**Exception Escalation:** Any request for a permanent exception to a control must be approved by the Security Steering Committee. If the exception would expose the company to risk above appetite, it must also be escalated to the Board.

---

## 7. ServiceNow Integration

All governance activities are supported by ServiceNow IRM:

| Governance Activity | ServiceNow Module | ServiceNow Reference |
|---------------------|-------------------|---------------------|
| Risk management and tracking | Risk Management | https://dev269444.service-now.com/now/risk |
| Policy lifecycle (draft, review, approve, publish) | Policy & Compliance | https://dev269444.service-now.com/now/policy |
| Control library and framework mappings | Control Library | https://dev269444.service-now.com/now/control |
| Exception requests and approvals | Exceptions | https://dev269444.service-now.com/now/exception |
| Audit plans, findings, and remediation | Audit Management | https://dev269444.service-now.com/now/audit |
| Vendor risk assessments | Vendor Risk | https://dev269444.service-now.com/now/vendor |
| Executive dashboards | Dashboards | https://dev269444.service-now.com/now/dashboard |

All approvals recorded in ServiceNow are auditable with date/timestamps and user IDs.

---

## 8. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial release | Board of Directors |

**Next Review Date:** 01 September 2027 (or earlier if significant organisational, regulatory, or technological changes occur).

---

## 9. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Policy | Information Security Policy | POL‑001 |
| Methodology | Risk Assessment Methodology | RISK‑METH‑001 |
| Procedure | Exception Management Procedure | PROC‑EXC‑001 |
| Plan | Internal Audit Plan | AUD‑PLAN‑001 |
| Policy | Vendor Management Policy | POL‑VEN‑001 |
| Library | Control Library | 01-Control-Library.csv |

---

**End of Charter**
