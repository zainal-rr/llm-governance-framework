# Data Governance Checklist for AI Systems

<!-- 
PURPOSE: Ensures that data used in AI systems is governed appropriately throughout 
its lifecycle — from collection through use, archival, and deletion.

ALIGNED WITH: Malaysia PDPA 2010, BNM RMiT (Data Management), 
NIST AI RMF (MAP 2.3, MEASURE 2.7), ISO/IEC 38505 (Data Governance)
-->

---

## Document Information

| Field | Value |
|-------|-------|
| **AI System / Model** | _ |
| **Assessment Date** | _YYYY-MM-DD_ |
| **Data Steward** | _ |
| **Data Owner (Business)** | _ |
| **Review Period** | _Annual / On material change_ |

---

## Section 1: Data Lineage Documentation

*Data lineage traces the origin, movement, transformation, and use of all data in the AI system.*

### 1.1 Data Source Inventory

For each data source, complete the following:

| Source ID | Source Name | Type | Owner | Location | Classification | Volume | Freshness |
|-----------|------------|------|-------|----------|---------------|--------|-----------|
| DS-001 | _e.g., Core Banking System_ | _Internal_ | _Core Banking Team_ | _On-premise DB_ | _Confidential_ | _5M records_ | _Real-time_ |
| DS-002 | _e.g., Credit Bureau (CCRIS)_ | _External_ | _BNM_ | _API_ | _Confidential_ | _Per query_ | _Real-time_ |
| DS-003 | _e.g., CTOS Sdn Bhd_ | _Third-party_ | _CTOS_ | _API_ | _Confidential_ | _Per query_ | _Real-time_ |
| DS-004 | _ | _ | _ | _ | _ | _ | _ |

### 1.2 Data Flow Diagram

*Attach or link to data flow diagram showing:*
- [ ] All data sources mapped
- [ ] Data ingestion pipelines documented
- [ ] Transformation/preprocessing steps captured
- [ ] Model training and inference flows
- [ ] Output data flows (where model results go)
- [ ] Data storage locations (training data, model artifacts, predictions)
- [ ] Data deletion/archival flows

**Data Flow Diagram location:** _[Link or "Attached"]_

### 1.3 Transformation Documentation

| Step | Input | Transformation | Output | Tool/System | Owner |
|------|-------|---------------|--------|------------|-------|
| 1 | _Raw loan application data_ | _Normalisation, missing value imputation_ | _Feature matrix_ | _Python / pandas_ | _Data Eng_ |
| 2 | _Customer demographics_ | _Anonymisation — NRIC hashed_ | _Anonymised features_ | _Internal script_ | _Data Privacy_ |
| 3 | _ | _ | _ | _ | _ |

---

## Section 2: Data Quality Assessment

### 2.1 Quality Dimensions

| Dimension | Definition | Assessment Method | Current Score (1-5) | Target | Pass? |
|-----------|-----------|------------------|--------------------|----|-------|
| **Completeness** | No missing critical fields | Missing value %; null counts | _ | ≥ 4 | ☐ |
| **Accuracy** | Data correctly reflects reality | Reconciliation vs source | _ | ≥ 4 | ☐ |
| **Consistency** | No contradictions across sources | Cross-source validation | _ | ≥ 4 | ☐ |
| **Timeliness** | Data is sufficiently current | Lag analysis | _ | ≥ 3 | ☐ |
| **Uniqueness** | No unintended duplicates | Deduplication check | _ | ≥ 4 | ☐ |
| **Validity** | Data conforms to defined formats/rules | Schema validation | _ | ≥ 4 | ☐ |
| **Representativeness** | Data reflects target population | Distribution analysis | _ | ≥ 3 | ☐ |

*Score: 1 = Very Poor → 5 = Excellent*

### 2.2 Data Quality Checks

| # | Check | Frequency | Last Run | Result | Owner |
|---|-------|-----------|----------|--------|-------|
| DQ-1 | Missing value rate < 5% per feature | Monthly | _YYYY-MM-DD_ | _X%_ | _ |
| DQ-2 | Outlier detection — values outside ±4σ reviewed | Monthly | _YYYY-MM-DD_ | _X flagged_ | _ |
| DQ-3 | Cross-source reconciliation | Quarterly | _YYYY-MM-DD_ | ☐ Pass ☐ Fail | _ |
| DQ-4 | Schema validation against defined spec | On ingestion | Automated | ☐ Pass ☐ Fail | _ |
| DQ-5 | Referential integrity checks | On ingestion | Automated | ☐ Pass ☐ Fail | _ |
| DQ-6 | Population distribution compared to baseline | Monthly | _YYYY-MM-DD_ | ☐ Pass ☐ Fail | _ |

### 2.3 Data Quality Issues Log

