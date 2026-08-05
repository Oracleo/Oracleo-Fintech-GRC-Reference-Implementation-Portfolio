# Statement of Applicability (SoA) – Oracleo Fintech LLC

**Document ID:** SOA‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Next Review Date:** 01 September 2027  
**Owner:** GRC Lead  
**Approved By:** CISO  

---

## 1. Purpose

This Statement of Applicability (SoA) documents the applicability of controls from **ISO/IEC 27001:2022 Annex A** to Oracleo Fintech LLC. It justifies which controls are applicable, which are excluded, and the implementation status of each applicable control. The SoA is a core component of the ISMS and is required for ISO 27001 certification.

The SoA is maintained in **ServiceNow Policy & Compliance module**:

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. Scope

The SoA covers the entire ISMS scope as defined in the **Information Security Policy (POL‑001)** , including:

- All business processes (digital banking, payments, lending, KYC/AML, customer support)
- All technology assets (applications, infrastructure, data, endpoints) as listed in the Asset Register
- All regions of operation (India, Singapore, United Kingdom)
- All employees, contractors, and third‑party vendors who handle Oracleo Fintech data

---

## 3. Applicability Rationale

Each control in ISO 27001:2022 Annex A has been assessed for applicability based on:

- **Risk Assessment Outcomes** – Controls that mitigate risks identified in the Risk Register are considered applicable.
- **Legal and Regulatory Requirements** – Controls required by GDPR, DPDP Act, PCI DSS, and RBI guidelines are marked as applicable.
- **Business Context** – Controls that do not align with Oracleo Fintech's operational model (e.g., physical security for on‑premises data centres) are excluded with justification.
- **Existing Technical Implementation** – Controls already implemented or planned are tracked.

All applicability decisions are documented in the **Control Library (01-Control-Library.csv)** , which maps each control to ISO Annex A references.

---

## 4. Summary of Excluded Controls

The following Annex A controls are excluded from the scope, with justifications:

| ISO Control ID | Control Title | Justification for Exclusion |
|---------------|---------------|-----------------------------|
| A.7.1 | Physical Security Perimeter | Oracleo Fintech operates primarily in co‑working spaces and Azure cloud; physical security is provided by landlords. We have no dedicated physical perimeter. |
| A.7.2 | Physical Entry Controls | Same as above; landlord manages physical access. We control logical access only. |
| A.7.3 | Securing Offices, Rooms and Facilities | Not applicable; we do not own or operate secure facilities. |
| A.8.4 | Return of Assets | Covered by employee contracts and HR offboarding procedures; no separate control needed. |
| A.8.8 | Management of Technical Vulnerabilities | We integrate vulnerability management into operations; no separate process beyond patch management and scanning. |
| A.11.2 | Monitoring of Systems | Integrated with SIEM and EDR; no separate control. |
| A.15.3 | Information Security in Supplier Agreements | Covered by vendor contracts and procurement process; not a standalone control. |
| A.18.2 | Independent Review of Information Security | Internal audit function covers this; no separate independent review. |

All other Annex A controls are considered applicable.

---

## 5. Control Applicability Table (Excerpt)

This table lists all applicable Annex A controls, their implementation status, and the relevant Control Library reference.

