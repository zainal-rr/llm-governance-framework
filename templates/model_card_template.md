# Model Card: [Model Name]

<!-- 
GUIDANCE: A Model Card is the primary documentation artifact for any AI/ML model 
deployed in your organisation. Complete this template before any production deployment.
All sections are mandatory unless marked [Optional].
Last reviewed against: BNM Responsible AI Principles, EU AI Act Art. 13 (Transparency)
-->

---

## 1. Model Overview

<!-- Fill in the basic identity information for this model -->

| Field | Value |
|-------|-------|
| **Model Name** | _e.g., "CreditScore-LLM-v2"_ |
| **Version** | _e.g., "2.1.0"_ |
| **Model Type** | _e.g., "Classification", "LLM / Text Generation", "Regression", "Ensemble"_ |
| **Date Published** | _YYYY-MM-DD_ |
| **Last Updated** | _YYYY-MM-DD_ |
| **Primary Authors** | _Name, Team, Contact_ |
| **Owning Team** | _e.g., "AI Platform Team, Technology Division"_ |
| **Model ID / Registry Reference** | _e.g., "MODEL-2024-0042"_ |
| **Status** | _Active / Under Review / Retired_ |
| **Review Due Date** | _YYYY-MM-DD (typically annual)_ |

### 1.1 Model Description

<!-- 
Provide a plain-language description of what this model does. 
Aim for 2-4 sentences. A non-technical reader should be able to understand the core purpose.
-->

> _Describe what the model does, how it works at a high level, and what problem it solves._

### 1.2 Architecture Summary

<!-- Describe the technical architecture. Include model family, base architecture, number of parameters if known. -->

- **Architecture:** _e.g., Transformer / XGBoost / LSTM / Fine-tuned LLaMA-2_
- **Base Model (if fine-tuned):** _e.g., "GPT-4o", "BERT-base", "N/A"_
- **Approximate Parameters:** _e.g., "7B", "125M", "N/A"_
- **Framework:** _e.g., PyTorch, TensorFlow, scikit-learn_
- **Inference Latency (p95):** _e.g., "< 200ms"_

---

## 2. Intended Use

<!-- 
Define the boundaries of acceptable use. This section is critical for preventing misuse.
Be specific — vague language here leads to scope creep and governance gaps.
-->

### 2.1 Primary Use Cases

<!-- List the approved uses for this model. Number each use case. -->

1. _e.g., Automated credit scoring for personal loan applications between MYR 5,000–500,000_
2. _e.g., Pre-screening of applicants to prioritise human review queue_
3. _Add additional use cases as needed_

### 2.2 Out-of-Scope Uses

<!-- 
IMPORTANT: Explicitly state what this model should NOT be used for.
This is your first line of defence against misuse. Be specific.
-->

> ⚠️ **This model must NOT be used for:**

1. _e.g., Final approval/rejection decisions without human review_
2. _e.g., Insurance underwriting — not validated for this domain_
3. _e.g., Corporate or SME lending — trained on consumer data only_
4. _e.g., Any use involving children under 18_
5. _Add more as applicable_

### 2.3 Intended Users

<!-- Who is authorised to interact with or rely on this model's outputs? -->

| User Type | Access Level | Notes |
|-----------|-------------|-------|
| _e.g., Credit Analyst_ | _View scores + explanations_ | _Must complete AI literacy training_ |
| _e.g., Loan Officer_ | _View final recommendation_ | _Retains override authority_ |
| _e.g., Risk Team_ | _Full audit access_ | _ |
| _e.g., Customer_ | _None (indirect only)_ | _Receives outcome, not raw score_ |

### 2.4 Deployment Context

<!-- Where and how is this model deployed? -->

- **Deployment Environment:** _e.g., Internal API, cloud-hosted, on-premise_
- **Integration Points:** _e.g., "Integrated into LOS (Loan Origination System) v4.2"_
- **Human-in-the-Loop:** _Yes / No — describe oversight mechanism_
- **Real-Time or Batch:** _e.g., "Real-time API inference"_

---

## 3. Training Data

<!-- 
Data transparency is essential for understanding model limitations and potential biases.
Where data is confidential, describe it at the aggregate level (volumes, date ranges, sources).
-->

### 3.1 Training Dataset Summary

| Attribute | Details |
|-----------|---------|
| **Dataset Name(s)** | _e.g., "Internal Credit History DB v3", "Bureau Data 2018-2023"_ |
| **Data Owner** | _e.g., "Credit Risk Data Team"_ |
| **Date Range** | _e.g., "January 2018 – December 2023"_ |
| **Total Records (Training)** | _e.g., "2.4M loan applications"_ |
| **Total Records (Validation)** | _e.g., "600K loan applications"_ |
| **Total Records (Test)** | _e.g., "300K loan applications (held out)"_ |
| **Data Classification** | _e.g., Confidential / Internal / Public_ |

### 3.2 Data Sources

<!-- List all data sources. Flag any third-party or external sources. -->

1. **[Source Name]** — _Description, provider, licensing terms_
2. **[Source Name]** — _Description, provider, licensing terms_
3. _Add more as needed_

