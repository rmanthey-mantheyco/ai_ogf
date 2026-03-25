# AIOGF‑SD‑12.2.3 — Human‑Validated Checkpoints

**Document Identifier:** AIOGF‑SD‑12.2.3  
**Related Control:** 12.2.3  
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

## 12.2.3.1 Purpose of the Practice

The purpose of this practice is to ensure that high‑risk, privileged, or safety‑critical AI actions require explicit human validation before execution.  
Human‑validated checkpoints enforce human‑in‑the‑loop control for actions that cannot be safely automated or delegated to AI systems.

---

## 12.2.3.2 Scope & Applicability

This practice applies to:

- AI systems performing privileged or destructive actions  
- AI systems modifying identity, infrastructure, or security controls  
- AI systems capable of triggering multi‑system workflows  
- AI systems operating in regulated or safety‑critical environments  
- cross‑AI workflows where one AI may amplify another’s actions  

---

## 12.2.3.3 Recommended Practice Statement

Organizations must implement human‑validated checkpoints for high‑risk AI actions, ensuring that no privileged or safety‑critical action proceeds without explicit human approval.

---

## 12.2.3.4 Rationale

AI systems may:

- misinterpret context  
- drift from intended behavior  
- escalate privileges  
- trigger cascading failures  
- act on incomplete or corrupted memory  
- initiate workflows with irreversible consequences  

Human‑validated checkpoints ensure that humans remain the final decision‑makers for actions that carry material operational, financial, or safety risk.

---

## Foundational Principle

High‑risk AI actions must not execute without explicit, informed human approval.

---

## 12.2.3.5 Implementation Guidance

Organizations should:

1. **Define High‑Risk Actions**  
   - destructive changes  
   - identity or access modifications  
   - infrastructure‑level changes  
   - irreversible or non‑rollbackable actions  
   - cross‑AI workflow triggers  

2. **Implement Checkpoint Enforcement**  
   - AI must pause execution at checkpoint boundaries  
   - AI must present a clear summary of the intended action  
   - humans must explicitly approve or deny the action  

3. **Ensure Checkpoints Are Binding**  
   - AI cannot bypass or override checkpoints  
   - AI cannot retry or escalate without approval  

4. **Log All Checkpoint Interactions**  
   - approvals  
   - denials  
   - context provided  
   - operator identity  

5. **Integrate with Override and Kill Switches**  
   - checkpoints must not block emergency intervention  

---

### 12.2.3.5.1 Preconditions

- defined autonomy levels  
- workflow instrumentation  
- identity and access controls  
- telemetry pipelines  

---

### 12.2.3.5.2 Scope & Impact Analysis

Evaluate:

- which actions require human approval  
- which actions require multi‑party approval  
- which actions require enhanced review (e.g., security, compliance)  

---

### 12.2.3.5.3 Standards Alignment

Aligns with:

- separation of duties  
- least privilege  
- operational control  
- safety‑critical system design  

---

### 12.2.3.5.4 Trust Relationship Evaluation

Evaluate:

- cross‑AI workflows  
- privilege propagation  
- identity dependencies  

---

### 12.2.3.5.5 Privilege Escalation Assessment

Assess:

- whether AI can bypass checkpoints  
- whether AI can escalate privileges through chained workflows  

---

### 12.2.3.5.6 Automated Validation

Automated systems should:

- detect missing or bypassed checkpoints  
- alert when checkpoint logic fails  
- enforce checkpoint boundaries  

---

### 12.2.3.5.7 Human Review Requirements

Human review is required for:

- all high‑risk actions  
- checkpoint approvals  
- post‑incident analysis of checkpoint failures  

---

### 12.2.3.5.8 Downstream Impact Analysis

Evaluate:

- impact on dependent systems  
- impact on identity and access  
- impact on cross‑AI interactions  

---

### 12.2.3.5.9 Documentation Requirements

Document:

- checkpoint approvals and denials  
- operator identity  
- context and justification  
- corrective actions  

---

## 12.2.3.6 Business Impact

Failure to implement human‑validated checkpoints may result in:

- unauthorized or irreversible changes  
- privilege escalation  
- governance violations  
- operational or safety incidents  

---

## 12.2.3.7 Expected Outcomes

Organizations should expect:

- predictable and controlled execution of high‑risk actions  
- preserved human authority  
- reduced risk of catastrophic failures  
- improved auditability  

---

## 12.2.3.8 Examples

### Example 1 — Privileged Identity Change  
An AI system proposes modifying an admin role; a human must approve.

### Example 2 — Infrastructure Modification  
An AI system attempts to decommission a production cluster; checkpoint halts execution until approved.

### Example 3 — Cross‑AI Workflow Trigger  
AI‑A attempts to trigger a workflow in AI‑B; checkpoint requires human validation.

---

## 12.2.3.9 Alignment to External Frameworks

NIST AI RMF — Govern (extension), Manage (extension)  
ISO/IEC 42001 — Operational Control (extension)

---

## 12.2.3.10 Notes

Checkpoints must remain enforceable even during degraded or failure conditions.

---

## 12.2.3.11 Cross‑References

Internal AIOGF Controls:
- 12.2.1 Manual Override  
- 12.2.2 Kill Switches  
- 8.4.x Override & Rollback  
- 11.x Drift Detection  

External Standards:
Defined in the AIOGF Crosswalk document.
