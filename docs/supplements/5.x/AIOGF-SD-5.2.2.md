---
title: 5.2.2 Map AI → AI
nav_order: 2
parent: "5.x"
---

# AIOGF‑SD‑5.2.2 — Map AI → AI

**Document Identifier:** AIOGF‑SD‑5.2.2  
**Related Control:** 5.2.2  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Framework Version:** 0.9 (Draft)  
**Document Version:** 1.6  
**Author:** Randy Manthey 
**Date:** March 2026  
**Status:** Working Draft  
© 2025–2026 Randy Manthey. All Rights Reserved.

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

## 5.2.2.1 Purpose of the Practice

The purpose of this practice is to identify, document, and govern all dependencies where one AI system relies on another AI system to perform tasks, validate outputs, make decisions, or maintain operational continuity. This mapping prevents uncontrolled automation loops, detects hidden or emergent dependencies, and reduces the blast radius of cascading AI failures.

This practice is foundational for detecting circular dependencies and ensuring that AI‑to‑AI interactions remain safe, bounded, and auditable.

---

## 5.2.2.2 Scope & Applicability

This practice applies to:

- All AI systems that call, rely on, or consume outputs from other AI systems  
- Direct and indirect AI‑to‑AI interactions  
- Synchronous and asynchronous AI workflows  
- Agentic systems, workflow engines, orchestration layers, and autonomous pipelines  
- Shared data, shared embeddings, shared memory, and shared model components  
- Any environment where AI‑generated outputs feed other AI systems  

This practice is required whenever AI systems interact, collaborate, or depend on each other for inference, validation, orchestration, or decision‑making.

---

## 5.2.2.3 Recommended Practice Statement

Organizations **must document and govern all AI‑to‑AI dependencies** to prevent cascading failures, autonomy drift, and unbounded workflow depth across interconnected AI systems.

---

## 5.2.2.4 Rationale

Modern AI systems frequently call other AI systems for:

- validation  
- summarization  
- code generation  
- remediation  
- monitoring  
- decision support  

These interactions create complex, dynamic dependency graphs. Without explicit mapping:

- multi‑AI operational chains remain hidden  
- AI systems may implicitly trust other AI systems  
- autonomy boundaries may be exceeded  
- human checkpoints may be bypassed  
- workflow depth limits may be violated  
- circular logic or runaway automation may occur  

Mapping AI → AI dependencies is essential for continuity planning, risk reduction, and safe multi‑AI orchestration.

---

## 5.2.2.5 Implementation Guidance

Organizations must implement a structured, repeatable process to identify, document, validate, and govern all AI‑to‑AI dependencies. This includes:

- Using dependency‑mapping tools capable of tracing AI‑to‑AI calls  
- Requiring teams to document AI‑to‑AI interactions during design reviews  
- Maintaining a central registry of AI systems and their dependencies  
- Validating that no AI system implicitly trusts another without justification  
- Requiring human‑validated checkpoints for high‑risk AI‑to‑AI interactions  
- Reviewing dependencies after every major model update  
- Integrating dependency maps into continuity and blast‑radius planning  

---

### 5.2.2.5.1 Preconditions

Before implementing this practice, organizations must have:

- An inventory of all AI systems in scope  
- Defined autonomy levels and workflow depth limits  
- A dependency registry or mapping tool  
- Documented trust models for AI systems  
- Monitoring and observability for AI‑to‑AI interactions  
- A continuity model for AI system failures  

---

### 5.2.2.5.2 Scope & Impact Analysis

For each AI system:

1. **Identify all direct AI dependencies**  
   Where one AI system directly calls another for inference, validation, decision support, remediation, or orchestration.  
   Document: calling system, called system, purpose, trust level, failure impact.

2. **Identify all indirect AI dependencies**  
   Through shared pipelines, monitoring systems, orchestration layers, IaC generation, or remediation engines.

3. **Identify trust relationships**  
   Full trust, partial trust, zero trust, or human‑validated trust.

4. **Identify AI‑generated inputs consumed by other AI systems**  
   Code, configuration, infrastructure, remediation actions, policy updates.

5. **Identify AI‑driven workflow chains**  
   Sequential chains such as:  
   `AI (A) → AI (B) → AI (C) → AI (D)`  
   Document workflow depth, escalation points, human checkpoints, rollback paths.

6. **Identify emergent dependencies**  
   Shared training data, embeddings, vector stores, prompt libraries, or memory systems.

---

### 5.2.2.5.3 Standards Alignment

This practice aligns with:

- **Least privilege** — AI systems must not inherit authority from other AI systems  
- **Separation of duties** — high‑risk AI‑to‑AI interactions require human checkpoints  
- **Governance policies** — AI‑to‑AI trust must be explicit and justified  
- **Regulatory requirements** — AI‑generated actions must remain auditable  
- **Operational continuity** — AI‑to‑AI failures must not cascade unchecked  

---

### 5.2.2.5.4 Trust Relationship Evaluation