### 3.3 Preprocessing Steps

<!-- Describe key preprocessing decisions that could affect model behaviour -->

- _e.g., Removed records with >20% missing features_
- _e.g., Age and income normalised using z-score_
- _e.g., Oversampled minority class (default rate) using SMOTE_
- _e.g., PII removed: NRIC, full name, address hashed/tokenised_

### 3.4 Known Data Gaps and Limitations

<!-- 
Be honest about what the training data doesn't cover. 
This is critical for understanding where the model may underperform.
-->

- _e.g., Underrepresentation of applicants from East Malaysia (Sabah/Sarawak) — <3% of records_
- _e.g., Limited coverage of gig economy workers (non-standard income patterns)_
- _e.g., Data skewed toward urban demographics_
- _e.g., Historical bias: training period may reflect discriminatory lending practices from earlier years_

### 3.5 Data Consent and Lineage

<!-- Confirm data handling compliance -->

- [ ] Data collection was lawfully authorised under PDPA 2010
- [ ] Consent obtained or legitimate interest documented
- [ ] Data lineage documented in [link to data catalogue]
- [ ] Data sharing agreements in place for any third-party data
- [ ] Sensitive personal data (race, religion, health) excluded or justified

---

## 4. Evaluation Results

<!-- 
Report all relevant performance metrics. Use tables for clarity.
Report disaggregated metrics wherever possible — overall performance hides demographic disparities.
-->

### 4.1 Primary Performance Metrics

<!-- Fill in your model's core performance metrics -->

| Metric | Value | Threshold / Target | Pass? |
|--------|-------|--------------------|-------|
| _e.g., AUC-ROC_ | _0.87_ | _≥ 0.80_ | ✅ |
| _e.g., F1 Score_ | _0.79_ | _≥ 0.75_ | ✅ |
| _e.g., Accuracy_ | _84.2%_ | _≥ 80%_ | ✅ |
| _e.g., Precision_ | _81.1%_ | _≥ 78%_ | ✅ |
| _e.g., Recall_ | _77.4%_ | _≥ 75%_ | ✅ |
| _e.g., False Positive Rate_ | _12.3%_ | _≤ 15%_ | ✅ |

### 4.2 Disaggregated Performance by Demographic Group

<!-- 
CRITICAL: Report performance broken down by protected characteristics.
"Overall" accuracy can mask significant disparities for specific groups.
-->

| Group | AUC-ROC | Accuracy | FPR | FNR | Notes |
|-------|---------|----------|-----|-----|-------|
| _Overall_ | _ | _ | _ | _ | |
| _Male_ | _ | _ | _ | _ | |
| _Female_ | _ | _ | _ | _ | |
| _Age 18-25_ | _ | _ | _ | _ | |
| _Age 26-40_ | _ | _ | _ | _ | |
| _Age 41-60_ | _ | _ | _ | _ | |
| _Age 60+_ | _ | _ | _ | _ | |
| _Urban_ | _ | _ | _ | _ | |
| _Rural_ | _ | _ | _ | _ | |
| _[Other relevant groups]_ | _ | _ | _ | _ | |

> ⚠️ **Fairness threshold:** Maximum allowable disparity between any two demographic groups: _[specify, e.g., ±5% AUC-ROC]_

### 4.3 Benchmark Comparisons

<!-- How does this model compare to baselines or previous versions? -->

| Model | AUC-ROC | Notes |
|-------|---------|-------|
| _This Model (v2.1)_ | _ | Current version |
| _Previous Version (v2.0)_ | _ | Baseline comparison |
| _Industry Benchmark_ | _ | _[Source]_ |
| _Human Expert Baseline_ | _ | _[Sample size, conditions]_ |

### 4.4 Evaluation Methodology

<!-- Describe how evaluation was conducted -->

- **Test Set Isolation:** _Was test set held out from training? (Yes/No)_
- **Evaluation Period:** _Date range of test data_
- **Evaluation Conducted By:** _Independent team? Same team?_
- **External Validation:** _Was external/third-party validation performed?_

---

## 5. Ethical Considerations

<!-- 
This section requires careful, honest analysis. Do not minimise risks.
Governance reviewers will scrutinise this section closely.
-->

### 5.1 Bias Analysis

<!-- Describe potential sources of bias and what was done to address them -->

**Identified Bias Risks:**

| Bias Type | Description | Mitigation Applied | Residual Risk |
|-----------|-------------|-------------------|---------------|
| _e.g., Historical bias_ | _Training data reflects past discriminatory patterns_ | _Re-weighting, threshold adjustment_ | _Low_ |
| _e.g., Measurement bias_ | _Proxy variables correlate with protected attributes_ | _Feature audit, removal of proxies_ | _Medium_ |
| _e.g., Representation bias_ | _Underrepresentation of certain demographics_ | _Oversampling, held-out evaluation_ | _Low_ |

### 5.2 Fairness Metrics

<!-- Report fairness-specific metrics -->

