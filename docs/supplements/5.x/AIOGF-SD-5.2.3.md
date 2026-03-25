# AIOGF‑SD‑5.2.3 — Map AI → Humans

**Document Identifier:** AIOGF‑SD‑5.2.3  
**Related Control:** 5.2.3  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.4  
**Date:** March 2026  
**Status:** Working Draft  

---

## Licensing and Usage Notice

This supplemental document is part of the AI Operational Governance Framework (AIOGF) and is protected under the AI‑OGF Limited Use License.

You may:
- Read and reference this document for internal, non‑commercial use.

You may not:
- Reproduce, redistribute, or create derivative works.
- Use this document for commercial purposes, consulting, training, or resale.
- Use this document to train AI models or automated systems.
- Incorporate this document into tools, platforms, or governance products without written permission.

For permission requests or collaboration inquiries, visit the Permission and Collaboration page on the official AIOGF site.

---

## 5.2.3.1 Purpose of the Practice

The purpose of this practice is to identify, document, and govern all points where AI systems depend on human judgment, oversight, intervention, context, or boundary‑setting. This ensures humans remain the ultimate authority in AI‑enabled workflows, even when AI must act faster than humans to maintain safety or continuity.

This practice mitigates autonomy drift, prevents unsafe or unbounded AI behavior, and ensures that human oversight, approvals, and intervention capabilities remain enforceable.

---

## 5.2.3.2 Scope & Applicability

This practice applies to:

- All AI systems that require human oversight, approval, or intervention  
- Agentic systems, workflow‑embedded AI, hosted‑mode AI, and cloud API AI  
- Systems operating within a Constrained Autonomy Envelope (CAE)  
- Environments where AI may act autonomously but humans must remain accountable  
- Workflows where human review, override, or escalation is required  
- Safety‑critical, compliance‑critical, or high‑risk operational domains  

This practice is required whenever AI actions depend on human authority, validation, or boundary‑setting.

---

## 5.2.3.3 Recommended Practice Statement

Organizations **must document and govern all AI‑to‑human dependencies** to ensure humans retain authority over high‑risk actions, boundary‑setting, exception handling, and oversight of autonomous AI behavior.

---

## 5.2.3.4 Rationale

AI systems rely on humans for:

- contextual interpretation  
- defining safe operational boundaries  
- exception handling  
- approval of high‑risk actions  
- monitoring for drift  
- escalation during uncertainty  
- override during unsafe behavior  
- post‑action review when AI acts autonomously  

In many environments, AI must act faster than humans to prevent harm. Humans therefore define the **Constrained Autonomy Envelope (CAE)**, while retaining oversight, intervention capability, and authority over out‑of‑bounds actions.

Without explicit mapping:

- AI may exceed intended boundaries  
- Humans may not know when intervention is required  
- Oversight gaps may lead to autonomy drift  
- Escalation paths may be undefined or untested  
- High‑risk actions may occur without proper approval  

Mapping AI → humans ensures safe, accountable, and predictable operation.

---

## 5.2.3.5 Implementation Guidance

Organizations must implement a structured, repeatable process to identify, document, validate, and govern all AI‑to‑human dependencies. This includes:

- Defining human roles (operator, validator, approver, overseer)  
- Ensuring humans have visibility into AI actions and telemetry  
- Training humans on AI behavior, limitations, and escalation triggers  
- Documenting expected response times for human actions  
- Ensuring human oversight is resilient to staffing changes  
- Integrating human checkpoints into workflow engines  
- Testing human override and escalation paths regularly  

---

### 5.2.3.5.1 Preconditions

Before implementing this practice, organizations must have:

- Defined AI system boundaries and autonomy levels  
- A documented Constrained Autonomy Envelope (CAE)  
- Human roles and responsibilities for oversight and approval  
- Monitoring and alerting mechanisms for AI behavior  
- A validated escalation and override framework  
- A continuity model for human response times  

---

### 5.2.3.5.2 Scope & Impact Analysis

For each AI system:

1. **Identify all human approval points**  
   High‑risk decisions, policy changes, financial commitments, infrastructure modifications.  
   Document responsible roles, required response times, and escalation paths.

2. **Identify oversight without pre‑approval**  
   Where AI may act autonomously but humans must monitor, intervene, or review actions.

3. **Identify human‑defined safety boundaries**  
   Maximum/minimum safe values, rate‑of‑change limits, environmental constraints, escalation thresholds, override rules.

4. **Identify validation points**  
   Where humans must validate AI‑generated code, infrastructure, remediation actions, classifications, or summaries.

5. **Identify escalation paths**  
   For low confidence, missing data, conflicting outputs, anomaly detection, or boundary approaches.

6. **Identify override capabilities**  
   How humans interrupt, halt, reverse, or disable AI actions.

7. **Identify monitoring responsibilities**  
   Drift indicators, workflow depth, autonomy boundaries, safety constraints.

