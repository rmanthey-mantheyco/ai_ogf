---
title: 9.2.3 Post‑Kill‑Switch Recovery
nav_order: 4
parent: "9.x"
---

# AIOGF‑SD‑9.2.3 — Circular Dependency Breakpoints

**Document Identifier:** AIOGF‑SD‑9.2.3  
**Related Control:** 9.2.3  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.6  
**Date:** March 24, 2026  
**Status:** Working Draft  
© 2025–2026 Randy Manthey. All Rights Reserved.

---

## Licensing & Usage Notice (Template v1.6)

This supplemental document is part of the AI Operational Governance Framework (AI-OGF) and is protected under the AI‑OGF Limited Use License.

You may:
- Read and reference this document for internal, non‑commercial use.

You may NOT:
- Reproduce, redistribute, or create derivative works.  
- Use this document for commercial purposes, consulting, training, or resale.  
- Use this document to train AI models or automated systems.  
- Incorporate this document into tools, platforms, or governance products without written permission.

For permission requests or collaboration inquiries, visit the Permission & Collaboration page on the official AI-OGF site.

---

## 9.2.3.1 Purpose of the Practice

The purpose of this practice is to identify, govern, and break circular dependencies between AI systems and AI‑dependent workflows, particularly in continuity and recovery scenarios.  
Circular dependencies can cause recovery processes to stall, loop indefinitely, or fail entirely when AI systems depend on each other for restoration.

---

## 9.2.3.2 Scope & Applicability

This practice applies to:

- AI‑to‑AI operational dependencies  
- AI‑driven remediation workflows  
- AI systems that maintain shared infrastructure or identity  
- AI‑orchestrated recovery pipelines  
- Multi‑AI and cross‑AI environments where workflows chain across systems  

It is especially applicable in:

- continuity planning  
- disaster recovery  
- incident response  
- large‑scale automation environments  

---

## 9.2.3.3 Recommended Practice Statement

Organizations must identify circular dependencies between AI systems and define explicit breakpoints that prevent recovery and continuity workflows from relying on AI loops.

---

## 9.2.3.4 Rationale

Circular dependencies occur when two or more AI systems or workflows depend on each other for configuration, identity, remediation, or recovery.  
Examples include:

- AI‑A depends on AI‑B for configuration, while AI‑B depends on AI‑A for identity  
- AI‑driven remediation pipelines that require other AI systems to be healthy before they can execute  
- AI systems that maintain the infrastructure or platforms they themselves run on  

During outages or degraded conditions, these loops can:

- prevent recovery from starting  
- cause repeated failures or retries  
- create deadlocks between AI systems  
- increase operational risk and downtime  

Defining breakpoints ensures that recovery can proceed even when AI systems are partially or fully unavailable.

---

## Foundational Principle

AI systems must not form circular dependencies that prevent safe, deterministic recovery during degraded or failure conditions.

---

## 9.2.3.5 Implementation Guidance

Organizations should implement the following:

1. **Map AI Dependencies**
   - Identify all AI systems and workflows involved in operations, remediation, and recovery.  
   - Document AI‑to‑AI, AI‑to‑platform, and AI‑to‑identity dependencies.

2. **Detect Circular Dependencies**
   - Analyze dependency graphs for loops (e.g., A → B → C → A).  
   - Include both direct and indirect dependencies.

3. **Define Breakpoints**
   - Identify points where AI must be removed from the loop during recovery.  
   - Define which actions must be performed by humans or non‑AI systems when breakpoints are active.

4. **Design Fallback Behavior**
   - Ensure that when a breakpoint is activated, recovery can proceed using AI‑independent paths.  
   - Document how workflows transition from AI‑dependent to AI‑independent modes.

5. **Validate Through Testing**
   - Include circular dependency scenarios in continuity and disaster recovery tests.  
   - Confirm that breakpoints activate correctly and recovery completes successfully.

6. **Monitor and Maintain**
   - Update dependency maps as AI systems evolve.  
   - Re‑evaluate breakpoints when new AI capabilities or integrations are introduced.

---

### 9.2.3.5.1 Preconditions

Organizations must:

- Maintain an inventory of AI systems and workflows.  
- Document operational, remediation, and recovery dependencies.  
- Establish continuity and recovery objectives (RTO/RPO).  
- Define roles and responsibilities for recovery execution.

---

### 9.2.3.5.2 Scope & Impact Analysis

Evaluate:

- Which AI systems are involved in recovery or remediation.  
- Which dependencies are critical for continuity.  
- Which loops would prevent recovery if AI is degraded.  
- The impact of breaking dependencies on automation and operations.

High‑impact loops must be prioritized for breakpoint definition and testing.

---

### 9.2.3.5.3 Standards Alignment

This practice aligns with:

- least privilege and separation of duties  
- operational continuity and disaster recovery policies  
- risk management and dependency management practices  

