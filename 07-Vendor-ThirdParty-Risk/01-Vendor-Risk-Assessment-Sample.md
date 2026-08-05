# Vendor Risk Assessment – Microsoft Azure

**Assessment ID:** VRA‑AZURE‑001  
**Date:** 01 September 2026  
**Assessor:** Niladri Biswas, GRC Analyst  
**Reviewed By:** Vendor Risk Manager  
**Approved By:** CISO  

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 1. Vendor Details

| Attribute | Details |
|-----------|---------|
| **Vendor Name** | Microsoft Corporation |
| **Service Type** | Cloud Infrastructure (IaaS, PaaS), Microsoft 365, Entra ID |
| **Contract Value** | ₹40 Crore (~$5M) annually |
| **Regions** | India (Central India), Singapore (Southeast Asia), UK (UK South) |
| **Data Processed** | Customer PII (names, addresses, payment data), transaction logs, corporate emails, source code |
| **Service Criticality** | **Critical** – Core infrastructure; outage would halt all business operations |
| **Asset References** | AST-013 (Azure Cloud), AST-014 (Microsoft 365), AST-015 (Entra ID), AST-035 (Cloud Provider) |
| **Contractual Obligations** | GDPR, DPDP Act, RBI Guidelines, PCI DSS (for payment processing) |
| **ServiceNow Vendor Record** | https://dev269444.service-now.com/vendor.do?sys_id=AZURE-001 |

---

## 2. Inherent Risk Assessment

| Factor | Score (1–5) | Justification |
|--------|-------------|---------------|
| **Data Sensitivity** | 5 | Processes customer PII, financial data, and IP; regulatory exposure is high. |
| **Business Criticality** | 5 | Core infrastructure; extended downtime would stop revenue generation. |
| **Regulatory Exposure** | 5 | Subject to GDPR, DPDP Act, RBI, MAS, and FCA oversight. |
| **Past Incidents** | 3 | Microsoft has experienced breaches (e.g., Exchange Server, China hack), though patched quickly. |
| **Reliance on Vendor** | 5 | High lock-in; migration to another cloud provider would be complex and costly. |
| **Inherent Score** | **23/25 (Critical)** | |

---

## 3. Controls Evaluation

| Control Category | Vendor Status | Oracleo Requirement | Assessment |
|------------------|---------------|---------------------|------------|
| **Security Management** | ISO 27001:2022, SOC 2 Type II certified | Certified | **Compliant** |
| **Access Control** | Entra ID MFA, RBAC, privileged access management | Strong | **Compliant** |
| **Data Encryption** | AES-256 at rest, TLS 1.3 in transit | Required | **Compliant** |
| **Logging & Monitoring** | Azure Monitor, Sentinel with threat detection | Required | **Compliant** |
| **Data Residency** | Region‑specific (India, Singapore, UK) | Required for Restricted data | **Compliant** |
| **Business Continuity** | Multi‑region failover, documented DR plans | Critical | **Compliant** |
| **Incident Response** | 72‑hour initial response SLA | 24‑hour notification | **Gap Identified** |
| **Subcontractor Management** | Many third‑party data centres | Full visibility required | **Gap Identified** |
| **Third‑Party Penetration Testing** | Regularly conducted, reports available | Independent validation | **Compliant** |
| **Compliance Certifications** | ISO, SOC, PCI, GDPR, FedRAMP | Required | **Compliant** |

### Identified Gaps

| Gap | Description | Risk Impact |
|-----|-------------|-------------|
| **GAP‑VND‑001** | Incident notification SLA is 72 hours; Oracleo requires 24 hours for critical incidents. | Regulatory reporting (GDPR/DPDP 72-hour clock) could be delayed. |
| **GAP‑VND‑002** | Microsoft does not provide a full list of subcontracted data centres and their security posture. | Supply chain risk; inability to fully assess downstream vendors. |

---

## 4. Residual Risk Assessment

| Factor | Score (1–5) | Justification |
|--------|-------------|---------------|
| **Data Sensitivity** | 5 | Unchanged; data remains sensitive. |
| **Business Criticality** | 5 | Unchanged; still core infrastructure. |
| **Regulatory Exposure** | 4 | Reduced slightly due to controls, but not eliminated. |
| **Past Incidents** | 2 | Microsoft has robust incident response and remediation. |
| **Reliance on Vendor** | 4 | Still high, but mitigation with multi‑region and failover. |
| **Residual Score** | **20/25 (Critical)** | |

**Residual Risk Rating:** Critical

**Justification:** Despite strong controls, the criticality of the service and the inability to fully mitigate reliance means residual risk remains Critical. This requires formal acceptance and ongoing monitoring.

---

## 5. Recommendation

**Approved with Conditions**

**Conditions:**

| Condition | Owner | Target Date | Verification Evidence |
|-----------|-------|-------------|----------------------|
| **1.** Microsoft must provide a 24‑hour incident notification SLA for Severity 1 incidents. | Vendor Risk Mgr | 31 Oct 2026 | Contract amendment signed |
| **2.** Microsoft must provide a list of all subcontracted data centres and their security certifications. | Vendor Risk Mgr | 31 Dec 2026 | Evidence of data centre list and certifications |
| **3.** Quarterly security review meetings with Microsoft security team. | Vendor Risk Mgr | Ongoing | Meeting minutes and action logs |
| **4.** Annual independent penetration test of Azure-hosted Oracleo environment. | Cloud Architect | Ongoing | Penetration test report |

---

## 6. Action Plan

| Action | Owner | Timeline |
|--------|-------|----------|
| Draft contract amendment for 24‑hour notification SLA. | Legal | Sep 2026 |
| Request subcontractor list from Microsoft. | Vendor Risk Mgr | Sep 2026 |
| Schedule quarterly review meetings with Microsoft. | Vendor Risk Mgr | Oct 2026 |
| Engage third‑party penetration testing firm. | Cloud Architect | Nov 2026 |

---

## 7. ServiceNow Integration

Vendor risk assessments are managed through the **ServiceNow Vendor Risk module**:

| Activity | ServiceNow Reference |
|----------|---------------------|
| Vendor risk record | https://dev269444.service-now.com/vendor |
| Assessment form | https://dev269444.service-now.com/vendor/assessment |
| Vendor dashboard | https://dev269444.service-now.com/dashboard/vendor |

Assessment scores, identified gaps, and monitoring plans are stored centrally. Vendor profiles are linked to issues and risk registers.

---

## 8. Document Control

| Version | Date | Author | Changes | Approver |
|---------|------|--------|---------|----------|
| 1.0 | 01 Sep 2026 | Niladri Biswas | Initial assessment | CISO |

---

## 9. Related Documents

| Document Type | Document Name | Document ID |
|---------------|---------------|-------------|
| Register | Asset Register | – |
| Library | Control Library | 01-Control-Library.csv |
| Report | Gap Assessment Report | GAP‑001 |
| Plan | Corrective Action Plan | CAP‑001 |
| Policy | Vendor Management Policy | POL‑VEN‑001 |

---

**End of Vendor Risk Assessment**
