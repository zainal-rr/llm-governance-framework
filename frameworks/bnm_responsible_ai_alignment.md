# BNM Responsible AI Principles — Framework Alignment Guide

> **Bank Negara Malaysia (BNM)** has articulated five core principles for Responsible AI in financial services. This guide maps each principle to the components of the LLM Governance Framework and provides actionable implementation guidance.

---

## Overview

Bank Negara Malaysia's Responsible AI principles are published as part of its broader technology risk and financial services oversight framework. They reflect global responsible AI thinking adapted for the Malaysian financial sector context, with particular attention to consumer protection, systemic stability, and financial inclusion.

**The five BNM Responsible AI Principles are:**

| # | Principle | Core Idea |
|---|-----------|----------|
| 1 | **Accountability** | Clear ownership and governance of AI systems |
| 2 | **Transparency** | Explainable, auditable AI decision-making |
| 3 | **Ethics** | Values-aligned AI that avoids harm |
| 4 | **Fairness** | Non-discriminatory, equitable outcomes |
| 5 | **Safety & Security** | Robust, secure, and controllable AI systems |

---

## Principle 1: Accountability

### What BNM Expects

Financial institutions must establish **clear lines of accountability** for AI systems. This includes:

- **Governance structures**: Board and senior management must own AI risk. AI cannot be solely the domain of technologists.
- **Model ownership**: Every deployed AI model must have a named owner responsible for its performance, compliance, and retirement.
- **Audit trails**: Decisions made by AI systems must be traceable, and institutions must be able to reconstruct why a decision was made.
- **Human oversight**: Meaningful human review must be present for consequential decisions. "Human in the loop" cannot be a rubber stamp.
- **Vendor accountability**: Where AI is sourced from third parties, accountability remains with the regulated institution — not the vendor.

### Framework Components Addressing Accountability

| Component | How It Addresses Accountability |
|-----------|--------------------------------|
| [Model Card Template](../templates/model_card_template.md) | Section 1 defines model owner, responsible team, review schedule. Section 7 captures governance sign-off chain. |
| [Risk Assessment Template](../templates/risk_assessment_template.md) | Section 9 defines residual risk sign-off with named approvers by role. |
| [AI Incident Response](../templates/ai_incident_response.md) | Section 3 defines escalation matrix and Incident Commander role. Section 5 captures post-incident accountability. |
| [Model Registry Tool](../tools/model_registry.py) | Maintains an auditable registry of all models, their owners, and status. |
| [Vendor Assessment](../templates/vendor_ai_assessment.md) | Section 1 verifies vendor governance structures; ensures accountability stays with the institution. |

### Implementation Checklist

- [ ] AI Governance Policy published and approved by Board/Risk Committee
- [ ] Every production AI model has a named model owner
- [ ] AI oversight committee or equivalent established
- [ ] Model registry maintained and current
- [ ] Decision audit logs retained for minimum 7 years
- [ ] Annual attestation by model owners to governance committee

---

## Principle 2: Transparency

### What BNM Expects

AI systems must be **explainable** — to affected customers, to internal governance bodies, and to the regulator. Transparency has three dimensions:

- **Model transparency**: Documentation of how the model works, what data it uses, and how it was validated.
- **Decision transparency**: For consequential decisions (credit, insurance, product recommendations), the key factors driving a decision must be explainable to the individual.
- **Systemic transparency**: BNM expects regulated institutions to maintain documentation that allows regulators to assess AI risk at an institutional and systemic level.

BNM emphasises that transparency is not about full algorithmic disclosure (which may not always be practical or safe) but about **meaningful explainability** — enough for customers to understand and challenge decisions, and for governance bodies to exercise oversight.

### Framework Components Addressing Transparency

| Component | How It Addresses Transparency |
|-----------|-------------------------------|
| [Model Card Template](../templates/model_card_template.md) | Sections 1-4 document model design, training data, and evaluation results. Section 5.4 covers explainability methods. |
| [Risk Assessment Template](../templates/risk_assessment_template.md) | Section 6 (Model Risk) includes explainability assessment. |
| [AI Incident Response](../templates/ai_incident_response.md) | Section 6 includes templates for transparent communication to customers and regulators. |
| [Data Governance Checklist](../templates/data_governance_checklist.md) | Section 1 (Data Lineage) ensures the data provenance is documented. |
| [Vendor Assessment](../templates/vendor_ai_assessment.md) | Section 5 specifically evaluates vendor explainability capabilities. |

