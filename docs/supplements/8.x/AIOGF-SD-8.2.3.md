---
title: 8.2.3 Prohibited Recursive AI Calls
nav_order: 4
parent: "8.x"
---

# AIOGF‑SD‑8.2.3 — Prohibited Recursive AI Calls

**Document Identifier:** AIOGF‑SD‑8.2.3  
**Related Control:** 8.2.3  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.6  
**Date:** March 23, 2026  
**Status:** Working Draft  
© 2025–2026 Randy Manthey. All Rights Reserved.

---

## Licensing and Usage Notice

This supplemental document is part of the AI Operational Governance Framework (AI-OGF) and is protected under the AI‑OGF Limited Use License.

You may:
- Read and reference this document for internal, non‑commercial use.

You may not:
- Reproduce, redistribute, or create derivative works.
- Use this document for commercial purposes, consulting, training, or resale.
- Use this document to train AI models or automated systems.
- Incorporate this document into tools, platforms, or governance products without written permission.

For permission requests or collaboration inquiries, visit the Permission and Collaboration page on the official AI-OGF site.

---

## 8.2.3.1 Purpose of the Practice

The purpose of this practice is to prevent AI systems from initiating **recursive or self‑referential execution paths**, whether direct or indirect.  
Recursive AI calls can create unbounded execution loops, amplify errors, bypass governance controls, and generate workflows that humans cannot interrupt or understand.

This control ensures that AI systems operate within **explicitly defined, non‑recursive execution boundaries**.

---

## 8.2.3.2 Scope and Applicability

This practice applies to any AI system that:

- invokes itself directly  
- invokes another AI system that may call back into the originating system  
- participates in multi‑agent orchestration  
- generates workflows with conditional or branching logic  
- interacts with automation or orchestration layers capable of recursion  

It applies across:

- infrastructure automation  
- remediation workflows  
- identity and access operations  
- cross‑AI orchestration  
- agent‑based systems  

Stricter enforcement applies in:

- production environments  
- privileged identity workflows  
- destructive or irreversible operations  
- multi‑agent systems with circular dependencies  

---

## 8.2.3.3 Recommended Practice Statement

Organizations should prohibit direct and indirect recursive AI calls to prevent unbounded execution loops, circular dependencies, and uncontrolled workflow propagation.

---

## 8.2.3.4 Rationale

Recursive AI calls can occur when:

- an AI system calls itself  
- two AI systems call each other  
- workflows create circular dependencies  
- orchestration layers re‑invoke AI systems based on prior output  

These patterns can lead to:

- runaway automation  
- infinite or near‑infinite loops  
- cascading failures  
- privilege escalation through repeated actions  
- loss of human oversight  
- inability to interrupt execution  

Traditional governance frameworks do not define enforceable constraints on recursive AI behavior.  
This control introduces explicit prohibitions to ensure AI systems remain predictable, bounded, and safe.

---

## Foundational Principle

AI systems must not generate or participate in recursive or circular execution paths that create unbounded or uncontrolled workflow behavior.

---

## 8.2.3.5 Implementation Guidance

Organizations should implement the following:

1. **Detect Direct Recursion**
   - block any AI system from invoking itself  
   - enforce at orchestration and model‑integration layers  

2. **Detect Indirect Recursion**
   - identify circular dependencies across AI systems  
   - maintain a call graph to detect loops  

3. **Enforce Non‑Recursive Execution**
   - workflows must terminate after defined steps  
   - AI systems must not re‑invoke prior steps  

4. **Implement Recursion Guards**
   - enforce maximum call depth of one for AI‑to‑AI calls  
   - block repeated calls to the same AI system within a workflow  

5. **Alert and Pause on Detection**
   - workflows must pause when recursion is detected  
   - human review is required before continuation  

---

### 8.2.3.5.1 Preconditions

Before enforcing recursion prohibitions, organizations must:

- identify all AI‑to‑AI interactions  
- map dependencies between AI systems  
- establish workflow tracing and call‑graph visibility  
- ensure workflows can be paused or terminated  