| Issue ID | Description | Severity | Date Found | Impact on AI | Status | Resolution |
|---------|-------------|---------|-----------|-------------|--------|------------|
| DQI-001 | _ | ☐ H ☐ M ☐ L | _ | _ | ☐ Open ☐ Resolved | _ |

---

## Section 3: Consent and Privacy Checklist

### 3.1 Legal Basis for Processing (PDPA S.5-6)

For each personal data category:

| Data Category | Lawful Basis | Consent Obtained? | Consent Reference | Notes |
|--------------|-------------|------------------|------------------|-------|
| Financial history | _Contract / Legitimate interest_ | ☐ Yes ☐ N/A | _ | _ |
| Identity data (name, NRIC) | _Contract_ | ☐ Yes ☐ N/A | _ | _ |
| Contact information | _Contract_ | ☐ Yes ☐ N/A | _ | _ |
| Employment/income | _Contract_ | ☐ Yes ☐ N/A | _ | _ |
| Behavioural/transaction data | _Legitimate interest / Consent_ | ☐ Yes ☐ No | _ | _ |
| Device/digital footprint | _Consent_ | ☐ Yes ☐ No | _ | _ |

### 3.2 Notice Requirements (PDPA S.10)

| # | Requirement | Status | Reference |
|---|------------|--------|-----------|
| 3.2.1 | Privacy Notice published and accessible | ☐ Done ☐ Pending | _ |
| 3.2.2 | AI-specific notice provided (how AI affects decisions) | ☐ Done ☐ Pending | _ |
| 3.2.3 | Notice available in Bahasa Malaysia and English | ☐ Done ☐ Pending | _ |
| 3.2.4 | Material changes to data use communicated to data subjects | ☐ Done ☐ Pending ☐ N/A | _ |
| 3.2.5 | Third-party data sharing disclosed in privacy notice | ☐ Done ☐ Pending ☐ N/A | _ |

### 3.3 Data Subject Rights

| Right | Mechanism in Place? | SLA | Owner |
|-------|-------------------|-----|-------|
| **Access** (S.12) — view their data | ☐ Yes ☐ No | _30 days_ | _ |
| **Correction** (S.13) — correct inaccurate data | ☐ Yes ☐ No | _21 days_ | _ |
| **Withdrawal of consent** | ☐ Yes ☐ No | _Immediate_ | _ |
| **Opt-out of direct marketing** | ☐ Yes ☐ No | _Immediate_ | _ |
| **Right of appeal** (AI decisions) | ☐ Yes ☐ No | _[Define SLA]_ | _ |

### 3.4 Sensitive Personal Data (PDPA Schedule 1)

Malaysia's PDPA defines sensitive personal data requiring enhanced protection:

| Sensitive Category | Used in AI System? | If Yes: Justification & Safeguards |
|-------------------|-------------------|------------------------------------|
| Physical/mental health | ☐ Yes ☐ No | _ |
| Political opinion | ☐ Yes ☐ No | _ |
| Religious beliefs | ☐ Yes ☐ No | _ |
| Offences / criminal record | ☐ Yes ☐ No | _ |
| Race / ethnicity | ☐ Yes (monitoring only) ☐ No | _ |
| Biometric data | ☐ Yes ☐ No | _ |
| Genetic data | ☐ Yes ☐ No | _ |

> ⚠️ Sensitive personal data requires **explicit consent** under PDPA and should not be used as model features in AI systems without strong legal justification.

---

## Section 4: Data Retention and Deletion

### 4.1 Retention Schedule

| Data Category | Retention Period | Basis | Archive Location | Deletion Method | Owner |
|--------------|-----------------|-------|-----------------|----------------|-------|
| Training dataset | _7 years_ | _BNM record-keeping_ | _S3 / on-prem_ | _Secure wipe_ | _ |
| Model predictions (logs) | _3 years_ | _Audit trail_ | _Data warehouse_ | _Automated delete_ | _ |
| Feature inputs per decision | _7 years_ | _FSA audit requirements_ | _Data warehouse_ | _Automated delete_ | _ |
| Model artifacts (weights, configs) | _As long as model active + 1 year_ | _Model reproducibility_ | _ML Registry_ | _Secure delete_ | _ |
| Audit trails | _7 years_ | _Regulatory_ | _Immutable store_ | _Archive only_ | _ |

### 4.2 Deletion Procedures

| # | Procedure | Status | Tested? | Owner |
|---|-----------|--------|---------|-------|
| 4.2.1 | Automated deletion jobs scheduled for all retention limits | ☐ Done ☐ Pending | ☐ Yes ☐ No | _ |
| 4.2.2 | Data deletion upon customer request process documented | ☐ Done ☐ Pending | ☐ Yes ☐ No | _ |
| 4.2.3 | Deletion cascades to all downstream systems (backups, analytics) | ☐ Done ☐ Pending | ☐ Yes ☐ No | _ |
| 4.2.4 | Vendor/third-party deletion obligations contractually enforced | ☐ Done ☐ Pending | ☐ Yes ☐ No | _ |
| 4.2.5 | Deletion certificates obtained from vendors on contract termination | ☐ Done ☐ Pending ☐ N/A | ☐ Yes ☐ No | _ |
| 4.2.6 | Anonymisation used where full deletion is not feasible | ☐ Done ☐ Pending ☐ N/A | ☐ Yes ☐ No | _ |