Evaluate:

- Whether AI systems trust each other implicitly or explicitly  
- Whether trust is justified by validation, testing, or human oversight  
- Whether trust crosses organizational or system boundaries  
- Whether trust relationships change after model updates  
- Whether trust is inherited through shared data or shared memory  

Trust relationships must be explicit, documented, and continuously validated.

---

### 5.2.2.5.5 Privilege Escalation Assessment

AI‑to‑AI dependencies can create privilege escalation risks when:

- One AI system generates inputs consumed by another with higher authority  
- AI systems chain together to exceed workflow depth limits  
- AI systems inherit permissions through orchestration layers  
- AI systems bypass human checkpoints through automation  

Organizations must detect:

- Direct escalation (AI calls a more privileged AI system)  
- Indirect escalation (AI consumes privileged AI‑generated outputs)  
- Lateral escalation (AI actions affect adjacent workflows)  

---

### 5.2.2.5.6 Automated Validation

Automated checks must verify:

- AI‑to‑AI calls are documented and authorized  
- Trust relationships match approved configurations  
- Workflow depth limits are enforced  
- AI‑generated inputs are validated before consumption  
- Emergent dependencies are monitored  
- Circular dependencies are detected and escalated  

---

### 5.2.2.5.7 Human Review Requirements

Human review is required when:

- AI‑to‑AI interactions involve high‑risk actions  
- Trust relationships change  
- AI‑generated code, infrastructure, or remediation is consumed by another AI  
- Workflow depth exceeds thresholds  
- Emergent dependencies are detected  
- Circular dependency indicators appear  

Reviewers must have:

- Visibility into dependency graphs  
- Context for AI‑to‑AI interactions  
- Authority appropriate to the risk level  

---

### 5.2.2.5.8 Downstream Impact Analysis

Organizations must evaluate how AI‑to‑AI dependencies affect:

- Workflow continuity  
- Automation reliability  
- Monitoring and observability  
- Identity and access boundaries  
- Other AI systems consuming shared data  
- Escalation chains and fallback behavior  

AI‑to‑AI dependencies must not create hidden continuity or blast‑radius risks.

---

### 5.2.2.5.9 Documentation Requirements

Organizations must document:

- All direct and indirect AI‑to‑AI dependencies  
- Trust relationships and justification  
- AI‑generated inputs consumed by other AI systems  
- Workflow chains and depth limits  
- Emergent dependencies  
- Quarterly reviews of AI‑to‑AI dependencies  
- Updates after model retraining or fine‑tuning  

All documentation must be retained for auditability and continuity planning.

---

## 5.2.2.6 Expected Outcomes

When implemented correctly, organizations will observe:

- Clear visibility into all AI‑to‑AI dependencies  
- Reduced risk of cascading failures or runaway automation  
- Explicit trust relationships between AI systems  
- Enforcement of workflow depth and autonomy boundaries  
- Early detection of emergent or hidden dependencies  
- Improved continuity and blast‑radius control  

---

## 5.2.2.7 Examples

### **Example 1 — AI Remediation System Calling AI Monitoring System**
AI Remediation → AI Monitoring → AI Deployment  
If monitoring fails, remediation cannot validate actions.

### **Example 2 — AI Code Generator Feeding AI Deployment System**
AI Code Generator → AI Validator → AI Deployment  
If the validator fails, deployment may push unverified code.

### **Example 3 — AI Summarization Layer Feeding AI Decision Engine**
AI Summarizer → AI Decision Engine  
If summarization drifts, decision quality degrades.

### **Example 4 — Multi‑AI Workflow Chain**
AI (A) Detection → AI (B) Classification → AI (C) Remediation  
Workflow depth = 3; human checkpoint required at layer 2.

---

## 5.2.2.8 Notes

- AI‑to‑AI dependencies must be reviewed quarterly.  
- Dependencies must be updated after model retraining or fine‑tuning.  
- AI‑to‑AI trust relationships must be explicitly documented.  
- Emergent dependencies must be monitored continuously.  
- This document is a prerequisite for **5.2.5 Identify Circular Dependencies**.  

---

## 5.2.2.9 Cross‑References

### **Internal AIOGF Controls**

- **5.2.5 — Identify Circular Dependencies**  
  AI‑to‑AI mapping is required to detect circular logic and automation loops.

- **5.2.3 — Map AI → Humans**  
  Complements this practice by identifying where humans must intervene in AI‑to‑AI chains.

- **5.2.4 — Map Humans → AI**  
  Provides the reverse dependency direction for continuity planning.

- **7.2.x — Workflow Continuity Controls**  
  AI‑to‑AI dependencies directly affect continuity and blast‑radius planning.

### **External Standards (Informative References — To Be Developed)**  
NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, SOC 2.

---

This document is part of the AI Operational Governance Framework (AIOGF) and is protected under the AI-OGF Limited Use License.
Official source: https://rmanthey-mantheyco.github.io/ai-ogf/