8. **Identify exception handling**  
   Where humans must intervene in novel, ambiguous, or conflicting situations.

9. **Identify review of out‑of‑bounds actions**  
   Where humans must review actions that exceeded the CAE or triggered safety boundaries.

---

### 5.2.3.5.3 Standards Alignment

This practice aligns with:

- **Least privilege** — humans define the limits of AI authority  
- **Separation of duties** — high‑risk actions require human approval  
- **Governance policies** — humans remain accountable for decisions  
- **Regulatory requirements** — oversight and intervention must be documented  
- **Operational continuity** — human oversight must remain available and effective  

---

### 5.2.3.5.4 Trust Relationship Evaluation

Evaluate:

- Whether AI actions require human trust before execution  
- Whether humans trust AI outputs without validation  
- Whether oversight spans multiple teams or systems  
- Whether boundary‑setting is authoritative and auditable  
- Whether escalation paths cross organizational boundaries  

Trust relationships must be explicit, validated, and monitored.

---

### 5.2.3.5.5 Privilege Escalation Assessment

AI‑to‑human dependencies can create privilege escalation risks when:

- AI acts outside the CAE  
- AI interprets ambiguous boundaries as authorization  
- Human approvals are bypassed or misrouted  
- AI executes actions faster than humans can intervene  

Organizations must detect:

- Direct escalation (AI exceeds defined authority)  
- Indirect escalation (AI acts on incomplete boundaries)  
- Lateral escalation (AI actions affect adjacent workflows)  

---

### 5.2.3.5.6 Automated Validation

Automated checks must verify:

- AI actions remain within the CAE  
- Human approval points are enforced  
- Escalation triggers fire correctly  
- Drift indicators are monitored  
- Override mechanisms are functional  
- Out‑of‑bounds actions are logged and surfaced for review  

---

### 5.2.3.5.7 Human Review Requirements

Human review is required when:

- AI actions exceed the CAE  
- High‑risk actions are proposed  
- AI encounters uncertainty or conflicting data  
- Exceptions or overrides are triggered  
- Drift indicators exceed thresholds  
- AI requests escalation or fallback activation  

Reviewers must have:

- Visibility into AI telemetry and decision context  
- Authority appropriate to the risk level  
- Access to logs of autonomous actions  

---

### 5.2.3.5.8 Downstream Impact Analysis

Organizations must evaluate how AI‑to‑human dependencies affect:

- Workflow continuity  
- Safety and compliance  
- Monitoring and observability  
- Identity and access boundaries  
- Other AI systems relying on human oversight  
- Escalation chains and fallback behavior  

AI actions requiring human oversight must not create hidden continuity risks.

---

### 5.2.3.5.9 Documentation Requirements

Organizations must document:

- All human approval points  
- Oversight responsibilities  
- Safety boundaries and CAE definitions  
- Escalation paths and response times  
- Override mechanisms  
- Drift indicators and monitoring requirements  
- Human review of out‑of‑bounds actions  
- Quarterly reviews of human dependencies  

All documentation must be retained for auditability and continuity planning.

---

## 5.2.3.6 Expected Outcomes

When implemented correctly, organizations will observe:

- Clear visibility into all AI‑to‑human dependencies  
- Humans retaining authority over high‑risk and boundary‑setting actions  
- Predictable AI behavior within the CAE  
- Faster and more reliable escalation and intervention  
- Reduced autonomy drift and unsafe behavior  
- Improved continuity and operational resilience  

---

## 5.2.3.7 Examples

### **Example 1 — AI Remediation System**
AI acts autonomously within the CAE; humans review out‑of‑bounds actions and approve high‑risk remediations.

### **Example 2 — AI Code Generator**
AI generates code; humans validate and approve deployment.

### **Example 3 — AI Medical Assistant**
AI analyzes imaging; clinicians interpret results; AI actions outside the CAE trigger alerts.

### **Example 4 — AI Facility Operations**
AI adjusts HVAC autonomously; humans monitor and intervene when thresholds are exceeded.

---

## 5.2.3.8 Notes

- Human dependencies must be reviewed quarterly.  
- Human roles must be updated after organizational changes.  
- Human approval points must be tested during continuity exercises.  
- This document is a prerequisite for **5.2.4 Map Humans → AI**.  

---

## 5.2.3.9 Cross‑References

### **Internal AIOGF Controls**

- **5.2.4 — Map Humans → AI**  
  Complements this practice by mapping the reverse dependency direction.

- **6.2.x — Autonomy Boundaries & Decision Authority**  
  AI‑to‑human dependencies define the CAE and escalation triggers.

- **7.2.x — Workflow Continuity Controls**  
  Human oversight and intervention requirements feed directly into continuity planning.

### **External Standards (Informative References — To Be Developed)**  
NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, SOC 2.
