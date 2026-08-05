# Information Security Policy – Oracleo Fintech LLC

**Document ID:** POL‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Next Review Date:** 01 September 2027  
**Owner:** Chief Information Security Officer (CISO)  
**Approved By:** Board of Directors  

---

## 1. Purpose

The Information Security Policy establishes the framework, principles, and mandatory requirements for protecting Oracleo Fintech LLC's information assets, technology infrastructure, and customer data. This policy ensures that security is managed consistently across all business units, regions, and third‑party relationships.

It provides the foundation for the Information Security Management System (ISMS) as required by **ISO/IEC 27001:2022** and aligns with **NIST CSF 2.0** and **COBIT 2019**. All employees, contractors, and vendors must adhere to this policy and its supporting standards.

All policy artifacts are managed through **ServiceNow Policy & Compliance module**:

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. Scope

This policy applies to:

- **All persons** – employees, contractors, consultants, temporary staff, interns, and third‑party representatives.
- **All information assets** – data, systems, applications, networks, cloud services (Azure, M365), endpoints, and mobile devices.
- **All locations** – on‑premises, co‑working spaces, remote work, and cloud environments.
- **All business processes** – digital banking, payments, lending, KYC, AML, merchant onboarding, customer support, and corporate functions.
- **All regions** – India, Singapore, and the United Kingdom.

Third‑party vendors that process, store, or transmit Oracleo Fintech data must comply with equivalent security requirements as specified in their contracts and the **Vendor Management Policy (POL‑VEN‑001)** .

---

## 3. Information Security Objectives

Oracleo Fintech LLC is committed to achieving the following objectives:

| Objective | Description |
|-----------|-------------|
| **Confidentiality** | Ensure that information is accessible only to authorised individuals, systems, or processes. |
| **Integrity** | Safeguard the accuracy, completeness, and authenticity of information and processing methods. |
| **Availability** | Ensure that authorised users have timely and reliable access to information and critical services. |
| **Compliance** | Meet all applicable legal, regulatory, and contractual obligations (including RBI, MAS, FCA, GDPR, DPDP Act, PCI DSS, and SOX). |
| **Accountability** | Assign clear ownership and responsibility for information security across all roles, with measurable performance indicators and regular reporting to the Board. |

---

## 4. Policy Statements

### 4.1 Access Control
The Company shall restrict access to information assets based on business need and least‑privilege principles. All access rights must be approved, documented, and reviewed quarterly. Privileged accounts shall be subject to enhanced monitoring and multi‑factor authentication (MFA).

*Reference: Access Control Policy (POL‑ACC‑001), ISO 27001 A.9*

### 4.2 Asset Management
All information assets shall be inventoried, classified according to sensitivity (Public, Internal, Confidential, Restricted), and assigned to a designated owner. Assets shall be protected commensurate with their classification.

*Reference: Data Classification Policy (POL‑DATA‑001), ISO 27001 A.8*

### 4.3 Cryptography
Cryptographic controls shall be implemented to protect data at rest, in transit, and where required by regulation or contract. Key management shall follow industry best practices, with regular rotation and secure backup.

*Reference: Encryption Standard (STD‑CRYPTO‑001), ISO 27001 A.10*

### 4.4 Physical & Environmental Security
While Oracleo Fintech operates primarily in co‑working spaces, the Company shall ensure that physical access controls are adequate for its data centres, offices, and any sensitive areas. Security of shared spaces is the responsibility of the landlord, with supplementary controls applied by the Company where feasible.

*Reference: Physical Security Standard (STD‑PHYS‑001), ISO 27001 A.7*

### 4.5 Operations Security
Operational procedures, including patch management, vulnerability management, and capacity planning, shall be documented and followed. Logging and monitoring shall be enabled on all critical systems, with alerts configured for security events.

*Reference: Logging Standard (STD‑LOGGING‑001), ISO 27001 A.12*

### 4.6 Communications & Network Security
Networks shall be segregated (e.g., DMZ, internal, guest) with firewalls and access controls. All remote access shall be via VPN or secure gateway, with MFA required. Network services shall be configured securely and reviewed regularly.

*Reference: Network Security Standard (STD‑NET‑001), ISO 27001 A.13*

### 4.7 System Acquisition, Development & Maintenance
Security shall be integrated into the software development lifecycle (SDLC), including threat modelling, secure coding practices, code reviews, and security testing (SAST, DAST, penetration testing). All production changes shall follow change management procedures.

