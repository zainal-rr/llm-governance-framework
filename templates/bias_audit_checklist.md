# AI Bias Audit Checklist

<!-- 
PURPOSE: Structured checklist for identifying, measuring, and mitigating bias in AI systems.
To be completed: (1) before initial deployment, (2) semi-annually in production, 
(3) after any material model update or retraining.

ALIGNED WITH: BNM Responsible AI (Fairness Principle), EU AI Act Art. 10 (Data Governance),
NIST AI RMF (MEASURE 2.5, 2.6), Malaysia PDPA Schedule 1 (sensitive personal data)
-->

---

## Audit Information

| Field | Value |
|-------|-------|
| **System / Model Name** | _ |
| **Model Version** | _ |
| **Audit Type** | ☐ Pre-deployment ☐ Semi-annual ☐ Post-retraining ☐ Ad hoc |
| **Audit Date** | _YYYY-MM-DD_ |
| **Conducted By** | _ |
| **Independent Review** | ☐ Yes ☐ No |
| **Related Risk Assessment** | _[Document Ref]_ |

---

## Section A: Pre-Deployment Checklist

*Complete before any production deployment. All items must be addressed.*

### A1. Dataset Diversity Assessment

| # | Check | Status | Notes / Evidence |
|---|-------|--------|-----------------|
| A1.1 | Training dataset demographic profile documented | ☐ Done ☐ Pending ☐ N/A | |
| A1.2 | Representation of all major demographic groups assessed | ☐ Done ☐ Pending ☐ N/A | |
| A1.3 | Underrepresented groups identified and documented | ☐ Done ☐ Pending ☐ N/A | |
| A1.4 | Sample size is sufficient for disaggregated evaluation (min. 100 per group) | ☐ Done ☐ Pending ☐ N/A | |
| A1.5 | Dataset temporal span assessed for historical bias risk | ☐ Done ☐ Pending ☐ N/A | |
| A1.6 | Collection method bias assessed (e.g., selection bias, survivorship bias) | ☐ Done ☐ Pending ☐ N/A | |
| A1.7 | Labelling/annotation bias assessed (if applicable) | ☐ Done ☐ Pending ☐ N/A | |
| A1.8 | Data augmentation techniques documented and assessed for bias introduction | ☐ Done ☐ Pending ☐ N/A | |

**A1 Summary:** ☐ Pass ☐ Fail ☐ Conditional  
**Gaps/Actions:** _[Describe any gaps]_

---

### A2. Protected Attributes Handling

| # | Check | Status | Notes / Evidence |
|---|-------|--------|-----------------|
| A2.1 | All protected attributes identified (see Malaysian context in Section E) | ☐ Done ☐ Pending ☐ N/A | |
| A2.2 | Direct protected attributes excluded from model features | ☐ Done ☐ Pending ☐ N/A | |
| A2.3 | Proxy variables for protected attributes identified and assessed | ☐ Done ☐ Pending ☐ N/A | |
| A2.4 | Decision to include/exclude proxy variables documented with justification | ☐ Done ☐ Pending ☐ N/A | |
| A2.5 | Feature importance analysis conducted with bias lens | ☐ Done ☐ Pending ☐ N/A | |
| A2.6 | Correlation between model features and protected attributes quantified | ☐ Done ☐ Pending ☐ N/A | |

**Malaysian Protected Attributes to Check:**
- [ ] Ethnicity (Malay, Chinese, Indian, other Bumiputera, others)
- [ ] Religion
- [ ] Gender
- [ ] Age
- [ ] Disability status
- [ ] Nationality / citizenship status
- [ ] Socioeconomic status / income band
- [ ] Geographic region (urban/rural, state, east/west Malaysia)
- [ ] Language preference (Bahasa Malaysia, English, Mandarin, Tamil, others)

**A2 Summary:** ☐ Pass ☐ Fail ☐ Conditional  
**Gaps/Actions:** _[Describe any gaps]_

---

### A3. Fairness Metrics — Pre-Deployment