---

### 8.2.3.5.2 Scope and Impact Analysis

Organizations should evaluate:

- whether workflows contain branching logic  
- whether AI systems call other AI systems  
- whether orchestration layers may re‑invoke AI systems  
- whether recursion could cause cascading failures  

High‑risk workflows require stricter recursion detection and earlier intervention.

---

### 8.2.3.5.3 Standards Alignment

This practice aligns with:

- least privilege  
- separation of duties  
- operational governance policies  
- risk management frameworks  

Prohibiting recursion prevents privilege escalation and uncontrolled execution through repeated or circular actions.

---

### 8.2.3.5.4 Trust Relationship Evaluation

Organizations must ensure:

- AI systems cannot create implicit trust relationships through recursion  
- cross‑AI calls are validated at each boundary  
- identity and authorization are revalidated for each call  

---

### 8.2.3.5.5 Privilege Escalation Assessment

Recursive workflows may:

- accumulate privileges across repeated steps  
- bypass access controls  
- escalate privileges indirectly  

High‑risk workflows require multi‑party approval.

---

### 8.2.3.5.6 Automated Validation

Automated systems should:

- detect direct and indirect recursion  
- block recursive execution paths  
- alert reviewers  
- validate call‑graph integrity  

---

### 8.2.3.5.7 Human Review Requirements

Human review is required when:

- recursion is detected  
- workflows involve privileged systems  
- workflows span multiple AI agents  
- execution paths are not fully observable  

Reviewers must see the full call graph and understand the recursion risk.

---

### 8.2.3.5.8 Downstream Impact Analysis

Organizations should evaluate:

- whether recursion prohibitions affect automation efficiency  
- whether workflows depend on other AI systems  
- whether failure in one step affects downstream systems  

---

### 8.2.3.5.9 Documentation Requirements

Documentation must include:

- recursion detection rules  
- call‑graph structures  
- exceptions and approvals  
- logs of workflow execution  
- validation and enforcement mechanisms  

Documentation must be auditable and version‑controlled.

---

## 8.2.3.6 Business Impact

Failure to prohibit recursive AI calls may result in:

- runaway or infinite workflows  
- cascading failures across systems  
- privilege escalation through repeated actions  
- loss of operational control  
- inability to interrupt AI‑driven processes  

---

## 8.2.3.7 Expected Outcomes

Organizations should expect:

- predictable workflow behavior  
- elimination of circular dependencies  
- improved auditability  
- reduced risk of cascading failures  
- enforceable limits on AI‑to‑AI interactions  

---

## 8.2.3.8 Examples

### Example 1: Direct Recursion Blocked  
An AI attempts to call itself.  
Execution is blocked and logged.

### Example 2: Indirect Recursion Detected  
AI system A calls AI system B, which attempts to call AI system A.  
Workflow is paused for review.

### Example 3: Orchestration Loop Prevented  
An orchestration engine attempts to re‑invoke an AI system based on its own output.  
Recursion guard blocks the call.

---

## 8.2.3.9 Alignment to External Frameworks

This control aligns with:

- NIST AI RMF (Govern, Manage)  
- ISO/IEC 42001 (Operational Control)  

Mapping classification:

- Partial Alignment  
- Extension  
- No Equivalent  

---

## 8.2.3.10 Notes

Recursion rules may vary by environment, system criticality, and autonomy level.  
Exceptions must be explicitly approved, monitored, and time‑bound.

---

## 8.2.3.11 Cross‑References

**Internal AI-OGF Controls:**  
- 8.2.1 Maximum Workflow Depth  
- 8.2.2 Mandatory Human Checkpoints  
- 8.3.x Workflow Telemetry and Interaction Controls  
- 7.2.x Destructive Action Controls  

**External Standards:**  
Defined in the AI-OGF Crosswalk document.

---

This document is part of the AI Operational Governance Framework (AI-OGF) and is protected under the AI-OGF Limited Use License.
Official source: https://rmanthey-mantheyco.github.io/ai-ogf/