### Implementation Checklist

- [ ] All production models documented via model cards
- [ ] Explainability method defined for each model (SHAP, LIME, rule extraction, etc.)
- [ ] Adverse action notice process in place for rejected credit applicants
- [ ] Customer-facing explanation is in plain language, available in BM and English
- [ ] Internal audit team can access decision audit logs
- [ ] BNM can be provided with model documentation on request within defined SLA

---

## Principle 3: Ethics

### What BNM Expects

AI systems must be designed and operated in alignment with **ethical values**, particularly in financial services where AI can affect people's financial wellbeing, access to services, and livelihoods. BNM's ethics principle encompasses:

- **Value alignment**: AI systems should reflect the institution's stated values and the broader societal interest.
- **Harm prevention**: AI must not be deployed in ways that cause harm — financial, reputational, psychological, or societal.
- **Human dignity**: AI must not demean, manipulate, or treat customers as mere data points.
- **Right to human review**: Customers subject to consequential AI decisions must have a meaningful right to human review.
- **Prohibited practices**: Certain AI uses are incompatible with ethical conduct — social scoring, subliminal manipulation, and exploitation of vulnerabilities.

### Framework Components Addressing Ethics

| Component | How It Addresses Ethics |
|-----------|------------------------|
| [Model Card Template](../templates/model_card_template.md) | Section 5 (Ethical Considerations) covers bias analysis, vulnerable groups, and human oversight mechanisms. |
| [Risk Assessment Template](../templates/risk_assessment_template.md) | Section 3 (Stakeholder Impact) and Section 5.4 (Data Protection) address ethical risks. The EU AI Act classification (Section 1) flags unacceptable risk uses. |
| [Bias Audit Checklist](../templates/bias_audit_checklist.md) | Section D3 (Escalation Path) ensures ethics concerns reach decision-makers. |
| [Vendor Assessment](../templates/vendor_ai_assessment.md) | Section 6 (Fairness and Bias) assesses vendor ethical conduct. Red Flag RF-10 flags discriminatory outputs as a deal-breaker. |

### Implementation Checklist

- [ ] AI ethics principles formally adopted and published
- [ ] Prohibited AI use cases explicitly documented in AI Governance Policy
- [ ] Ethics review is a required gate in the AI development lifecycle
- [ ] Human review mechanism in place for consequential decisions
- [ ] Customer complaint/appeal mechanism exists for AI-influenced decisions
- [ ] AI ethics considerations included in staff training

---

## Principle 4: Fairness

### What BNM Expects

AI systems in financial services must deliver **equitable outcomes** across all customer segments. BNM's fairness principle is particularly important in Malaysia's multi-ethnic, multilingual society with significant income inequality. Expectations include:

- **Non-discrimination**: AI must not produce outcomes that systematically disadvantage customers based on race, gender, age, religion, or other protected characteristics — whether through direct discrimination or through proxy variables.
- **Financial inclusion**: AI should support — not hinder — BNM's financial inclusion agenda. Models that exclude underserved populations (B40, rural communities, East Malaysia, first-time borrowers) without objective justification are problematic.
- **Consistent treatment**: Similar customers in similar circumstances should receive similar outcomes.
- **Ongoing monitoring**: Fairness must be monitored continuously — a model that is fair at launch can become unfair as demographics shift.

### Framework Components Addressing Fairness

| Component | How It Addresses Fairness |
|-----------|--------------------------|
| [Bias Audit Checklist](../templates/bias_audit_checklist.md) | Primary template for fairness. Section A (pre-deployment), B (evaluation), C (outputs), D (monitoring), E (Malaysian context). |
| [Model Card Template](../templates/model_card_template.md) | Section 4.2 (Disaggregated Performance) and Section 5 (Ethical Considerations, Fairness Metrics). |
| [Risk Assessment Template](../templates/risk_assessment_template.md) | Section 4 (Risk Inventory) includes fairness as a risk category. Section 3.2 (Vulnerable Groups). |
| [AI Incident Response](../templates/ai_incident_response.md) | P2 incident definition includes "confirmed bias" as a trigger. Escalation matrix ensures fairness issues reach senior management. |