### 4.3 Anonymisation Standards

When data is anonymised rather than deleted:

| # | Standard | Applied? |
|---|----------|---------|
| 4.3.1 | k-anonymity applied (k ≥ 5 recommended) | ☐ Yes ☐ No ☐ N/A |
| 4.3.2 | l-diversity or t-closeness applied for sensitive attributes | ☐ Yes ☐ No ☐ N/A |
| 4.3.3 | Differential privacy used (if applicable) | ☐ Yes ☐ No ☐ N/A |
| 4.3.4 | Re-identification risk assessed post-anonymisation | ☐ Yes ☐ No |
| 4.3.5 | Anonymisation process independently verified | ☐ Yes ☐ No |

---

## Section 5: Cross-Border Data Transfer

*Relevant when data is sent to or processed by systems outside Malaysia.*

### 5.1 Transfer Inventory

| Transfer | Destination Country | Recipient | Data Type | Legal Mechanism | Risk |
|---------|--------------------|-----------|-----------|-----------------|----|
| _e.g., Cloud ML training_ | _US_ | _AWS / GCP / Azure_ | _Anonymised training data_ | _Contractual clauses_ | _Low_ |
| _e.g., LLM API calls_ | _US_ | _OpenAI / Anthropic_ | _Query data (may include PII)_ | _DPA + SCCs_ | _Medium_ |
| _ | _ | _ | _ | _ | _ |

### 5.2 PDPA S.129 — Cross-Border Transfer Requirements

Under PDPA S.129, personal data may only be transferred to countries with **adequate data protection** or under **approved mechanisms**:

| # | Requirement | Status | Notes |
|---|------------|--------|-------|
| 5.2.1 | Destination country assessed for PDPA adequacy | ☐ Done ☐ Pending | _ |
| 5.2.2 | If no adequacy: contractual safeguards (DPA/SCCs) in place | ☐ Done ☐ N/A | _ |
| 5.2.3 | Data subjects informed of cross-border transfer in Privacy Notice | ☐ Done ☐ Pending | _ |
| 5.2.4 | PII minimised before transfer (anonymise where possible) | ☐ Done ☐ Pending | _ |
| 5.2.5 | Vendor contractually prohibited from sub-processing without notice | ☐ Done ☐ Pending | _ |
| 5.2.6 | Transfer impact assessment conducted | ☐ Done ☐ Pending | _ |

### 5.3 Malaysia-Specific Restrictions

| # | Restriction | Applicable? | Status |
|---|------------|------------|--------|
| 5.3.1 | BNM residency requirements for financial data assessed | ☐ Yes ☐ No | _ |
| 5.3.2 | Customer financial data not stored outside Malaysia without BNM approval | ☐ Done ☐ N/A | _ |
| 5.3.3 | CDS/core banking data subject to local storage requirements | ☐ Done ☐ N/A | _ |
| 5.3.4 | Open API / PSD2-equivalent data sharing compliance assessed | ☐ Done ☐ N/A | _ |

---

## Section 6: Access Controls and Security

| # | Control | Status | Owner |
|---|---------|--------|-------|
| 6.1 | Role-based access control (RBAC) for training data | ☐ Done ☐ Pending | _ |
| 6.2 | Access to personal data limited to need-to-know basis | ☐ Done ☐ Pending | _ |
| 6.3 | All data access logged for audit trail | ☐ Done ☐ Pending | _ |
| 6.4 | Data access logs reviewed quarterly | ☐ Done ☐ Pending | _ |
| 6.5 | Training data encrypted at rest (AES-256) | ☐ Done ☐ Pending | _ |
| 6.6 | Training data encrypted in transit (TLS 1.2+) | ☐ Done ☐ Pending | _ |
| 6.7 | Developer access to production data prohibited (use sanitised data for dev/test) | ☐ Done ☐ Pending | _ |
| 6.8 | Data masking applied in non-production environments | ☐ Done ☐ Pending | _ |

---

## Sign-Off

| Role | Name | Date | Status |
|------|------|------|--------|
| **Data Steward** | _ | _YYYY-MM-DD_ | ☐ Approved |
| **Data Privacy Officer** | _ | _YYYY-MM-DD_ | ☐ Approved |
| **Data Governance Lead** | _ | _YYYY-MM-DD_ | ☐ Approved |
| **Model Owner** | _ | _YYYY-MM-DD_ | ☐ Approved |

---

*Template version: 1.0.0 | LLM Governance Framework | [llm-governance-framework](../README.md)*