| # | Check | Status | Threshold | Measured Value | Pass? |
|---|-------|--------|-----------|----------------|-------|
| A3.1 | Demographic Parity measured | ☐ Done ☐ Pending | Diff ≤ 0.10 | _ | ☐ ☐ |
| A3.2 | Equal Opportunity (True Positive Rate parity) measured | ☐ Done ☐ Pending | Diff ≤ 0.10 | _ | ☐ ☐ |
| A3.3 | Equalised Odds measured | ☐ Done ☐ Pending | Diff ≤ 0.10 | _ | ☐ ☐ |
| A3.4 | Disparate Impact Ratio calculated | ☐ Done ☐ Pending | ≥ 0.80 | _ | ☐ ☐ |
| A3.5 | Predictive Parity assessed | ☐ Done ☐ Pending | Diff ≤ 0.10 | _ | ☐ ☐ |
| A3.6 | Individual fairness (similar individuals treated similarly) assessed | ☐ Done ☐ Pending | — | _ | ☐ ☐ |

*Adjust thresholds based on risk level and business context. Document any threshold changes.*

**A3 Summary:** ☐ Pass ☐ Fail ☐ Conditional  
**Gaps/Actions:** _[Describe any gaps]_

---

### A4. Bias Mitigation Applied

| Mitigation Type | Applied? | Technique Used | Effectiveness Assessment |
|----------------|----------|----------------|--------------------------|
| Pre-processing (data level) | ☐ Yes ☐ No ☐ N/A | _e.g., Resampling, reweighting_ | _ |
| In-processing (training level) | ☐ Yes ☐ No ☐ N/A | _e.g., Adversarial debiasing_ | _ |
| Post-processing (output level) | ☐ Yes ☐ No ☐ N/A | _e.g., Threshold calibration_ | _ |
| Fairness constraints in objective | ☐ Yes ☐ No ☐ N/A | _e.g., Fairness-aware loss_ | _ |

---

## Section B: Model Evaluation Checklist

*Detailed evaluation of model performance across groups.*

### B1. Performance Across Demographic Groups

For each relevant demographic dimension, verify that performance metrics are within acceptable bounds:

| Group | AUC-ROC | Accuracy | Precision | Recall | FPR | FNR | Within Threshold? |
|-------|---------|----------|-----------|--------|-----|-----|------------------|
| **All (overall)** | _ | _ | _ | _ | _ | _ | — |
| Male | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| Female | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| Age 18–25 | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| Age 26–40 | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| Age 41–60 | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| Age 60+ | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| Urban | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| Rural | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| Peninsular Malaysia | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| East Malaysia | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| B40 (bottom 40% income) | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| M40 | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| T20 | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |
| _[Add groups as relevant]_ | _ | _ | _ | _ | _ | _ | ☐ Yes ☐ No |

**Acceptable disparity threshold:** ☐ ±3% ☐ ±5% ☐ ±10% (document justification for chosen threshold)

**B1 Summary:** ☐ Pass ☐ Fail ☐ Conditional

---

### B2. False Positive / False Negative Parity

<!-- 
In financial services, FPR and FNR disparities can have severe impact:
- High FPR for a group → denied credit they qualify for (unfair exclusion)
- High FNR for a group → approved credit they won't repay (predatory lending risk)
Both are harmful in different ways.
-->

| # | Check | Status | Notes |
|---|-------|--------|-------|
| B2.1 | False Positive Rate compared across all demographic groups | ☐ Done ☐ Pending | |
| B2.2 | False Negative Rate compared across all demographic groups | ☐ Done ☐ Pending | |
| B2.3 | Maximum FPR disparity within acceptable threshold | ☐ Pass ☐ Fail | _Value: ___ | Threshold: _____ |
| B2.4 | Maximum FNR disparity within acceptable threshold | ☐ Pass ☐ Fail | _Value: ___ | Threshold: _____ |
| B2.5 | Trade-off between FPR and FNR parity documented and accepted | ☐ Done ☐ Pending | |
| B2.6 | Error rates by intersectional groups assessed (e.g., young + rural + female) | ☐ Done ☐ Pending ☐ N/A | |

**B2 Summary:** ☐ Pass ☐ Fail ☐ Conditional

---

### B3. Calibration Assessment

| # | Check | Status | Notes |
|---|-------|--------|-------|
| B3.1 | Model calibration assessed (predicted vs actual outcomes) | ☐ Done ☐ Pending | |
| B3.2 | Calibration compared across demographic groups | ☐ Done ☐ Pending | |
| B3.3 | Reliability diagrams / calibration plots reviewed | ☐ Done ☐ Pending | |
| B3.4 | Recalibration applied if needed | ☐ Done ☐ Pending ☐ N/A | |

---

## Section C: Output Review Checklist

*For systems generating text, recommendations, or explanations.*

### C1. Tone and Sentiment Analysis

