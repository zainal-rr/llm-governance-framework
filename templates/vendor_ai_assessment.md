# Third-Party AI Vendor Assessment Questionnaire

<!-- 
PURPOSE: Due diligence framework for evaluating AI/LLM vendors before procurement 
and at annual review. Use this when procuring any AI system, API, or platform where 
a third party processes data, provides models, or delivers AI-powered decisions.

ALIGNED WITH: BNM Outsourcing Policy, BNM RMiT, PDPA S.129 (cross-border transfers),
EU AI Act (supply chain obligations), NIST AI RMF (GOVERN 1.6, 6.1)
-->

---

## Assessment Information

| Field | Value |
|-------|-------|
| **Vendor Name** | _ |
| **Product / Service** | _ |
| **Assessment Date** | _YYYY-MM-DD_ |
| **Conducted By** | _ |
| **Vendor Contact** | _ |
| **Procurement Reference** | _ |
| **Contract Value (Annual)** | _MYR_ |
| **Data Classification of Data Shared** | ☐ Public ☐ Internal ☐ Confidential ☐ Restricted |
| **BNM Outsourcing Materiality** | ☐ Material ☐ Non-material |

---

## Scoring Guide

Each question is scored 0–3:

| Score | Meaning |
|-------|---------|
| **3** | Fully satisfactory — evidence provided, meets all requirements |
| **2** | Partially satisfactory — meets requirements with minor gaps |
| **1** | Partially unsatisfactory — significant gaps; mitigation required |
| **0** | Unsatisfactory — does not meet requirement; deal-breaker risk |
| **N/A** | Not applicable to this vendor/product |

**Scoring bands:**
- **85–100%** — Proceed: Low risk
- **70–84%** — Proceed with conditions: Medium risk; mitigations required
- **50–69%** — High risk: Escalate to CRO/CISO; major mitigations required
- **< 50%** — Do not proceed: Unacceptable risk level

---

## Section 1: Company and AI Governance

| # | Question | Score (0-3) | Evidence | Notes |
|---|----------|------------|---------|-------|
| 1.1 | Does the vendor have a documented AI ethics or responsible AI policy? | | | |
| 1.2 | Is there a named individual/team accountable for AI governance at the vendor? | | | |
| 1.3 | Has the vendor published or shared their AI governance framework? | | | |
| 1.4 | Does the vendor conduct internal AI ethics reviews before releasing new models? | | | |
| 1.5 | Is the vendor subject to or compliant with any AI regulatory frameworks (EU AI Act, NIST AI RMF, ISO 42001)? | | | |
| 1.6 | Has the vendor experienced AI-related regulatory action, fines, or investigations in the past 3 years? | | | |
| 1.7 | Does the vendor have an AI incident response procedure? | | | |

**Section Score:** ___/21 (___%)

---

## Section 2: Model Development and Documentation

| # | Question | Score (0-3) | Evidence | Notes |
|---|----------|------------|---------|-------|
| 2.1 | Does the vendor provide model cards or equivalent documentation for all AI models? | | | |
| 2.2 | Is the training data clearly documented (sources, date range, volume, consent basis)? | | | |
| 2.3 | Has the vendor conducted independent validation or third-party audit of their models? | | | |
| 2.4 | Are model versioning and change management procedures documented? | | | |
| 2.5 | Does the vendor disclose when they retrain or update models? What is the notification SLA? | | | |
| 2.6 | Are performance benchmarks and evaluation results publicly available or shared upon request? | | | |
| 2.7 | Does the vendor document known limitations and out-of-scope uses for their models? | | | |
| 2.8 | Is the training data free from known copyright or licensing violations? | | | |

**Section Score:** ___/24 (___%)

---

## Section 3: Data Handling and Privacy

| # | Question | Score (0-3) | Evidence | Notes |
|---|----------|------------|---------|-------|
| 3.1 | What personal data is collected from or about your organisation's customers? | | | |
| 3.2 | Is customer data used to train or fine-tune the vendor's models? | | | |
| 3.3 | Can customers opt out of their data being used for training? | | | |
| 3.4 | Where is customer data stored (country, cloud provider, data centre)? | | | |
| 3.5 | Does the vendor comply with Malaysia PDPA 2010 requirements? | | | |
| 3.6 | Does the vendor have a Data Processing Agreement (DPA) / Data Processing Addendum available? | | | |
| 3.7 | What is the vendor's data retention policy for customer data? | | | |
| 3.8 | Can customer data be deleted upon request? What is the process and timeline? | | | |
| 3.9 | Does the vendor undergo regular data privacy audits (ISO 27701, SOC 2, etc.)? | | | |
| 3.10 | What is the vendor's process for notifying customers of a data breach? | | | |

