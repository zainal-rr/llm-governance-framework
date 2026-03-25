# AI Incident Response Playbook

<!-- 
PURPOSE: Defines the procedures for detecting, responding to, and learning from AI/LLM 
system incidents. This playbook covers failures, harmful outputs, bias events, security 
breaches, and regulatory triggers.

ALIGNED WITH: BNM RMiT (Technology Risk), BNM Responsible AI (Safety & Security),
NIST AI RMF (MANAGE 4.1-4.2), PDPA S.28 (security incidents)

OWNER: [AI Governance Team / CISO / CRO — assign one]
REVIEW FREQUENCY: Annual, or after any P1 or P2 incident
-->

---

## Document Information

| Field | Value |
|-------|-------|
| **Version** | 1.0.0 |
| **Last Updated** | _YYYY-MM-DD_ |
| **Owner** | _[Role]_ |
| **Approved By** | _[Role]_ |
| **Next Review** | _YYYY-MM-DD_ |

---

## 1. Incident Severity Classification

### Severity Levels

| Level | Name | Definition | Response Time | Resolution Target |
|-------|------|-----------|---------------|------------------|
| **P1** | Critical | AI system causing active harm, regulatory breach, or widespread customer impact | **15 minutes** | 4 hours |
| **P2** | High | Significant malfunction, confirmed bias, data breach, or potential regulatory exposure | **1 hour** | 24 hours |
| **P3** | Medium | Degraded performance, anomalous outputs, potential issue under investigation | **4 hours** | 72 hours |
| **P4** | Low | Minor issue, informational, cosmetic, or potential future risk | **Next business day** | 2 weeks |

### P1 — Critical: Examples

- AI system making **harmful automated decisions** at scale (e.g., mass wrongful rejections due to model failure)
- **Discriminatory outputs** confirmed and affecting a large number of customers
- **Personal data exfiltration** via AI system (e.g., LLM leaking PII in outputs)
- AI system **completely unavailable** for a core banking function
- **Regulator (BNM) has been notified** or is actively investigating
- AI system **manipulated by adversarial attack** affecting real decisions
- Media coverage of AI-related harm is live or imminent

### P2 — High: Examples

- Model producing **consistently biased results** for a demographic group (confirmed, but limited scale)
- **Unexpected model drift** causing materially wrong predictions
- AI system generating **offensive, illegal, or harmful content** to customers
- **Vendor AI system breach** exposing customer data
- Model outputs used to make decisions that are later found **legally non-compliant**
- Monitoring alerts showing metric breach of regulatory threshold
- Internal whistleblower complaint about AI system behaviour

### P3 — Medium: Examples

- **Performance degradation** (metrics below threshold but system still functioning)
- **Anomalous output patterns** detected but not yet confirmed as harmful
- **Feature drift** detected — inputs changing from training distribution
- Customer **complaints about unfair treatment** (individual, not confirmed systemic)
- Third-party AI tool responding with **unexpected content** in isolated cases
- Model monitoring **alert triggered** — investigation required

### P4 — Low: Examples

- Minor logging or monitoring gap discovered
- Documentation out of date for a deployed model
- Non-critical feature behaving unexpectedly
- Isolated, non-harmful anomalous output
- Potential future risk identified in risk review (not yet materialised)

---

## 2. Response Procedures

### 2.1 P1 — Critical Response

```
T+0:00   DETECT — Incident identified (automated alert, staff report, customer complaint, media)
T+0:15   NOTIFY — Incident Commander notified; war room convened (virtual or physical)
T+0:30   CONTAIN — Affected AI system suspended or isolated; fallback activated
T+1:00   ASSESS — Initial impact assessment completed; customer count and exposure quantified
T+2:00   COMMUNICATE — Internal comms to leadership; initial customer notice if required
T+4:00   RESOLVE — System restored or workaround fully operational
T+24:00  REPORT — Preliminary incident report to EXCO/Board; regulator notification if required
T+72:00  REVIEW — Post-incident review initiated
```

**P1 Immediate Actions Checklist:**

