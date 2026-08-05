# Risk Assessment Methodology – Oracleo Fintech LLC

**Document ID:** RISK‑METH‑001  
**Version:** 1.0  
**Effective Date:** 01 September 2026  
**Next Review Date:** 01 September 2027  
**Owner:** GRC Lead  
**Approved By:** CISO  

---

## 1. Purpose

This document defines the standardised methodology for identifying, analysing, evaluating, and treating information security risks across Oracleo Fintech LLC. It ensures that risk assessments are consistent, objective, and aligned with business objectives, regulatory obligations, and strategic priorities.

The methodology is designed to comply with **ISO/IEC 27005:2022**, **NIST CSF 2.0 (ID.RA)** , **ISO 31000**, and **COBIT 2019 (APO12)** . All risk assessments conducted within the organisation shall follow this methodology.

All risks are recorded, tracked, and reported in the **ServiceNow Risk Management module**:

**ServiceNow Instance:** https://dev269444.service-now.com

---

## 2. Scope

This methodology applies to:

- **All information assets** – data, systems, networks, cloud services, applications, and endpoints.
- **All business processes** – including digital banking, payments, lending, KYC, AML, customer support, and corporate functions.
- **All third‑party services** – vendors, suppliers, partners, and outsourced providers.
- **All projects** – new systems, major changes, and acquisitions.
- **All regions** – India, Singapore, and the United Kingdom.

Risk assessments shall be conducted at the enterprise level (annual), at the system/application level (before deployment, after major changes), and at the project level (during initiation).

---

## 3. Risk Management Framework

Oracleo Fintech adopts a three‑tiered risk management framework aligned with industry standards:

| Tier | Layer | Framework |
|------|-------|-----------|
| **Tier 1** | Enterprise Risk Management | ISO 31000 – overarching principles for risk governance. |
| **Tier 2** | Information Security Risk | ISO 27005 – specific to information security risks; defines the assessment methodology. |
| **Tier 3** | Technical Risk | NIST CSF – provides categories (Identify, Protect, Detect, Respond, Recover) and sub‑categories for technical controls. |

All risks are assessed, documented, and tracked in the **ServiceNow Risk Management module**.

---

## 4. Risk Criteria

### 4.1 Likelihood Scale

| Score | Description | Qualitative Definition |
|-------|-------------|------------------------|
| 1 | Rare | May occur in exceptional circumstances (<5% chance per year). |
| 2 | Unlikely | Could occur at some point (5‑15% chance per year). |
| 3 | Possible | Might occur at some time (15‑40% chance per year). |
| 4 | Likely | Will probably occur in most circumstances (40‑70% chance per year). |
| 5 | Almost Certain | Expected to occur in most circumstances (>70% chance per year). |

### 4.2 Impact Scale

Impact is assessed across four dimensions. The overall impact score is the **highest** of the four.

| Score | Financial | Reputational | Regulatory | Operational |
|-------|-----------|--------------|------------|-------------|
| 1 | < $50K | Minimal internal awareness | Minor fine (< $10K) | Minor disruption (< 1 hour) |
| 2 | $50K – $250K | Local media coverage | Moderate fine ($10K‑$50K) | Moderate disruption (1‑8 hours) |
| 3 | $250K – $1M | National media coverage | Significant fine ($50K‑$250K) | Major disruption (8‑24 hours) |
| 4 | $1M – $5M | International media coverage | Severe fine ($250K‑$1M) | Extended outage (24‑72 hours) |
| 5 | > $5M | Permanent brand damage | Regulatory action (> $1M, license risk) | Catastrophic outage (> 72 hours) |

### 4.3 Risk Score Calculation