**Section Score:** ___/30 (___%)

---

## Section 4: Security and Infrastructure

| # | Question | Score (0-3) | Evidence | Notes |
|---|----------|------------|---------|-------|
| 4.1 | Does the vendor hold relevant security certifications (ISO 27001, SOC 2 Type II, CSA STAR)? | | | |
| 4.2 | Is data encrypted in transit (TLS 1.2+) and at rest (AES-256)? | | | |
| 4.3 | Are access controls implemented using least-privilege principles? | | | |
| 4.4 | Does the vendor conduct regular penetration testing? When was the last test? | | | |
| 4.5 | Has the vendor tested their AI system against adversarial attacks or prompt injection? | | | |
| 4.6 | What is the vendor's vulnerability disclosure and patching SLA? | | | |
| 4.7 | Does the vendor have a Business Continuity Plan (BCP) and Disaster Recovery Plan (DRP)? | | | |
| 4.8 | What is the vendor's documented uptime SLA and historical availability? | | | |

**Section Score:** ___/24 (___%)

---

## Section 5: Explainability and Transparency

| # | Question | Score (0-3) | Evidence | Notes |
|---|----------|------------|---------|-------|
| 5.1 | Can the vendor provide explanations for individual AI decisions (local explainability)? | | | |
| 5.2 | Can the vendor provide global explainability (how the model works overall)? | | | |
| 5.3 | Are explanations in plain language suitable for customer communication? | | | |
| 5.4 | Does the vendor support audit trails — i.e., can you retrieve the exact input/output for any given decision? | | | |
| 5.5 | Does the vendor disclose whether their model uses black-box (opaque) architectures? | | | |
| 5.6 | Is the model's decision logic auditable by your internal risk or compliance team? | | | |

**Section Score:** ___/18 (___%)

---

## Section 6: Fairness and Bias

| # | Question | Score (0-3) | Evidence | Notes |
|---|----------|------------|---------|-------|
| 6.1 | Has the vendor conducted bias testing on their model? What fairness metrics were used? | | | |
| 6.2 | Are bias test results available for the specific use case you are deploying? | | | |
| 6.3 | Has the vendor tested performance across Malaysian demographic groups (ethnic groups, language)? | | | |
| 6.4 | Does the vendor have a process for customers to report suspected bias? | | | |
| 6.5 | What is the vendor's remediation process when bias is detected? | | | |
| 6.6 | Does the vendor commit to notification if bias is detected in their models post-deployment? | | | |

**Section Score:** ___/18 (___%)

---

## Section 7: Compliance and Legal

| # | Question | Score (0-3) | Evidence | Notes |
|---|----------|------------|---------|-------|
| 7.1 | Does the vendor's contract include explicit data protection obligations aligned with PDPA? | | | |
| 7.2 | Is the vendor willing to sign a Data Processing Agreement (DPA) meeting your requirements? | | | |
| 7.3 | Does the vendor's AI system fall under EU AI Act high-risk categories? If so, are they compliant? | | | |
| 7.4 | Does the vendor support your obligations under BNM's Outsourcing Policy? | | | |
| 7.5 | Does the vendor allow you to audit their AI systems and security controls? | | | |
| 7.6 | What jurisdiction governs the vendor contract? Is dispute resolution acceptable? | | | |
| 7.7 | Does the vendor have adequate professional indemnity / cyber liability insurance? | | | |

**Section Score:** ___/21 (___%)

---

## Section 8: Operational and SLA

