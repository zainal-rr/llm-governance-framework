# AI Risk Assessment

<!-- 
PURPOSE: This template captures the risk profile of an AI/LLM system before deployment 
and at each annual review. It must be completed before go-live and updated whenever a 
material change occurs (new use case, retraining, significant performance drift).

ALIGNED WITH: EU AI Act (risk classification), BNM Responsible AI, NIST AI RMF (MAP function)
REQUIRED BY: AI Governance Policy [Policy Ref], Model Risk Management Policy [Policy Ref]
-->

---

## Document Information

| Field | Value |
|-------|-------|
| **Assessment Title** | _ |
| **System / Model Name** | _ |
| **Version Assessed** | _ |
| **Assessment Date** | _YYYY-MM-DD_ |
| **Assessment Author(s)** | _ |
| **Next Review Date** | _YYYY-MM-DD_ |
| **Document Reference** | _e.g., RISK-2024-0012_ |

---

## 1. Risk Classification

<!-- 
STEP 1: Classify your AI system according to EU AI Act risk tiers.
Even if your bank is not in the EU, this provides a globally recognised framework.
See frameworks/eu_ai_act_overview.md for detailed guidance.
-->

### 1.1 EU AI Act Risk Tier

Select the applicable risk level:

- [ ] **Unacceptable Risk** — System must NOT be deployed (prohibited practices)
- [ ] **High Risk** — Strict requirements apply; full compliance required
- [ ] **Limited Risk** — Transparency obligations apply
- [ ] **Minimal Risk** — Standard good practice applies

**Justification for classification:**

> _Explain why this risk level was assigned. Reference specific EU AI Act Annex III categories if applicable (e.g., "This system performs creditworthiness assessment — Annex III, point 5(b).")_

### 1.2 BNM Internal Risk Classification

Per BNM's Model Risk Management Guidelines:

- [ ] **Critical Model** — Directly impacts regulatory capital, financial stability, or customer rights
- [ ] **High Importance Model** — Significant impact on business decisions or financial position
- [ ] **Standard Model** — Moderate impact, manageable risk
- [ ] **Low Importance Model** — Limited scope and impact

### 1.3 Overall Residual Risk Rating (Assessed at completion)

- [ ] **High** — Requires executive approval and enhanced monitoring
- [ ] **Medium** — Requires management approval and standard monitoring
- [ ] **Low** — Requires team-level approval

---

## 2. Use Case Description

### 2.1 System Overview

<!-- Describe what this AI system does, in plain language -->