- [ ] Page Incident Commander (24/7 on-call defined — see escalation matrix)
- [ ] Convene crisis team: AI Lead, Risk, Compliance, Comms, Legal
- [ ] Suspend or isolate affected AI system immediately
- [ ] Activate fallback/manual process (see Business Continuity Plan)
- [ ] Preserve all logs and model artifacts (evidence preservation)
- [ ] Do not delete or modify any system records
- [ ] Assess customer impact — quantify volume, demographics, financial harm
- [ ] Draft internal communication for leadership
- [ ] Determine if BNM notification is required (see Section 4)
- [ ] Determine if PDPA breach notification is required (72-hour rule)

---

### 2.2 P2 — High Response

**Actions:**

- [ ] Notify AI Model Owner and Risk Officer within 1 hour
- [ ] Convene response team: AI Lead, Model Owner, Risk, Compliance
- [ ] Assess severity — could this escalate to P1?
- [ ] Increase monitoring frequency to real-time
- [ ] Isolate or throttle affected system if risk warrants it
- [ ] Begin root cause investigation
- [ ] Document all actions with timestamps
- [ ] Prepare management update within 4 hours
- [ ] Determine regulatory notification requirements
- [ ] Begin customer impact assessment

**Escalation trigger to P1:** If customer harm is confirmed, regulatory breach identified, or media exposure imminent → escalate immediately.

---

### 2.3 P3 — Medium Response

**Actions:**

- [ ] Notify Model Owner and AI Governance within 4 hours
- [ ] Log incident in incident management system
- [ ] Conduct investigation — assign owner and timeline
- [ ] Monitor for escalation indicators
- [ ] Document findings in incident log
- [ ] Assess if model requires interim mitigations
- [ ] Weekly status update until resolved

---

### 2.4 P4 — Low Response

**Actions:**

- [ ] Log in incident management system
- [ ] Assign owner during next sprint/planning cycle
- [ ] Review at next AI governance meeting
- [ ] Document resolution and close

---

## 3. Escalation Matrix

### Primary Escalation Path

| Role | Contact | P1 | P2 | P3 | P4 |
|------|---------|----|----|----|----|
| **On-Call ML Ops** | _[Contact]_ | ✅ Immediate | ✅ 1 hour | ✅ 4 hours | Next day |
| **AI Model Owner** | _[Contact]_ | ✅ Immediate | ✅ 1 hour | ✅ 4 hours | Next day |
| **AI Governance Lead** | _[Contact]_ | ✅ Immediate | ✅ 1 hour | ✅ Inform | Inform |
| **Chief Risk Officer (CRO)** | _[Contact]_ | ✅ 30 min | ✅ 2 hours | Inform | — |
| **Chief Compliance Officer** | _[Contact]_ | ✅ 30 min | ✅ 2 hours | Inform | — |
| **Chief Information Security Officer** | _[Contact]_ | ✅ 30 min | ✅ If security | — | — |
| **Chief Technology Officer** | _[Contact]_ | ✅ 1 hour | ✅ 4 hours | — | — |
| **CEO** | _[Contact]_ | ✅ 1 hour | If major | — | — |
| **Board Risk Committee** | _[Contact]_ | ✅ 4 hours | If major | — | — |
| **BNM** | See Section 4 | If required | If required | — | — |
| **Legal Counsel** | _[Contact]_ | ✅ 1 hour | ✅ 4 hours | If legal risk | — |
| **Communications / PR** | _[Contact]_ | ✅ 2 hours | If public risk | — | — |

### Incident Commander

The **Incident Commander** is the single decision-maker during a P1/P2 incident. They:
- Have authority to suspend AI systems
- Coordinate all teams
- Own external communications

**Primary IC:** _[Name, Role]_  
**Backup IC:** _[Name, Role]_

---

## 4. Regulatory Notification Procedures

### 4.1 BNM Notification

**When to notify BNM:**
- Any incident that materially impacts customer protection or financial stability
- Data breach involving customer financial data
- Significant AI system failure affecting core banking services
- Discrimination complaints being investigated that could become systemic
- Any incident where media coverage is anticipated

**How to notify:**
- Contact: BNM Supervision Department, [contact details per your licence]
- Initial notification: Within **24 hours** of P1 incident; **5 business days** for P2
- Follow-up report: Within **30 days** with full root cause and remediation

**BNM Notification Template:** See Section 5.2

### 4.2 PDPA Notification

**When required:** If incident involves a **data breach** (unauthorised access, disclosure, loss, or destruction of personal data)