It extends traditional continuity planning by explicitly addressing AI‑to‑AI and AI‑dependent loops.

---

### 9.2.3.5.4 Trust Relationship Evaluation

Evaluate:

- AI systems that maintain or grant privileges to other AI systems.  
- AI systems that manage identity, access, or policy for their own dependencies.  
- Cross‑tenant or cross‑account AI interactions that may form loops.

Trust relationships must not create conditions where no independent authority can break the loop.

---

### 9.2.3.5.5 Privilege Escalation Assessment

Assess:

- Whether circular dependencies allow AI systems to indirectly escalate privileges.  
- Whether breakpoints could be abused to bypass normal controls.  
- Whether recovery paths grant broader access than steady‑state operations.

Breakpoints must not introduce new privilege escalation paths.

---

### 9.2.3.5.6 Automated Validation

Automated systems should:

- Analyze dependency graphs for cycles.  
- Flag newly introduced AI‑to‑AI loops.  
- Validate that breakpoints are defined for detected loops.  
- Generate alerts when recovery workflows attempt to execute within a circular dependency.

---

### 9.2.3.5.7 Human Review Requirements

Human review is required for:

- Approval of identified breakpoints.  
- Evaluation of high‑risk dependency loops.  
- Review of test results from continuity and recovery exercises involving AI loops.

Reviewers must include both technical and governance stakeholders.

---

### 9.2.3.5.8 Downstream Impact Analysis

Evaluate:

- Impact of breaking dependencies on automation pipelines.  
- Impact on identity, access, and policy enforcement.  
- Impact on cross‑AI workflows and shared services.  

Ensure that breaking a loop does not unintentionally disable critical safety or governance controls.

---

### 9.2.3.5.9 Documentation Requirements

Document:

- AI dependency maps and identified loops.  
- Defined breakpoints and their activation conditions.  
- Fallback behaviors and AI‑independent paths.  
- Test results from continuity and recovery exercises.  

Documentation must be version‑controlled and accessible during outages.

---

## 9.2.3.6 Business Impact

Failure to identify and govern circular dependencies may result in:

- recovery processes that cannot start or complete  
- deadlocks between AI systems during outages  
- extended downtime and operational disruption  
- increased financial and regulatory risk  

Circular dependencies can turn otherwise recoverable incidents into prolonged or unrecoverable failures.

---

## 9.2.3.7 Expected Outcomes

Organizations should expect:

- clear visibility into AI‑to‑AI and AI‑dependent loops  
- defined and tested breakpoints for circular dependencies  
- predictable recovery behavior under degraded conditions  
- reduced risk of AI‑driven deadlocks during continuity events  

---

## 9.2.3.8 Examples

### Example 1 — AI‑Maintained Identity and Configuration  
AI‑A manages identity policies, while AI‑B manages configuration.  
AI‑A depends on AI‑B for access, and AI‑B depends on AI‑A for identity.  
A breakpoint is defined where, during recovery, identity and configuration are restored by human‑operated tools instead of AI.

### Example 2 — Cross‑AI Remediation Loop  
AI‑A triggers remediation actions in AI‑B, while AI‑B triggers validation checks in AI‑A.  
During an outage, this loop prevents remediation from completing.  
A breakpoint disables cross‑AI remediation and routes actions to a human‑controlled workflow.

### Example 3 — AI‑Orchestrated Recovery Pipeline  
An AI‑based orchestrator coordinates recovery steps across multiple AI systems.  
If the orchestrator and its dependencies form a loop, recovery stalls.  
A breakpoint allows a human‑operated orchestration path to take over.

---

## 9.2.3.9 Alignment to External Frameworks

This control aligns with and extends concepts defined in established frameworks, including:

### NIST AI Risk Management Framework (AI RMF)
- Govern — partial alignment  
- Manage — extension  

### ISO/IEC 42001
- Monitoring and measurement — partial alignment  
- Operational control — extension  

Mapping classification:
- Partial Alignment — External frameworks define related concepts but do not enforce this control at runtime.  
- Extension — AI-OGF introduces additional operational or enforceable requirements.

---

## 9.2.3.10 Notes

Circular dependency analysis must be revisited regularly as AI systems, workflows, and integrations evolve.  
New AI capabilities and cross‑system automations can silently introduce loops if not governed.

---

## 9.2.3.11 Cross‑References

### Internal AI-OGF Controls

- 8.2.x Workflow Limits  
- 8.3.x Workflow Controls  
- 8.4.x Workflow Continuity Controls  
- 9.2.1 AI‑Dependent Recovery Paths  
- 9.2.2 AI‑Independent Fallback Paths  

### External Standards (Informative References — To Be Developed)

Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AI-OGF Annex.

---

This document is part of the AI Operational Governance Framework (AI-OGF) and is protected under the AI-OGF Limited Use License.
Official source: https://rmanthey-mantheyco.github.io/ai-ogf/