| Fairness Metric | Value | Threshold | Pass? |
|----------------|-------|-----------|-------|
| _Demographic Parity Difference_ | _ | _≤ 0.10_ | _ |
| _Equal Opportunity Difference_ | _ | _≤ 0.10_ | _ |
| _Equalised Odds Difference_ | _ | _≤ 0.10_ | _ |
| _Disparate Impact Ratio_ | _ | _≥ 0.80_ | _ |

### 5.3 Vulnerable Groups

<!-- 
Identify groups that may be disproportionately affected by model errors.
What safeguards exist for these groups?
-->

| Group | Risk | Safeguard |
|-------|------|-----------|
| _e.g., First-time borrowers_ | _Limited credit history → higher error rate_ | _Refer to human review_ |
| _e.g., Elderly applicants_ | _Different financial patterns_ | _Age-specific threshold calibration_ |
| _e.g., Low-income applicants_ | _Disproportionate impact of false negatives_ | _Secondary review process_ |

### 5.4 Explainability and Transparency

<!-- How can model decisions be explained to affected individuals? -->

- **Explainability Method:** _e.g., SHAP values, LIME, rule extraction_
- **Explanation Available to Customers:** _Yes / No_
- **Adverse Action Notices:** _Process for notifying declined applicants_
- **Right of Appeal:** _Process for challenging decisions_

### 5.5 Human Oversight

<!-- Describe the human oversight mechanisms -->

- **Human Review Rate:** _e.g., "100% of rejections reviewed by credit analyst"_
- **Override Mechanism:** _Can humans override the model? What's the process?_
- **Escalation Path:** _When does a case escalate to senior review?_

---

## 6. Caveats and Recommendations

<!-- 
Be transparent about limitations. This section protects users from over-relying on the model
and gives future teams important context.
-->

### 6.1 Known Limitations

<!-- List specific, concrete limitations — not generic disclaimers -->

1. _e.g., Performance degrades for applications with income variability > 40% month-on-month_
2. _e.g., Not validated for applicants with income primarily in foreign currencies_
3. _e.g., Model is not robust to adversarial input (deliberate data manipulation by applicants)_
4. _e.g., Seasonal effects not captured — economic cycles may affect accuracy_

### 6.2 Deployment Recommendations

<!-- What conditions must be in place for safe deployment? -->

- [ ] Model must not be the sole decision-maker — human review required for all rejections
- [ ] Performance should be monitored monthly; full re-evaluation annually
- [ ] Alert thresholds must be set for score distribution drift
- [ ] Frontline staff must complete AI literacy training before using outputs
- [ ] _[Add institution-specific recommendations]_

### 6.3 Monitoring Requirements

| Metric | Frequency | Alert Threshold | Owner |
|--------|-----------|----------------|-------|
| _Score distribution drift_ | _Weekly_ | _PSI > 0.2_ | _ML Ops_ |
| _Approval/rejection rate change_ | _Monthly_ | _>5% shift_ | _Credit Risk_ |
| _Demographic parity metrics_ | _Monthly_ | _> threshold_ | _AI Ethics_ |
| _Model accuracy on new data_ | _Quarterly_ | _AUC < 0.80_ | _Model Owner_ |

---

## 7. Governance Sign-off

<!-- 
This section formalises the governance approval process.
All fields are mandatory before production deployment.
-->

### 7.1 Approval Record

| Role | Name | Signature / Sign-off Date | Notes |
|------|------|--------------------------|-------|
| **Model Owner** | _ | _YYYY-MM-DD_ | |
| **Risk Reviewer** | _ | _YYYY-MM-DD_ | |
| **Compliance Officer** | _ | _YYYY-MM-DD_ | |
| **Data Privacy Officer** | _ | _YYYY-MM-DD_ | |
| **Ethics/AI Governance Committee** | _ | _YYYY-MM-DD_ | |
| **CTO / Head of Technology** | _ | _YYYY-MM-DD_ | Required for high-risk systems |

### 7.2 Review Schedule

| Review Type | Frequency | Next Due | Responsible Party |
|-------------|-----------|----------|------------------|
| Performance Review | Quarterly | _YYYY-MM-DD_ | Model Owner |
| Bias Audit | Semi-annual | _YYYY-MM-DD_ | AI Ethics Team |
| Full Model Card Review | Annual | _YYYY-MM-DD_ | Model Owner + Compliance |
| Material Change Review | On change | On trigger | Model Owner |

### 7.3 Change History

| Version | Date | Changed By | Description |
|---------|------|------------|-------------|
| _1.0_ | _YYYY-MM-DD_ | _ | _Initial model card_ |
| _1.1_ | _YYYY-MM-DD_ | _ | _Updated evaluation metrics after Q1 review_ |

### 7.4 Related Documents

<!-- Link to related governance documents -->

- Risk Assessment: _[Link]_
- Bias Audit Report: _[Link]_
- Data Protection Impact Assessment (DPIA): _[Link]_
- Vendor Assessment (if applicable): _[Link]_
- Incident Response Plan: _[Link]_

---

*Template version: 1.0.0 | LLM Governance Framework | [llm-governance-framework](../README.md)*