- Notify affected **individuals**: As soon as reasonably practicable
- Internal escalation: Notify Data Privacy Officer immediately
- Document: All breaches must be logged regardless of notification obligation

**Note:** Malaysia's PDPA (2010) does not currently mandate regulator notification of breaches, but this is expected to change. Prepare for a 72-hour notification requirement aligned with GDPR standards.

---

## 5. Post-Incident Review Template

*Complete within 5 business days for P1/P2, within 2 weeks for P3.*

### 5.1 Incident Summary

| Field | Details |
|-------|---------|
| **Incident ID** | _INC-YYYY-NNNN_ |
| **Severity** | _P1 / P2 / P3 / P4_ |
| **AI System Affected** | _ |
| **Incident Date/Time** | _YYYY-MM-DD HH:MM (timezone)_ |
| **Detected By** | _Automated alert / Staff / Customer / Media_ |
| **Resolved Date/Time** | _ |
| **Total Duration** | _ |
| **Customers Affected** | _Count, demographics if known_ |
| **Financial Impact** | _Estimated MYR amount_ |
| **Reputational Impact** | _None / Low / Medium / High_ |
| **Regulatory Impact** | _None / Notified / Under investigation_ |

### 5.2 Timeline of Events

| Time | Event | Actor | Notes |
|------|-------|-------|-------|
| _HH:MM_ | _Incident began (estimated)_ | _ | |
| _HH:MM_ | _First detection_ | _ | |
| _HH:MM_ | _Incident Commander engaged_ | _ | |
| _HH:MM_ | _System suspended_ | _ | |
| _HH:MM_ | _Customers notified_ | _ | |
| _HH:MM_ | _Root cause identified_ | _ | |
| _HH:MM_ | _Fix deployed / system restored_ | _ | |
| _HH:MM_ | _Incident closed_ | _ | |

### 5.3 Root Cause Analysis

**Primary Root Cause:**
> _[Single sentence describing the fundamental cause]_

**Contributing Factors:**
1. _[Factor 1]_
2. _[Factor 2]_
3. _[Add as needed]_

**Five Whys Analysis:**
| Why | Answer |
|-----|--------|
| Why did the incident occur? | _ |
| Why did that happen? | _ |
| Why did that happen? | _ |
| Why did that happen? | _ |
| Why did that happen (root)? | _ |

### 5.4 What Went Well

> _[Describe what the team did effectively during response — this is important for morale and learning]_

### 5.5 What Could Be Improved

> _[Describe gaps in detection, response, communication, tooling, etc.]_

### 5.6 Action Items

| # | Action | Owner | Priority | Due Date | Status |
|---|--------|-------|----------|----------|--------|
| 1 | _ | _ | P1/P2/P3 | _YYYY-MM-DD_ | ☐ Open |
| 2 | _ | _ | _ | _YYYY-MM-DD_ | ☐ Open |
| 3 | _ | _ | _ | _YYYY-MM-DD_ | ☐ Open |

### 5.7 Sign-off

| Role | Name | Date |
|------|------|------|
| **Incident Commander** | _ | _ |
| **AI Governance Lead** | _ | _ |
| **Risk Officer** | _ | _ |
| **Compliance** | _ | _ |

---

## 6. Communication Templates

### 6.1 Internal — Initial Incident Alert

```
SUBJECT: [SEVERITY] AI Incident Alert — [System Name] — [Date]

INCIDENT ID: INC-YYYY-NNNN
SEVERITY: P[1/2/3/4]
TIME DETECTED: HH:MM [timezone]
SYSTEM AFFECTED: [System name]
STATUS: Under investigation / Contained / Resolved

SUMMARY:
[2-3 sentences describing what happened and current status]

CUSTOMER IMPACT:
[Estimated number of customers affected and nature of impact]

IMMEDIATE ACTIONS TAKEN:
- [Action 1]
- [Action 2]

NEXT UPDATE: [Time]
INCIDENT COMMANDER: [Name, contact]

For updates, join the incident channel: [Link]
```

---

### 6.2 Internal — Executive Update (P1/P2)