| ISO Control ID | Control Title | Applicable? | Implementation Status | Owner | Control Library Reference |
|----------------|---------------|-------------|-----------------------|-------|---------------------------|
| A.5.1 | Policies for Information Security | Yes | Implemented | CISO | AC‑01, CM‑01 |
| A.5.2 | Review of Policies | Yes | Implemented | CISO | CM‑01 |
| A.5.3 | Information Security Roles & Responsibilities | Yes | Implemented | CISO | GOV‑001 |
| A.5.4 | Information Security in Project Management | Yes | In Progress | CISO | BD‑01 |
| A.5.5 | Information Security in Outsourcing | Yes | Partially Implemented | Vendor Risk Mgr | VD‑01, VD‑02 |
| A.6.1 | Screening of Personnel | Yes | Implemented | HR | – |
| A.6.2 | Terms & Conditions of Employment | Yes | Implemented | HR | – |
| A.6.3 | Information Security Awareness, Education & Training | Yes | Implemented | Security Awareness | – |
| A.6.4 | Disciplinary Process | Yes | Implemented | HR | – |
| A.6.5 | Responsibilities after Employment | Yes | Implemented | HR | – |
| A.6.6 | Non‑Disclosure Agreements | Yes | Implemented | Legal | – |
| A.7.1 | Physical Security Perimeter | No | – | – | – |
| A.7.2 | Physical Entry Controls | No | – | – | – |
| A.7.3 | Securing Offices, Rooms and Facilities | No | – | – | – |
| A.8.1 | Inventory of Assets | Yes | Implemented | Asset Manager | AM‑01 |
| A.8.2 | Ownership of Assets | Yes | Implemented | Asset Manager | AM‑02 |
| A.8.3 | Acceptable Use of Assets | Yes | Implemented | CISO | POL‑AUP‑001 |
| A.8.4 | Return of Assets | No | – | – | – |
| A.8.5 | Classification of Information | Yes | Implemented | DPO | AM‑03, POL‑DATA‑001 |
| A.8.6 | Handling of Assets | Yes | Implemented | DPO | PROC‑DATA‑001 |
| A.8.7 | Management of Removable Media | Yes | Not Started | IT Ops | – |
| A.8.8 | Management of Technical Vulnerabilities | No | – | – | – |
| A.8.9 | Information Deletion | Yes | In Progress | DPO | PROC‑DISPOSAL‑001 |
| A.8.10 | Data Leakage Prevention | Yes | In Progress | DLP Lead | – |
| A.8.11 | Backup | Yes | Implemented | Cloud Architect | BC‑01, BC‑02 |
| A.8.12 | Information Transfer | Yes | Implemented | CISO | POL‑TRANS‑001 |
| A.9.1 | Access Control Policy | Yes | Implemented | IAM Lead | AC‑03 |
| A.9.2 | User Access Management | Yes | Partially Implemented | IAM Lead | AC‑01, AC‑02, AC‑05 |
| A.9.3 | User Responsibilities | Yes | Implemented | IAM Lead | AC‑04 |
| A.9.4 | System Access Control | Yes | In Progress | IAM Lead | AC‑04 |
| A.10.1 | Cryptographic Controls | Yes | Implemented | Cloud Architect | CR‑01, CR‑02 |
| A.10.2 | Key Management | Yes | Implemented | Cloud Architect | CR‑03 |
| A.11.1 | Logging & Monitoring | Yes | Implemented | SOC Lead | OP‑04 |
| A.11.2 | Monitoring of Systems | No | – | – | – |
| A.11.3 | Protection of Log Information | Yes | Implemented | SOC Lead | OP‑04 |
| A.11.4 | Administrator & Operator Logs | Yes | Implemented | SOC Lead | OP‑04 |
| A.12.1 | Management of Technical Vulnerabilities | Yes | Implemented | AppSec Lead | OP‑01, OP‑02 |
| A.12.2 | Change Management | Yes | Implemented | IT Ops | OP‑03 |
| A.12.3 | Capacity Management | Yes | In Progress | Cloud Architect | – |
| A.12.4 | Protection from Malware | Yes | Implemented | SOC Lead | OP‑01 |
| A.12.5 | Secure System Engineering | Yes | Partially Implemented | AppSec Lead | BD‑01 |
| A.13.1 | Network Security | Yes | Implemented | Network Lead | NW‑01, NW‑02, NW‑03 |
| A.13.2 | Security of Network Services | Yes | Implemented | Network Lead | NW‑02 |
| A.13.3 | Network Segregation | Yes | Implemented | Network Lead | NW‑01 |
| A.14.1 | Secure Development | Yes | Partially Implemented | AppSec Lead | BD‑01, BD‑04 |
| A.14.2 | Security in Development Lifecycle | Yes | In Progress | AppSec Lead | BD‑02, BD‑03 |
| A.14.3 | Security Testing | Yes | Implemented | AppSec Lead | BD‑02 |
| A.15.1 | Vendor Relationship | Yes | Implemented | Vendor Risk Mgr | VD‑01 |
| A.15.2 | Vendor Service Delivery | Yes | Partially Implemented | Vendor Risk Mgr | VD‑02 |
| A.15.3 | Information Security in Supplier Agreements | No | – | – | – |
| A.16.1 | Incident Management | Yes | Implemented | CISO | IR‑01, IR‑02 |
| A.16.2 | Reporting Security Events | Yes | Implemented | SOC Lead | IR‑02 |
| A.17.1 | Business Continuity | Yes | Implemented | BCP Lead | BC‑01 |
| A.17.2 | ICT Readiness | Yes | Implemented | Cloud Architect | BC‑02 |
| A.18.1 | Compliance with Legal Requirements | Yes | In Progress | Compliance Officer | CM‑01 |
| A.18.2 | Independent Review of Information Security | No | – | – | – |

---

## 6. ServiceNow Integration

The SoA is maintained in **ServiceNow Policy & Compliance module**:

| Activity | ServiceNow Reference |
|----------|---------------------|
| SoA records | https://dev269444.service-now.com/now/soa |
| Control applicability decisions | https://dev269444.service-now.com/now/control/applicability |
| Audit trail and version history | https://dev269444.service-now.com/now/soa/history |

All applicability decisions are linked to the Control Library and Risk Register.

---

## 7. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial release | CISO |

---

## 8. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Policy | Information Security Policy | POL‑001 |
| Charter | Governance Charter | GOV‑001 |
| Register | Asset Register | – |
| Library | Control Library | 01-Control-Library.csv |
| Methodology | Risk Assessment Methodology | RISK‑METH‑001 |
| Policy | Data Classification Policy | POL‑DATA‑001 |

---

**End of Statement of Applicability**
