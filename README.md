# LLM Governance Framework

> **Enterprise AI Governance Toolkit for Financial Institutions**  
> Aligned with BNM Responsible AI Principles · EU AI Act · NIST AI RMF

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-1.0.0-green.svg)](CHANGELOG.md)
[![Status](https://img.shields.io/badge/status-active-brightgreen.svg)]()

---

## Overview

The **LLM Governance Framework** is an open source toolkit designed to help financial institutions responsibly deploy, monitor, and audit Large Language Models (LLMs) and AI systems. It provides structured templates, checklists, and lightweight tooling grounded in internationally recognized standards and Malaysian regulatory requirements.

This framework addresses the complete AI lifecycle from initial risk assessment and vendor due diligence, through model deployment and bias auditing, to incident response and ongoing governance oversight.

---

## Who Is This For?

| Role | How You'll Use This |
|------|---------------------|
| **AI/ML Engineers** | Model cards, bias audit checklists, risk assessment templates |
| **Risk & Compliance Officers** | Risk classification, regulatory compliance checklists, incident response |
| **Data Governance Teams** | Data lineage, consent frameworks, retention policies |
| **Procurement / Vendor Management** | Third-party AI vendor assessment questionnaire |
| **Executive / Board** | Framework alignment summaries, governance sign-off templates |
| **Legal & Privacy Teams** | PDPA compliance checklists, cross-border data transfer guidance |

---

## Regulatory Alignment

This framework is explicitly aligned with:

| Standard | Coverage |
|----------|----------|
| **BNM Responsible AI Principles** | Accountability, Transparency, Ethics, Fairness, Safety & Security |
| **EU AI Act (2024)** | Risk tier classification, prohibited practices, high-risk system requirements |
| **NIST AI RMF (2023)** | GOVERN, MAP, MEASURE, MANAGE functions |
| **Malaysia PDPA (2010)** | Personal data protection, consent, cross-border transfers |
| **ISO/IEC 42001** | AI management system alignment |

See [`frameworks/`](frameworks/) for detailed alignment guides.

---

## Repository Structure

```
llm-governance-framework/
│
├── README.md                          # This file
├── CHANGELOG.md                       # Version history
├── CONTRIBUTING.md                    # How to contribute
│
├── templates/                         # Reusable governance templates
│   ├── model_card_template.md         # Model documentation template
│   ├── risk_assessment_template.md    # AI risk assessment
│   ├── bias_audit_checklist.md        # Bias auditing checklist
│   ├── ai_incident_response.md        # Incident response playbook
│   ├── vendor_ai_assessment.md        # Third-party vendor questionnaire
│   └── data_governance_checklist.md   # Data governance for AI
│
├── frameworks/                        # Regulatory alignment guides
│   ├── bnm_responsible_ai_alignment.md
│   ├── nist_ai_rmf_mapping.md
│   └── eu_ai_act_overview.md
│
├── tools/                             # Lightweight CLI tools
│   ├── risk_scorer.py                 # Risk assessment scorer
│   └── model_registry.py             # Model registry manager
│
└── examples/                          # Filled-in worked examples
    ├── sample_model_card.md           # LoanSense AI model card
    ├── sample_risk_assessment.md      # LoanSense AI risk assessment
    └── sample_assessment.yaml        # YAML input for risk_scorer.py
```

---

## Quick Start

### 1. Assess Your AI System's Risk Level

Before deploying any AI/LLM system, complete a risk assessment:

```bash
# Copy the template
cp templates/risk_assessment_template.md my-project/risk-assessment.md

# Edit and fill in your details
# Then score it automatically:
python tools/risk_scorer.py --input examples/sample_assessment.yaml
```

### 2. Document Your Model

Every AI model in production should have a model card:

```bash
cp templates/model_card_template.md my-project/model-card.md
```

See [`examples/sample_model_card.md`](examples/sample_model_card.md) for a complete worked example.

### 3. Register Your Model

Track all AI models in your organisation:

```bash
# List all registered models
python tools/model_registry.py list

# Add a new model
python tools/model_registry.py add

# Export a governance report
python tools/model_registry.py export-report
```

### 4. Conduct Bias Audit

Before deployment and quarterly thereafter:

```bash
cp templates/bias_audit_checklist.md my-project/bias-audit.md
```

### 5. Prepare for Incidents

Ensure your team knows what to do when things go wrong:

```bash
cp templates/ai_incident_response.md my-project/incident-response.md
```

---

## Governance Principles

This framework is built on **five core principles** drawn from BNM's Responsible AI framework:

1. **Accountability** — Clear ownership of AI systems and their outcomes
2. **Transparency** — Explainable decisions, documented models, audit trails
3. **Ethics** — Values-aligned design, harm prevention, human oversight
4. **Fairness** — Bias detection and mitigation across demographic groups
5. **Safety & Security** — Adversarial robustness, incident response, data protection

---

## Templates at a Glance

### 📋 Model Card Template
Structured documentation for every AI model — training data, evaluation results, ethical considerations, and governance sign-off. Based on Google's Model Cards paper, extended for financial services.

### ⚠️ Risk Assessment Template
Comprehensive risk classification using EU AI Act risk tiers (minimal → unacceptable). Covers data risk, model risk, operational risk, and regulatory compliance.

### ⚖️ Bias Audit Checklist
Pre-deployment and post-deployment bias checks. Includes Malaysian-specific considerations (ethnic groups, language equity, economic status).

### 🚨 AI Incident Response Playbook
P1–P4 severity classification with clear response procedures, escalation matrix, and regulator notification templates.

### 🔍 Vendor AI Assessment
40+ questions for evaluating third-party AI vendors. Includes scoring rubric and red-flag deal-breakers.

### 🗄️ Data Governance Checklist
Data lineage, quality assessment, consent management, retention policies, and cross-border transfer rules under Malaysia PDPA.

---

## Tools

### `risk_scorer.py`
CLI tool that takes a YAML risk assessment and produces a weighted risk score with a markdown report.

```bash
python tools/risk_scorer.py --input examples/sample_assessment.yaml --output report.md
```

### `model_registry.py`
CLI tool to maintain a JSON registry of all AI models deployed in your organisation.

```bash
python tools/model_registry.py list
python tools/model_registry.py add
python tools/model_registry.py export-report --output model-registry-report.md
```

---

## Examples

The [`examples/`](examples/) directory contains fully worked examples using **LoanSense AI**, a fictional credit scoring model at **Amanah Digital Bank Berhad** — a fictional Malaysian bank. These demonstrate what good governance documentation looks like in practice.

---

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- How to submit new templates
- How to propose new framework sections
- The review and approval process
- Coding standards for tools

---

## Versioning

This project uses [Semantic Versioning](https://semver.org/). See [CHANGELOG.md](CHANGELOG.md) for the full history.

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

## Acknowledgements

This framework draws on:
- [Bank Negara Malaysia — Responsible AI Principles](https://www.bnm.gov.my)
- [NIST AI Risk Management Framework](https://www.nist.gov/system/files/documents/2023/01/26/AI%20RMF%201.0.pdf)
- [EU Artificial Intelligence Act](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689)
- [Google Model Cards](https://arxiv.org/abs/1810.03993)
- [Hugging Face Model Cards](https://huggingface.co/docs/hub/model-cards)
- [PDPA Malaysia 2010](https://www.pdp.gov.my)

---

*Maintained by the AI Governance Community. Not legal advice — consult qualified counsel for regulatory compliance.*
