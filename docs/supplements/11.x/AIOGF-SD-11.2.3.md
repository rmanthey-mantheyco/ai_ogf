# AIOGF‑SD‑11.2.3 — Autonomy Drift

**Document Identifier:** AIOGF‑SD‑11.2.3  
**Related Control:** 11.2.3  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.6  
**Date:** March 24, 2026  
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

## 11.2.3.1 Purpose of the Practice

The purpose of this practice is to detect and govern autonomy drift—changes in the level of autonomy an AI system exercises compared to its defined and approved autonomy boundaries.  
Autonomy drift occurs when an AI system begins to take actions with fewer checkpoints, fewer approvals, or broader scope than originally authorized.

---

## 11.2.3.2 Scope & Applicability

This practice applies to:

- AI systems performing operational or autonomous actions  
- AI systems with identity, infrastructure, or security privileges  
- multi‑AI and cross‑AI environments  
- AI systems with defined autonomy levels or tiers  
- AI systems that can trigger workflows, changes, or remediation  

---

## 11.2.3.3 Recommended Practice Statement

Organizations must monitor AI systems for autonomy drift and intervene when autonomy exceeds approved boundaries or bypasses required human checkpoints.

---

## 11.2.3.4 Rationale

Autonomy drift may occur due to:

- emergent behavior  
- cross‑AI interactions and chaining  
- model or configuration updates  
- privilege propagation  
- misconfigured workflow limits or checkpoints  

Autonomy drift can lead to:

- AI systems acting without required approvals  
- bypassed human‑in‑the‑loop controls  
- expanded impact radius of AI actions  
- increased operational and security risk  

---

## Foundational Principle

AI systems must not exceed their explicitly defined autonomy boundaries, regardless of model, environment, or memory changes.

---

## 11.2.3.5 Implementation Guidance

Organizations should:

1. **Define Autonomy Levels**  
   - Specify what actions each AI system is allowed to perform.  
   - Define which actions require human approval or checkpoints.

2. **Instrument Autonomy Controls**  
   - Enforce workflow depth limits and checkpoints.  
   - Require explicit approval for high‑impact actions.

3. **Monitor for Autonomy Drift**  
   - Detect when actions are taken without required approvals.  
   - Detect when AI systems initiate new classes of actions.

4. **Trigger Alerts and Safeguards**  
   - Generate alerts when autonomy boundaries are exceeded.  
   - Automatically pause or downgrade AI autonomy when drift is detected.

5. **Review and Correct**  
   - Require human review of autonomy drift events.  
   - Adjust configurations, permissions, or workflows as needed.

---

### 11.2.3.5.1 Preconditions

- defined autonomy levels and boundaries  
- workflow control mechanisms (checkpoints, approvals, limits)  
- telemetry pipelines capturing actions and approvals  
- identity and access controls for AI systems  

---

### 11.2.3.5.2 Scope & Impact Analysis

Evaluate:

- which AI systems can perform high‑impact actions  
- which actions must always require human approval  
- which autonomy changes pose unacceptable risk  
- how autonomy drift could affect continuity and safety  

---

### 11.2.3.5.3 Standards Alignment

Aligns with:

- least privilege  
- separation of duties  
- operational control  
- risk management  

---

### 11.2.3.5.4 Trust Relationship Evaluation

Evaluate:

- cross‑AI workflows that may increase effective autonomy  
- AI systems that can delegate or trigger other AI systems  
- trust boundaries between AI, orchestration, and identity systems  

---

### 11.2.3.5.5 Privilege Escalation Assessment

Assess:

- whether autonomy drift effectively escalates privileges  
- whether AI systems can grant themselves or others more autonomy  
- whether workflow changes bypass existing controls  

---

### 11.2.3.5.6 Automated Validation

Automated systems should:

- detect actions taken without required approvals  
- detect new action types outside the approved scope  
- enforce autonomy limits and pause execution when exceeded  

---

### 11.2.3.5.7 Human Review Requirements

Human review is required for:

- classification of autonomy drift events  
- decisions to restore, reduce, or revoke autonomy  
- approval of changes to autonomy levels or boundaries  

---

### 11.2.3.5.8 Downstream Impact Analysis

Evaluate:

- impact on operational workflows  
- impact on identity and access  
- impact on cross‑AI orchestration and chaining  
- impact on continuity and recovery plans  

---

### 11.2.3.5.9 Documentation Requirements

Document:

- autonomy definitions and boundaries  
- drift events and their root causes  
- corrective actions and configuration changes  
- decisions to adjust autonomy levels  

---

## 11.2.3.6 Business Impact

Failure to detect and govern autonomy drift may result in:

- AI systems acting without appropriate oversight  
- unauthorized or irreversible changes  
- increased likelihood of security incidents  
- regulatory and governance violations  
- loss of trust in AI‑enabled operations  

---

## 11.2.3.7 Expected Outcomes

Organizations should expect:

- early detection of autonomy expansion  
- predictable and bounded AI behavior  
- preserved human control over high‑impact actions  
- reduced risk of uncontrolled AI operations  

---

## 11.2.3.8 Examples

### Example 1 — Skipped Checkpoints  
An AI system begins executing remediation actions without previously required human approval.

### Example 2 — Expanded Action Scope  
An AI system starts modifying systems outside its originally defined domain.

### Example 3 — Cross‑AI Autonomy Amplification  
AI‑A triggers AI‑B and AI‑C in a way that effectively increases overall autonomy beyond approved limits.

---

## 11.2.3.9 Alignment to External Frameworks

NIST AI RMF — Govern (partial), Manage (extension)  
ISO/IEC 42001 — Operational Control (extension)

---

## 11.2.3.10 Notes

Autonomy drift is often subtle and may emerge from cross‑AI interactions rather than a single system’s configuration.

---

## 11.2.3.11 Cross‑References

Internal AIOGF Controls:
- 8.3.x Workflow Controls  
- 8.4.x Workflow Continuity Controls  
- 11.2.1 Behavioral Drift  
- 11.2.2 Model Drift  
- 11.2.4 Memory Drift  

External Standards:
Defined in the AIOGF Crosswalk document.