```
SUBJECT: Executive Briefing — AI Incident [INC-YYYY-NNNN]

TO: [CTO, CRO, CCO, CEO as appropriate]
FROM: [Incident Commander]

SITUATION SUMMARY
[System Name] experienced [brief description] at [time]. [Current status].

CUSTOMER IMPACT
Approximately [N] customers affected. Impact: [describe].

FINANCIAL EXPOSURE
Estimated: MYR [X] ([describe basis of estimate]).

REGULATORY IMPLICATIONS
[BNM notification required / not required / under assessment]. [PDPA breach / not applicable].

ACTIONS IN PROGRESS
1. [Action]
2. [Action]

DECISIONS REQUIRED FROM LEADERSHIP
1. [Decision needed, by when]
2. [Decision needed, by when]

NEXT UPDATE: [Time/Date]
```

---

### 6.3 Customer Notification — Service Disruption

```
Dear [Customer Name],

We are writing to inform you that our [service name] experienced a technical issue 
between [date/time] and [date/time].

WHAT HAPPENED
[Plain language description — avoid technical jargon]

HOW YOU MAY BE AFFECTED
[Specific, honest description of impact]

WHAT WE HAVE DONE
We have [describe fix/remediation]. The issue has been [resolved/is being resolved].

WHAT YOU NEED TO DO
[Clear action steps, or "No action is required from you."]

If you have any questions or believe you have been affected, please contact us at:
- Phone: [number] (available [hours])
- Email: [email]
- Branch: [any branch]

We sincerely apologise for any inconvenience caused.

[Name]
[Title]
[Bank Name]
[Date]
```

---

### 6.4 Regulator Notification — BNM (Template)

```
CONFIDENTIAL

TO: Bank Negara Malaysia, Supervision Department
FROM: [Bank Name], [Bank Licence Number]
DATE: [Date]
RE: Notification of AI System Incident — [Brief Description]

1. INCIDENT OVERVIEW
On [date], [Bank Name] experienced [brief description of AI incident]. This notification 
is submitted in accordance with [BNM/RMiT/relevant guideline reference].

2. NATURE OF INCIDENT
[Detailed description of what occurred, how it was detected, and its scope]

3. CUSTOMER IMPACT
[Number of affected customers, nature of impact, financial exposure]

4. IMMEDIATE ACTIONS TAKEN
[List of containment and remediation actions with dates]

5. ROOT CAUSE (PRELIMINARY / CONFIRMED)
[Root cause analysis — mark as preliminary if investigation ongoing]

6. REGULATORY IMPLICATIONS
[Assessment of regulatory breaches, consumer protection concerns, etc.]

7. REMEDIATION PLAN
[Timeline and actions for full remediation]

8. CONTACT PERSON
Name: [Name]
Title: [Title]
Phone: [Number]
Email: [Email]

We will provide a full incident report within [30 days / as agreed with BNM].

Yours sincerely,
[CEO / CRO signature]
```

---

### 6.5 Public Statement (if required)

```
STATEMENT FROM [BANK NAME] REGARDING [AI SYSTEM] SERVICE ISSUE

[Date]

[Bank Name] acknowledges that customers [experienced / may have experienced] [brief 
neutral description of issue] between [date] and [date].

We take the reliability and fairness of our services extremely seriously. Upon 
identifying this issue, we immediately [action taken]. The issue has been [resolved / 
and we are working to resolve it fully by date].

We have reviewed affected accounts and [describe any remediation, e.g., "corrected 
all affected decisions" / "contacted all affected customers directly"].

Customers who have questions are encouraged to contact our customer service team at 
[contact].

We are conducting a full review to prevent recurrence and will cooperate fully with 
any regulatory review.

[Authorised signatory]
[Title]
```

---

## Appendix: Incident Severity Decision Tree

```
Is an AI system producing harmful outputs or wrong decisions at scale?
    │
    ├─ YES → Is it affecting > 100 customers or causing financial harm?
    │           ├─ YES → P1 (Critical)
    │           └─ NO  → Is it confirmed bias or data breach?
    │                       ├─ YES → P2 (High)
    │                       └─ NO  → P3 (Medium)
    │
    └─ NO  → Is there a confirmed security, data, or bias issue?
                ├─ YES → P2 (High)
                └─ NO  → Is there performance degradation or anomaly?
                            ├─ YES → P3 (Medium)
                            └─ NO  → P4 (Low)
```

---

*Template version: 1.0.0 | LLM Governance Framework | [llm-governance-framework](../README.md)*