### Implementation Checklist

- [ ] Fairness metrics defined and thresholds set before deployment
- [ ] Disaggregated performance evaluation conducted across demographic groups
- [ ] Malaysian demographic groups explicitly included in evaluation (ethnic groups, B40/M40/T20, urban/rural, East/West Malaysia)
- [ ] Bias audit conducted pre-deployment and semi-annually in production
- [ ] Fairness monitoring automated with alerting
- [ ] Process to receive and investigate customer bias complaints

---

## Principle 5: Safety and Security

### What BNM Expects

AI systems must be **robust, reliable, and secure**. BNM's safety and security principle addresses both the technical integrity of AI systems and their operational resilience. Key expectations:

- **Technical robustness**: AI models should perform reliably under normal and stressed conditions, and should degrade gracefully rather than catastrophically when inputs are unexpected.
- **Adversarial resilience**: AI systems, especially those in financial services, are targets for adversarial manipulation. Institutions must test and harden models against deliberate misuse.
- **Operational safety**: AI systems should not create single points of failure. Fallback mechanisms must exist.
- **Data security**: The data used to train and operate AI systems must be protected from breach, poisoning, and unauthorised access.
- **Controllability**: Institutions must be able to shut down, roll back, or override AI systems — and there must be humans who know how to do so and have the authority to act.

### Framework Components Addressing Safety and Security

| Component | How It Addresses Safety and Security |
|-----------|--------------------------------------|
| [Risk Assessment Template](../templates/risk_assessment_template.md) | Section 6 (Model Risk) — adversarial robustness, drift, accuracy thresholds. Section 7 (Operational Risk) — dependencies, BCP, change management. |
| [AI Incident Response](../templates/ai_incident_response.md) | Full playbook for responding to AI safety failures. P1/P2 severity definitions include security and manipulation scenarios. |
| [Data Governance Checklist](../templates/data_governance_checklist.md) | Section 6 (Access Controls and Security) — encryption, RBAC, audit logging. |
| [Vendor Assessment](../templates/vendor_ai_assessment.md) | Section 4 (Security and Infrastructure) — certifications, encryption, pen testing, adversarial testing. |
| [Model Card Template](../templates/model_card_template.md) | Section 6 (Caveats and Recommendations) — monitoring requirements and deployment safeguards. |
| [Risk Scorer Tool](../tools/risk_scorer.py) | Automates risk scoring to surface safety issues consistently. |

### Implementation Checklist

- [ ] Adversarial testing conducted before deployment
- [ ] Fallback/manual process defined for all AI-supported functions
- [ ] Business Continuity Plan covers AI system failures
- [ ] Model monitoring in place with automated alerts
- [ ] Rollback procedure documented and tested
- [ ] CISO included in AI governance sign-off for high-risk systems
- [ ] Regular security assessments include AI components

---

## Summary Mapping Table

| BNM Principle | Primary Templates | Primary Tools | Key Metrics |
|---------------|------------------|---------------|-------------|
| **Accountability** | Model Card §7, Risk Assessment §9, Incident Response §3 | Model Registry | % models with named owner; governance sign-off rate |
| **Transparency** | Model Card §1-5, Data Governance §1 | Model Registry | % models with explainability method; audit log coverage |
| **Ethics** | Model Card §5, Risk Assessment §1 & §3 | Risk Scorer | Prohibited use case incidents; appeal rate |
| **Fairness** | Bias Audit Checklist (all), Model Card §4-5 | Risk Scorer | Fairness metric pass rates; demographic performance gaps |
| **Safety & Security** | Risk Assessment §6-7, Incident Response, Data Governance §6 | Risk Scorer | Incident frequency; MTTD/MTTR; model drift alerts |

---

## Further Reading

- [BNM Responsible AI Principles](https://www.bnm.gov.my) — Official BNM publication
- [BNM Risk Management in Technology (RMiT)](https://www.bnm.gov.my/documents/20124/938039/RMiT.pdf)
- [BNM Model Risk Management Guidelines](https://www.bnm.gov.my)
- [EU AI Act Overview](eu_ai_act_overview.md) — For international context
- [NIST AI RMF Mapping](nist_ai_rmf_mapping.md) — For implementation structure

---

*Framework version: 1.0.0 | Last updated: 2024 | [LLM Governance Framework](../README.md)*