*Reference: Secure SDLC Standard (STD‑SDLC‑001), ISO 27001 A.14*

### 4.8 Supplier Relationships
All third‑party suppliers shall be assessed for security risk prior to engagement. Contracts shall include security obligations, rights to audit, and breach notification clauses. Suppliers shall be monitored continuously for compliance.

*Reference: Vendor Management Policy (POL‑VEN‑001), ISO 27001 A.15*

### 4.9 Incident Management
The Company shall maintain an Incident Response Plan that covers detection, containment, eradication, recovery, and lessons learned. All security incidents shall be reported, investigated, and remediated. Regulatory notifications shall be made within applicable timeframes (e.g., GDPR 72 hours, DPDP Act 72 hours).

*Reference: Incident Response Policy (POL‑IR‑001), ISO 27001 A.16*

### 4.10 Business Continuity
Business continuity and disaster recovery plans shall be documented, tested, and maintained for all critical services. Recovery objectives (RTO/RPO) shall be defined in the Business Impact Analysis and approved by business owners.

*Reference: BCP Policy (POL‑BCP‑001), ISO 27001 A.17*

### 4.11 Compliance (Legal & Regulatory)
The Company shall maintain a register of applicable legal, regulatory, and contractual obligations. Compliance shall be assessed regularly through internal audits, gap assessments, and external reviews. Any deviations shall be documented and remediated.

*Reference: Compliance Management Procedure (PROC‑COMP‑001), ISO 27001 A.18*

### 4.12 Data Protection & Privacy
Personal data shall be processed in accordance with the **India DPDP Act**, **GDPR**, **Singapore PDPA**, and **UK GDPR**. Data subject rights shall be honoured, and data protection impact assessments (DPIAs) shall be conducted for high‑risk processing activities. All data breaches shall be reported to the Data Protection Officer (DPO) and relevant regulators.

*Reference: Data Protection Policy (POL‑DATA‑PROT‑001)*

---

## 5. Compliance & Enforcement

All employees, contractors, and vendors are required to comply with this policy and its associated standards and procedures. Failure to comply may result in:

- **Employees:** disciplinary action, up to and including termination of employment.
- **Contractors:** contract termination or non‑renewal.
- **Vendors:** financial penalties, suspension of services, or contract termination.

Annual acknowledgement of this policy is mandatory for all personnel. The CISO shall report compliance status to the Board quarterly.

---

## 6. Policy Review & Maintenance

This policy shall be reviewed:

- Annually (by 01 September each year), or
- After any significant organisational, regulatory, or technological change, or
- Following a major security incident that highlights a policy gap.

The CISO is responsible for coordinating reviews and obtaining Board approval for updates.

---

## 7. ServiceNow Integration

All policies, standards, and procedures are managed through the **ServiceNow Policy & Compliance module**:

| Activity | ServiceNow Reference |
|----------|---------------------|
| Policy lifecycle (draft, review, approve, publish) | https://dev269444.service-now.com/now/policy |
| Employee policy acknowledgment tracking | https://dev269444.service-now.com/now/policy/compliance |
| Version history and audit trail | https://dev269444.service-now.com/now/policy/history |

Policy acknowledgments are recorded and auditable with date/timestamps and user IDs.

---

## 8. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial release | Board of Directors |

---

## 9. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Charter | Governance Charter | GOV‑001 |
| Policy | Access Control Policy | POL‑ACC‑001 |
| Policy | Acceptable Use Policy | POL‑AUP‑001 |
| Policy | Data Classification Policy | POL‑DATA‑001 |
| Policy | Incident Response Policy | POL‑IR‑001 |
| Policy | Vendor Management Policy | POL‑VEN‑001 |
| Policy | Business Continuity Policy | POL‑BCP‑001 |
| Policy | Data Protection Policy | POL‑DATA‑PROT‑001 |
| Standard | Access Control Standard | STD‑ACC‑001 |
| Standard | Encryption Standard | STD‑CRYPTO‑001 |
| Standard | Logging Standard | STD‑LOGGING‑001 |
| Standard | Network Security Standard | STD‑NET‑001 |
| Standard | Secure SDLC Standard | STD‑SDLC‑001 |
| Procedure | Incident Response Procedure | PROC‑IR‑001 |
| Procedure | Vendor Onboarding Procedure | PROC‑VEN‑001 |
| Library | Control Library | 01-Control-Library.csv |

---

**End of Policy**