| # | Question | Score (0-3) | Evidence | Notes |
|---|----------|------------|---------|-------|
| 8.1 | What is the guaranteed uptime SLA? (Target: ≥ 99.9%) | | | |
| 8.2 | What is the SLA for planned maintenance windows? Are out-of-hours windows available? | | | |
| 8.3 | What is the vendor's incident response SLA (acknowledgement, resolution by severity)? | | | |
| 8.4 | What is the support model (24/7, business hours, dedicated CSM)? | | | |
| 8.5 | Does the vendor provide a public status page and proactive incident communication? | | | |
| 8.6 | What are the exit provisions — can you migrate away? What data portability is offered? | | | |
| 8.7 | Does the vendor have a sunsetting/deprecation policy for models and APIs? | | | |
| 8.8 | What is the pricing model — are there usage caps or throttling that could affect operations? | | | |

**Section Score:** ___/24 (___%)

---

## Scoring Summary

| Section | Max Score | Actual Score | % |
|---------|-----------|-------------|---|
| 1. Company & AI Governance | 21 | | |
| 2. Model Development & Documentation | 24 | | |
| 3. Data Handling & Privacy | 30 | | |
| 4. Security & Infrastructure | 24 | | |
| 5. Explainability & Transparency | 18 | | |
| 6. Fairness & Bias | 18 | | |
| 7. Compliance & Legal | 21 | | |
| 8. Operational & SLA | 24 | | |
| **TOTAL** | **180** | | |

**Overall Score:** ___/180 (___%)

**Risk Rating:**
- [ ] Low (85–100%) — Proceed
- [ ] Medium (70–84%) — Proceed with conditions
- [ ] High (50–69%) — Escalate; major mitigations required
- [ ] Critical (<50%) — Do not proceed

---

## Red Flag Indicators (Deal-Breakers)

The following are automatic deal-breakers regardless of overall score. If any of these apply, **do not proceed without executive and legal sign-off**:

| # | Red Flag | Triggered? |
|---|----------|-----------|
| RF-1 | Vendor uses customer data to train models without explicit consent | ☐ Yes ☐ No |
| RF-2 | Customer data stored in jurisdictions with inadequate data protection (no PDPA-equivalent) | ☐ Yes ☐ No |
| RF-3 | Vendor has no data deletion capability — data cannot be removed upon contract end | ☐ Yes ☐ No |
| RF-4 | No audit rights — vendor refuses to allow security or compliance audit | ☐ Yes ☐ No |
| RF-5 | Active regulatory investigation or enforcement action against the vendor | ☐ Yes ☐ No |
| RF-6 | Vendor cannot provide any explainability for individual decisions | ☐ Yes ☐ No |
| RF-7 | No incident notification obligation — vendor not required to tell you about breaches | ☐ Yes ☐ No |
| RF-8 | Contract prohibits you from auditing, testing, or monitoring the AI system | ☐ Yes ☐ No |
| RF-9 | Vendor refuses to sign a Data Processing Agreement | ☐ Yes ☐ No |
| RF-10 | AI system is confirmed to produce discriminatory outputs and vendor has no remediation plan | ☐ Yes ☐ No |

**Red Flags Triggered:** ___/10

If **any** red flag is triggered → escalate immediately to Legal, Compliance, and CRO before proceeding.

---

## Conditions and Required Actions

*If proceeding despite gaps, document required contractual/technical conditions:*

| # | Condition | Required By | Owner | Deadline |
|---|-----------|-------------|-------|----------|
| 1 | _ | _ | _ | _ |
| 2 | _ | _ | _ | _ |

---

## Assessment Sign-Off

| Role | Name | Date | Recommendation |
|------|------|------|----------------|
| **Assessment Author** | _ | _YYYY-MM-DD_ | ☐ Proceed ☐ Conditional ☐ Decline |
| **Procurement Lead** | _ | _YYYY-MM-DD_ | ☐ Proceed ☐ Conditional ☐ Decline |
| **Risk Officer** | _ | _YYYY-MM-DD_ | ☐ Proceed ☐ Conditional ☐ Decline |
| **Data Privacy Officer** | _ | _YYYY-MM-DD_ | ☐ Proceed ☐ Conditional ☐ Decline |
| **CISO** | _ | _YYYY-MM-DD_ | ☐ Proceed ☐ Conditional ☐ Decline |
| **CRO (if Material Outsourcing)** | _ | _YYYY-MM-DD_ | ☐ Proceed ☐ Conditional ☐ Decline |

**Final Decision:** ☐ **Approved** ☐ **Approved with Conditions** ☐ **Declined**

---

*Template version: 1.0.0 | LLM Governance Framework | [llm-governance-framework](../README.md)*