| # | Check | Status | Notes |
|---|-------|--------|-------|
| C1.1 | Sample outputs reviewed for tone disparities across demographic groups | ☐ Done ☐ Pending ☐ N/A | |
| C1.2 | Adverse action notices reviewed for consistent, neutral tone | ☐ Done ☐ Pending ☐ N/A | |
| C1.3 | Explanations checked for accessibility across language backgrounds | ☐ Done ☐ Pending ☐ N/A | |
| C1.4 | No stigmatising or stereotyping language in outputs | ☐ Done ☐ Pending ☐ N/A | |
| C1.5 | Customer-facing language reviewed by compliance/legal | ☐ Done ☐ Pending ☐ N/A | |

### C2. Demographic Consistency Testing

| # | Check | Status | Notes |
|---|-------|--------|-------|
| C2.1 | Counterfactual testing performed (same input, changed protected attribute) | ☐ Done ☐ Pending ☐ N/A | |
| C2.2 | Output consistency verified when only protected attribute changes | ☐ Done ☐ Pending ☐ N/A | |
| C2.3 | Stereotype amplification tested (does model amplify social stereotypes?) | ☐ Done ☐ Pending ☐ N/A | |
| C2.4 | Name-based bias tested (e.g., ethnically identifiable names) | ☐ Done ☐ Pending ☐ N/A | |
| C2.5 | Language bias tested (outputs in Bahasa Malaysia vs English) | ☐ Done ☐ Pending ☐ N/A | |

### C3. Explanation Quality

| # | Check | Status | Notes |
|---|-------|--------|-------|
| C3.1 | Explanations are consistent across similar cases | ☐ Done ☐ Pending ☐ N/A | |
| C3.2 | Explanations do not inadvertently reveal protected group membership | ☐ Done ☐ Pending ☐ N/A | |
| C3.3 | Explanations are actionable (customer can act on them) | ☐ Done ☐ Pending ☐ N/A | |
| C3.4 | Explanation quality assessed for different education/literacy levels | ☐ Done ☐ Pending ☐ N/A | |

---

## Section D: Post-Deployment Monitoring Checklist

*To be repeated at defined monitoring intervals (minimum: quarterly).*

### D1. Ongoing Bias Metrics Monitoring

| Metric | Baseline (Deployment) | Current | Threshold | Alert Triggered? |
|--------|----------------------|---------|-----------|-----------------|
| Demographic Parity Difference | _ | _ | ≤ 0.10 | ☐ Yes ☐ No |
| Equal Opportunity Difference | _ | _ | ≤ 0.10 | ☐ Yes ☐ No |
| Disparate Impact Ratio | _ | _ | ≥ 0.80 | ☐ Yes ☐ No |
| FPR disparity (max group diff) | _ | _ | ≤ 0.05 | ☐ Yes ☐ No |
| Approval rate by group (drift) | _ | _ | ±5% | ☐ Yes ☐ No |

### D2. Feedback and Complaint Monitoring

| # | Check | Status | Notes |
|---|-------|--------|-------|
| D2.1 | Customer complaint/appeal logs reviewed for bias patterns | ☐ Done ☐ Pending | |
| D2.2 | Complaint rate by demographic group tracked | ☐ Done ☐ Pending | |
| D2.3 | Internal audit findings reviewed for bias indicators | ☐ Done ☐ Pending | |
| D2.4 | Staff-reported concerns reviewed | ☐ Done ☐ Pending | |
| D2.5 | Media/external bias complaints tracked | ☐ Done ☐ Pending | |

### D3. Escalation Path

If any bias threshold is breached, the following escalation applies:

| Severity | Trigger | Action | Owner | Timeframe |
|----------|---------|--------|-------|-----------|
| **Watch** | Metric approaching threshold (>80% of limit) | Increase monitoring frequency | Model Owner | Within 1 week |
| **Alert** | Threshold breached but < 2× limit | Bias review, mitigation assessment | AI Ethics + Model Owner | Within 2 weeks |
| **Critical** | Metric > 2× threshold or customer harm confirmed | Suspend affected function; emergency review | CRO + AI Committee | Within 24 hours |
| **Regulatory** | BNM inquiry or legal action | Regulator notification; legal counsel | Compliance + Legal | Within 24 hours |

---

## Section E: Malaysian Context

*Considerations specific to Malaysia's demographic and regulatory environment.*

### E1. Malaysian Ethnic Group Considerations

Malaysia's multi-ethnic society requires explicit attention to ethnic equity. The following groups should be represented in evaluation:

