# Data Classification Policy – Oracleo Fintech LLC

**Document ID:** POL‑DATA‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Next Review Date:** 01 September 2027  
**Owner:** Data Protection Officer (DPO)  
**Approved By:** CISO  

---

## 1. Purpose

This policy establishes a formal data classification framework to ensure that information assets are protected according to their value, sensitivity, and legal/regulatory requirements. Classification enables Oracleo Fintech LLC to apply appropriate security controls, reduce risk, and comply with obligations under the **India DPDP Act**, **GDPR**, **Singapore PDPA**, **UK GDPR**, **RBI Cyber Security Guidelines**, and **PCI DSS**.

All classification decisions are recorded and tracked in **ServiceNow Asset Management module**:

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. Scope

This policy applies to:

- All data created, collected, stored, processed, or transmitted by Oracleo Fintech LLC.
- All data owned or managed by third‑party vendors on behalf of Oracleo Fintech.
- All formats: structured data, unstructured data, paper, and digital media.
- All employees, contractors, consultants, and temporary staff who handle Oracleo Fintech data.

Data classification is mandatory for all information assets listed in the **Asset Register (AST‑001‑040)** .

---

## 3. Classification Levels

Oracleo Fintech uses four classification levels, defined by the potential impact of unauthorised disclosure, alteration, or destruction.

| Level | Label | Definition | Example Data | Impact of Loss |
|-------|-------|------------|--------------|----------------|
| 1 | **Public** | Information intended for public consumption; no harm if disclosed. | Corporate website, press releases, job postings, marketing collateral. | Negligible |
| 2 | **Internal** | Information intended for internal use only; limited harm if disclosed. | Internal policies, org charts, meeting minutes, non‑sensitive internal reports. | Minor – internal embarrassment, limited operational disruption |
| 3 | **Confidential** | Sensitive business information; significant harm if disclosed to unauthorised parties. | Financial statements (pre‑public), source code, vendor contracts, internal audit reports, business plans, employee performance data. | Moderate to High – competitive disadvantage, reputational damage, financial loss |
| 4 | **Restricted** | Highly sensitive information requiring the strictest controls; severe harm if disclosed. | Customer PII (names, addresses, IDs, payment info), financial transaction data, authentication credentials, cryptographic keys, trade secrets, legal privileged data, regulatory filing data (e.g., RBI, MAS, FCA). | Critical – regulatory fines, legal liability, permanent brand damage, business continuity risk |

---

## 4. Classification Criteria

| Factor | Public | Internal | Confidential | Restricted |
|--------|--------|----------|--------------|------------|
| **Contains PII?** | No | No | Maybe (e.g., employee internal data) | Yes (customer PII) |
| **Contains Financial Data?** | No | No | Yes (internal finance) | Yes (customer transactions) |
| **Regulatory Obligation?** | No | No | Yes (e.g., SOX, internal audit) | Yes (GDPR, DPDP, PCI, RBI) |
| **Competitive Value** | None | Low | High | Critical |
| **Legal Requirement for Confidentiality?** | No | No | Sometimes (contracts) | Always (regulations) |

---

## 5. Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| **Data Owner** | Business leader accountable for a specific data set (e.g., VP Payments for transaction data). Approves classification and access. |
| **Data Steward** | Day‑to‑day manager of data (e.g., DBA, data analyst). Implements classification, maintains metadata, and ensures handling requirements are followed. |
| **DPO / Compliance** | Ensures classification aligns with regulatory requirements; approves Restricted classifications. |
| **CISO** | Defines technical controls for each classification; reviews classification policy annually. |

---

## 6. Handling Requirements

| Requirement | Public | Internal | Confidential | Restricted |
|-------------|--------|----------|--------------|------------|
| **Encryption at Rest** | Not required | Recommended | Required | Required |
| **Encryption in Transit** | Not required | Required (TLS) | Required (TLS with strong ciphers) | Required (TLS 1.3+ with strong ciphers) |
| **Access Control** | None (public) | Need‑to‑know within Oracleo | Need‑to‑know, manager approval, regular review | Need‑to‑know, DPO/owner approval, quarterly review, MFA required |
| **Storage Location** | Any | Any (within Oracleo) | Must be within Oracleo‑controlled environment | Must be in approved regions (India, Singapore, UK) and only on approved services (e.g., Azure with data residency) |
| **Retention Period** | Per content policy | Per record schedule | Per regulatory/legal requirements (e.g., 5‑7 years) | Per regulatory requirements (e.g., 7‑10 years for financial records) |
| **Disposal** | Standard deletion | Secure deletion (software overwrite) | Secure deletion (overwrite or physical destruction) | Secure deletion (overwrite or physical destruction) with verification log |
| **Incident Notification** | Not required | Notify internal team | Notify data owner and CISO within 24h | Notify DPO and CISO within 4h; mandatory regulatory notification within 72h (GDPR, DPDP) |

---

## 7. Classification Process

1. **Initial Classification:** When a new data set or system is created, the Data Owner, in consultation with the Data Steward and DPO, assigns an initial classification using the criteria in Section 4.
2. **Re‑classification:** Data classification shall be reviewed:
   - Annually (during the annual asset review).
   - When the data's use, purpose, or sensitivity changes.
   - When new regulations come into effect.
3. **De‑classification:** If data no longer meets the criteria for its current level (e.g., becomes public), the Data Owner may request re‑classification to a lower level with approval from the DPO.

All classification decisions shall be recorded in the **Asset Register** (ServiceNow / CSV).

---

## 8. ServiceNow Integration

Classification is managed through **ServiceNow Asset Management module**:

| Activity | ServiceNow Reference |
|----------|---------------------|
| Asset classification records | https://dev269444.service-now.com/asset |
| Classification change history | https://dev269444.service-now.com/asset/history |
| Classification reports | https://dev269444.service-now.com/asset/reports |

---

## 9. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial release | CISO |

---

## 10. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Register | Asset Register | – |
| Policy | Information Security Policy | POL‑001 |
| Policy | Data Protection Policy (DPDP/GDPR) | POL‑DATA‑PROT‑001 |
| Procedure | Data Handling Procedure | PROC‑DATA‑001 |
| Procedure | Data Disposal Procedure | PROC‑DISPOSAL‑001 |
| Standard | Encryption Standard | STD‑CRYPTO‑001 |

---

**End of Policy**