**What it does:**
> _[2-3 sentences describing the system's function]_

**How it works:**
> _[Brief technical description — enough for a non-technical risk reviewer to understand]_

**Where it operates:**
> _[Business unit, product, customer segment affected]_

### 2.2 Decision or Output Type

Select all that apply:

- [ ] **Automated decision** — System output directly triggers an action without human review
- [ ] **Decision support** — System assists a human who makes the final decision
- [ ] **Risk flagging** — System identifies items for human investigation
- [ ] **Content generation** — System generates text, documents, or communications
- [ ] **Classification / scoring** — System categorises or scores inputs
- [ ] **Prediction** — System forecasts future events or behaviours
- [ ] **Other:** _[Describe]_

### 2.3 Scale and Frequency

| Dimension | Value |
|-----------|-------|
| **Daily transaction volume** | _e.g., ~5,000 applications/day_ |
| **Customers affected** | _e.g., ~120,000/year_ |
| **Revenue/exposure involved** | _e.g., "Loan portfolio: ~MYR 2B"_ |
| **Real-time or batch** | _ |
| **Geographic scope** | _e.g., Peninsular Malaysia only_ |

---

## 3. Stakeholder Impact Analysis

<!-- 
Identify ALL parties affected by this system — not just direct users.
Consider customers, employees, third parties, society.
-->

### 3.1 Stakeholder Map

| Stakeholder | Impact Type | Severity | Notes |
|-------------|-------------|----------|-------|
| _e.g., Retail loan applicants_ | _Credit decision outcome_ | _High_ | _Direct financial impact_ |
| _e.g., Credit analysts_ | _Workflow change_ | _Medium_ | _Model changes their review process_ |
| _e.g., Relationship managers_ | _Customer-facing decision support_ | _Medium_ | _ |
| _e.g., BNM (regulator)_ | _Regulatory risk_ | _High_ | _Must comply with guidelines_ |
| _e.g., External data providers_ | _Data dependency_ | _Low_ | _ |

### 3.2 Customer Vulnerability Assessment

Are any of the following vulnerable groups disproportionately represented in this system's scope?

| Group | Represented? | Impact Concern | Mitigation |
|-------|-------------|---------------|------------|
| Elderly customers (65+) | ☐ Yes ☐ No | _ | _ |
| Low-income / B40 households | ☐ Yes ☐ No | _ | _ |
| Persons with disabilities | ☐ Yes ☐ No | _ | _ |
| First-time borrowers / no credit history | ☐ Yes ☐ No | _ | _ |
| Customers in financial distress | ☐ Yes ☐ No | _ | _ |
| Non-native language speakers | ☐ Yes ☐ No | _ | _ |

### 3.3 Adverse Impact Scenarios

<!-- Describe the worst-case scenarios if this system fails or misbehaves -->

| Scenario | Probability | Customer Impact | Financial Impact | Reputational Impact |
|----------|-------------|-----------------|------------------|---------------------|
| _e.g., Systematic bias against demographic group_ | _Low_ | _High_ | _MYR Xm (remediation)_ | _High_ |
| _e.g., Model drift leading to over-approval_ | _Medium_ | _Medium_ | _MYR Xm (credit losses)_ | _Medium_ |
| _e.g., System unavailability_ | _Low_ | _Low_ | _MYR Xm (lost revenue)_ | _Low_ |

---

## 4. Risk Inventory

<!-- 
List all identified risks. Use one row per distinct risk.
Likelihood: 1 (Rare) – 5 (Almost Certain)
Impact: 1 (Negligible) – 5 (Catastrophic)
Risk Score = Likelihood × Impact
-->

| # | Risk | Category | Likelihood (1-5) | Impact (1-5) | Risk Score | Mitigation | Owner | Residual Risk |
|---|------|----------|-----------------|-------------|------------|------------|-------|---------------|
| 1 | _e.g., Model produces biased outcomes for protected group_ | _Fairness_ | _2_ | _5_ | _10_ | _Quarterly bias audit, threshold calibration_ | _AI Ethics_ | _Medium_ |
| 2 | _e.g., Training data becomes stale / model drifts_ | _Model_ | _3_ | _4_ | _12_ | _Monthly drift monitoring, annual retrain_ | _ML Ops_ | _Low_ |
| 3 | _e.g., Data breach of training data_ | _Data/Security_ | _2_ | _5_ | _10_ | _Encryption, access controls, DPIA_ | _CISO_ | _Low_ |
| 4 | _e.g., Third-party API dependency fails_ | _Operational_ | _3_ | _3_ | _9_ | _Fallback rule-based system, SLA with vendor_ | _Ops Risk_ | _Low_ |
| 5 | _ | _ | _ | _ | _ | _ | _ | _ |
| 6 | _ | _ | _ | _ | _ | _ | _ | _ |

**Risk Matrix Legend:**

| Score | Level |
|-------|-------|
| 1-4 | Low |
| 5-9 | Medium |
| 10-14 | High |
| 15-25 | Critical |

---

## 5. Data Risk

<!-- 
Data quality and privacy issues are the most common root cause of AI failures.
Complete this section carefully.
-->

### 5.1 Personal Data Inventory

| Data Element | Classification | PII? | Sensitive? | Justification for Use |
|-------------|---------------|------|------------|----------------------|
| _e.g., Credit score_ | _Confidential_ | _Yes_ | _No_ | _Core feature_ |
| _e.g., Income data_ | _Confidential_ | _Yes_ | _No_ | _Core feature_ |
| _e.g., NRIC (hashed)_ | _Confidential_ | _Yes_ | _No_ | _Individual linkage only_ |
| _e.g., Age_ | _Internal_ | _Yes_ | _No_ | _Risk factor_ |
| _e.g., Ethnicity_ | _Restricted_ | _Yes_ | _Yes_ | _Bias monitoring only; not a model feature_ |

### 5.2 Data Quality Assessment

| Dimension | Assessment | Score (1-5) | Notes |
|-----------|-----------|------------|-------|
| **Completeness** | _% of records complete_ | _ | _ |
| **Accuracy** | _Verified vs source_ | _ | _ |
| **Consistency** | _Cross-source consistency_ | _ | _ |
| **Timeliness** | _Data freshness_ | _ | _ |
| **Representativeness** | _Matches target population_ | _ | _ |

*Score: 1 = Poor, 5 = Excellent. Target: all dimensions ≥ 3*

### 5.3 Data Protection Compliance

- [ ] Data Protection Impact Assessment (DPIA) completed
- [ ] Lawful basis for processing personal data established (PDPA s.5)
- [ ] Data subject consent obtained (or exemption documented)
- [ ] Data minimisation applied — only necessary data collected/used
- [ ] Sensitive personal data (race, religion, health, etc.) handled per PDPA Schedule 1
- [ ] Data retention schedule defined and enforced
- [ ] Data deletion/anonymisation procedures documented
- [ ] Data breach notification procedure in place (72-hour requirement)

---

## 6. Model Risk

<!-- 
Assess the technical risks inherent to the model itself.
-->

### 6.1 Accuracy and Reliability

| Risk | Description | Likelihood | Impact | Mitigation |
|------|-------------|-----------|--------|------------|
| **Underfitting** | Model too simple, poor generalisation | _ | _ | _ |
| **Overfitting** | Model memorises training data, poor on new data | _ | _ | _ |
| **Distribution shift** | Real-world data diverges from training data | _ | _ | _ |
| **Concept drift** | Underlying patterns change over time | _ | _ | _ |
| **Edge cases** | Unexpected inputs cause erratic behaviour | _ | _ | _ |

### 6.2 Performance Monitoring Plan

| Metric | Baseline | Alert Threshold | Critical Threshold | Monitoring Frequency |
|--------|----------|----------------|-------------------|---------------------|
| _e.g., AUC-ROC_ | _0.87_ | _< 0.82_ | _< 0.78_ | _Monthly_ |
| _e.g., PSI (drift)_ | _0.05_ | _> 0.15_ | _> 0.25_ | _Weekly_ |
| _e.g., Approval rate_ | _62%_ | _± 5%_ | _± 10%_ | _Monthly_ |

### 6.3 Adversarial Robustness

<!-- Has the model been tested against deliberate manipulation or adversarial inputs? -->

- [ ] Adversarial testing / red-teaming conducted
- [ ] Model hardened against known attack vectors
- [ ] Input validation in place to reject malformed inputs
- [ ] Rate limiting and abuse detection implemented
- [ ] Anomalous input logging and alerting configured

**Adversarial risk level:** ☐ Low ☐ Medium ☐ High

**Notes:** _[Describe any specific adversarial concerns and mitigations]_

### 6.4 Model Explainability

| Aspect | Approach | Adequate? |
|--------|----------|-----------|
| **Local explainability** (per-decision) | _e.g., SHAP values_ | ☐ Yes ☐ No |
| **Global explainability** (overall behaviour) | _e.g., Feature importance_ | ☐ Yes ☐ No |
| **Customer-facing explanation** | _e.g., Top 3 factors notice_ | ☐ Yes ☐ No |
| **Regulator-facing documentation** | _e.g., Model documentation_ | ☐ Yes ☐ No |

---

## 7. Operational Risk

<!-- 
Consider what happens when systems fail, change, or interact with other systems.
-->

### 7.1 System Dependencies

| Dependency | Type | Criticality | Fallback Available? | Owner |
|------------|------|------------|--------------------|----|
| _e.g., Credit Bureau API_ | _External_ | _High_ | _Yes (cached scores 24h)_ | _Vendor_ |
| _e.g., Cloud ML Platform_ | _Internal/Cloud_ | _High_ | _On-premise fallback_ | _ML Ops_ |
| _e.g., Customer Data Platform_ | _Internal_ | _High_ | _No_ | _Data Eng_ |

### 7.2 Business Continuity

- **Recovery Time Objective (RTO):** _e.g., "< 4 hours"_
- **Recovery Point Objective (RPO):** _e.g., "< 1 hour"_
- **Fallback Procedure:** _e.g., "Revert to rule-based scoring engine v3"_
- **BC Plan Reference:** _[Link]_

### 7.3 Change Management

- [ ] Change control process defined for model updates
- [ ] Rollback procedure documented and tested
- [ ] Stakeholder notification plan for changes
- [ ] Material change threshold defined (triggers new risk assessment)

---

## 8. Regulatory Compliance Checklist

### 8.1 Malaysia PDPA (2010)

- [ ] **S.5** — Lawful basis established for processing personal data
- [ ] **S.6** — Consent obtained (or applicable exemption documented)
- [ ] **S.10** — Notice provided to data subjects
- [ ] **S.12** — Data subject access rights process in place
- [ ] **S.13** — Correction of data process in place
- [ ] **S.28** — Security safeguards implemented
- [ ] **S.129** — Cross-border transfer restrictions assessed
- [ ] **Schedule 1** — Sensitive personal data handled appropriately

### 8.2 BNM Guidelines

- [ ] **BNM/RH/GN/001** — Risk management in technology (RMiT) assessed
- [ ] **BNM Responsible AI** — Five principles addressed (see bnm_responsible_ai_alignment.md)
- [ ] **Model Risk Management** — Internal policy requirements met
- [ ] **Consumer Protection** — Adverse action notice process in place
- [ ] **Outsourcing Policy** — Vendor/cloud dependencies assessed (if applicable)

### 8.3 International Standards (as applicable)

- [ ] **EU AI Act** — Risk classification conducted; high-risk requirements identified
- [ ] **NIST AI RMF** — Framework mapping completed (see nist_ai_rmf_mapping.md)
- [ ] **ISO 27001** — Information security controls assessed
- [ ] **GDPR** — Assessed for applicability (if EU customer data processed)

### 8.4 Internal Policies

- [ ] AI Governance Policy — [Policy Ref]
- [ ] Model Risk Management Policy — [Policy Ref]
- [ ] Data Governance Policy — [Policy Ref]
- [ ] Technology Risk Policy — [Policy Ref]

---

## 9. Residual Risk Sign-off

### 9.1 Risk Summary

| Risk Domain | Inherent Risk | Mitigation Quality | Residual Risk |
|-------------|-------------|-------------------|---------------|
| Data Risk | ☐ H ☐ M ☐ L | ☐ Strong ☐ Adequate ☐ Weak | ☐ H ☐ M ☐ L |
| Model Risk | ☐ H ☐ M ☐ L | ☐ Strong ☐ Adequate ☐ Weak | ☐ H ☐ M ☐ L |
| Fairness/Bias Risk | ☐ H ☐ M ☐ L | ☐ Strong ☐ Adequate ☐ Weak | ☐ H ☐ M ☐ L |
| Operational Risk | ☐ H ☐ M ☐ L | ☐ Strong ☐ Adequate ☐ Weak | ☐ H ☐ M ☐ L |
| Regulatory Risk | ☐ H ☐ M ☐ L | ☐ Strong ☐ Adequate ☐ Weak | ☐ H ☐ M ☐ L |
| **Overall** | ☐ H ☐ M ☐ L | ☐ Strong ☐ Adequate ☐ Weak | **☐ H ☐ M ☐ L** |

### 9.2 Deployment Decision

- [ ] **Approved for Deployment** — Residual risk is acceptable; proceed with noted conditions
- [ ] **Conditional Approval** — Additional mitigations required before/after go-live (see below)
- [ ] **Deferred** — Material issues must be resolved; re-assess before deployment
- [ ] **Rejected** — Risk is unacceptable; system must be redesigned or abandoned

**Conditions / Required Actions:**

> _[List any conditions attached to approval, with owners and deadlines]_

### 9.3 Sign-off

| Role | Name | Date | Signature |
|------|------|------|-----------|
| **Risk Assessment Author** | _ | _YYYY-MM-DD_ | _ |
| **Line Manager / Model Owner** | _ | _YYYY-MM-DD_ | _ |
| **Risk & Compliance** | _ | _YYYY-MM-DD_ | _ |
| **Data Privacy Officer** | _ | _YYYY-MM-DD_ | _ |
| **CISO (if security risk ≥ High)** | _ | _YYYY-MM-DD_ | _ |
| **CRO / Executive (if overall risk = High)** | _ | _YYYY-MM-DD_ | _ |

---

*Template version: 1.0.0 | LLM Governance Framework | [llm-governance-framework](../README.md)*