| Ethnic Group | Population ~% | In Training Data? | Evaluation Sample Adequate? |
|-------------|--------------|-------------------|----------------------------|
| Malay | ~70% | ☐ Yes ☐ No | ☐ Yes ☐ No |
| Chinese | ~23% | ☐ Yes ☐ No | ☐ Yes ☐ No |
| Indian | ~7% | ☐ Yes ☐ No | ☐ Yes ☐ No |
| Other Bumiputera (Sabah/Sarawak) | ~13%* | ☐ Yes ☐ No | ☐ Yes ☐ No |
| Other ethnicities | ~2% | ☐ Yes ☐ No | ☐ Yes ☐ No |

*\*Included in "Malay/Bumiputera" 70% figure above.*

> ⚠️ **Note:** Ethnicity is sensitive personal data under PDPA Schedule 1. It must NOT be used as a model feature. It may only be used for bias monitoring purposes with appropriate safeguards.

### E2. Language Equity

| # | Check | Status | Notes |
|---|-------|--------|-------|
| E2.1 | Model/system tested in Bahasa Malaysia | ☐ Done ☐ Pending ☐ N/A | |
| E2.2 | Model/system tested in English | ☐ Done ☐ Pending ☐ N/A | |
| E2.3 | Model/system tested in Mandarin (if customer-facing) | ☐ Done ☐ Pending ☐ N/A | |
| E2.4 | Model/system tested in Tamil (if customer-facing) | ☐ Done ☐ Pending ☐ N/A | |
| E2.5 | Performance parity verified across language variants | ☐ Done ☐ Pending ☐ N/A | |
| E2.6 | No systematic degradation for non-English speakers | ☐ Done ☐ Pending ☐ N/A | |

### E3. Socioeconomic Considerations

| # | Check | Status | Notes |
|---|-------|--------|-------|
| E3.1 | B40 (bottom 40% income) adequately represented | ☐ Done ☐ Pending | |
| E3.2 | Gig economy / informal income workers assessed | ☐ Done ☐ Pending | |
| E3.3 | Rural and semi-urban populations not disadvantaged | ☐ Done ☐ Pending | |
| E3.4 | East Malaysia (Sabah/Sarawak) populations assessed separately | ☐ Done ☐ Pending | |
| E3.5 | First-time borrowers (no credit history) not systematically excluded | ☐ Done ☐ Pending | |
| E3.6 | Foreign worker applicants (if applicable) assessed separately | ☐ Done ☐ Pending ☐ N/A | |

### E4. Regulatory Alignment (Malaysian Context)

| # | Check | Status | Notes |
|---|-------|--------|-------|
| E4.1 | BNM Responsible AI Fairness principle addressed | ☐ Done ☐ Pending | |
| E4.2 | Financial Services Act (FSA) 2013 — non-discriminatory treatment | ☐ Done ☐ Pending | |
| E4.3 | Equal opportunity in credit access (consistent with CCRIS data use) | ☐ Done ☐ Pending | |
| E4.4 | Compliant with BNM CCRIS and CTOS data use guidelines | ☐ Done ☐ Pending ☐ N/A | |

---

## Audit Sign-Off

### Overall Bias Audit Result

| Section | Result | Conditions |
|---------|--------|-----------|
| A: Pre-deployment Dataset & Metrics | ☐ Pass ☐ Fail ☐ Conditional | |
| B: Model Performance Evaluation | ☐ Pass ☐ Fail ☐ Conditional | |
| C: Output Review | ☐ Pass ☐ Fail ☐ Conditional | |
| D: Post-deployment Monitoring (if applicable) | ☐ Pass ☐ Fail ☐ N/A | |
| E: Malaysian Context | ☐ Pass ☐ Fail ☐ Conditional | |
| **Overall** | **☐ Pass ☐ Fail ☐ Conditional** | |

### Required Actions Before Deployment / Continuation

| # | Action | Owner | Deadline | Status |
|---|--------|-------|----------|--------|
| 1 | _ | _ | _YYYY-MM-DD_ | ☐ Open |
| 2 | _ | _ | _YYYY-MM-DD_ | ☐ Open |

### Auditor Sign-off

| Role | Name | Date |
|------|------|------|
| **Audit Lead** | _ | _YYYY-MM-DD_ |
| **AI Ethics Reviewer** | _ | _YYYY-MM-DD_ |
| **Model Owner** | _ | _YYYY-MM-DD_ |
| **Compliance** | _ | _YYYY-MM-DD_ |

---

*Template version: 1.0.0 | LLM Governance Framework | [llm-governance-framework](../README.md)*
