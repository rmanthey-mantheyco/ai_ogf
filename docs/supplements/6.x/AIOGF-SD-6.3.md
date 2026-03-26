---
title: 6.3 Decision Authority & Escalation
nav_order: 5
parent: "6.x"
---

# AIOGF‑SD‑6.3 — Implementation Guidance

**Document Identifier:** AIOGF‑SD‑6.3  
**Related Control:** 6.3  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.3  
**Date:** March 6, 2026  
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

## 6.3.1 Purpose

The purpose of this implementation guidance is to:

- provide practical steps for enforcing autonomy, decision authority, permission scope, and escalation triggers  
- ensure AI systems operate within approved boundaries  
- prevent autonomy drift and privilege escalation  
- ensure identity separation and prevent hosted‑mode identity collapse  
- support continuity by ensuring AI systems can fail safely  
- provide operators with clear governance patterns  
- ensure consistent implementation across environments  
- support audits, reviews, and dependency mapping  

This guidance ensures the requirements in **Section 6.2** are applied consistently and effectively across all AI deployment models, including:

- cloud API AI  
- hosted‑mode AI  
- edge‑isolated agents  
- workflow‑embedded AI  
- agentic orchestration layers  

---

## 6.3.2 Rationale

Implementation guidance is required because:

- autonomy levels alone do not guarantee safe operation  
- hosted‑mode AI cannot enforce permission boundaries without compensating controls  
- edge‑isolated agents require continuity safeguards  
- agentic orchestration layers can create recursive or cross‑AI actions  
- workflow‑embedded AI shares a failure domain with automation engines  
- identity collapse and privilege inheritance must be mitigated  
- escalation triggers must be operationalized, not theoretical  
- organizations require repeatable, auditable implementation patterns  

Without structured implementation guidance, autonomy controls may be inconsistently applied or bypassed entirely.

---

## 6.3.3 Implementation Guidance

The following guidance supports the safe and consistent implementation of autonomy controls.

---

### 6.3.3.1 Use Autonomy Matrices

Organizations must document autonomy levels, decision authority, permission scope, and escalation triggers in a unified **autonomy matrix**.

The autonomy matrix must include:

- assigned autonomy level  
- permitted decisions  
- prohibited decisions  
- approved tools and APIs  
- identity and credential boundaries  
- escalation triggers  
- continuity requirements  
- model‑specific deviations (hosted‑mode, edge, agentic, workflow‑embedded)  

**Hosted‑Mode Consideration:**  
Autonomy matrices must explicitly document compensating controls for hosted‑mode AI, including:

- separate OS users  
- sandboxed directories  
- isolated browser profiles  

---

### 6.3.3.2 Require Human‑in‑the‑Loop for High‑Risk Actions

High‑risk actions must always require human approval, regardless of autonomy level.

High‑risk actions include:

- modifying infrastructure  
- altering identity or access controls  
- changing workflow logic  
- deleting or quarantining workloads  
- modifying dependencies  
- altering continuity or failover paths  

**Hosted‑Mode Consideration:**  
Because hosted‑mode AI inherits user privileges, human‑in‑the‑loop controls must be enforced externally (workflow gates, approval systems, IAM policies).

---

### 6.3.3.3 Enforce Identity Separation

AI systems must use **dedicated service identities** whenever possible.

Identity separation must include:

- separate OS user accounts  
- separate browser profiles  
- separate credential stores  
- scoped API tokens  
- temporary session credentials  

**Hosted‑Mode Consideration (Critical):**  
Hosted‑mode AI cannot enforce identity separation natively.  
Organizations must create a dedicated OS user and isolate:

- credentials  
- files  
- browser sessions  

---

### 6.3.3.4 Implement Permission Boundaries Through Technical Controls

Permission scope must be enforced through:

- IAM policies  
- API gateways  
- network segmentation  
- sandboxing  
- containerization  
- filesystem permissions  
- resource limits  

**Hosted‑Mode Consideration:**  
Local agents require OS‑level sandboxing, restricted PATH, and removal of sensitive CLI tools.

---

### 6.3.3.5 Implement Escalation Triggers in Workflow Engines

Escalation triggers must be embedded into:

- workflow engines  
- orchestration layers  
- automation pipelines  
- monitoring systems  

Escalation triggers must include:

- risk thresholds  
- uncertainty thresholds  
- permission boundary checks  
- workflow boundary checks  
- continuity impact checks  

**Hosted‑Mode Consideration:**  
Hosted‑mode AI must escalate before performing any action that uses inherited privileges.

---

### 6.3.3.6 Monitor for Autonomy Drift

Organizations must implement monitoring to detect:

- expanded tool access  
- expanded data access  
- expanded decision authority  
- expanded workflow influence  
- recursive or cross‑AI actions  
- silent failure modes  

**Hosted‑Mode Consideration:**  
Local agents require additional monitoring because they lack centralized observability.

---

### 6.3.3.7 Validate Continuity Requirements

AI systems must include:

- fail‑safe defaults  
- rollback paths  
- human override mechanisms  
- independent health checks  
- dependency mapping updates  

**Edge‑Isolated Consideration:**  
Edge agents must include cloud‑based continuity anchors to prevent workflow loss if the device fails.

---

### 6.3.3.8 Document Model‑Specific Deviations

Every AI system must document deviations from standard autonomy behavior, including:

- hosted‑mode identity collapse  
- edge‑isolated continuity gaps  
- workflow‑embedded shared failure domains  
- agentic cross‑AI interactions  

These deviations must be reviewed **quarterly**.

---

## 6.3.4 Examples

### **Example 1 — Autonomy Matrix Implementation**  
An organization creates a matrix defining autonomy level, decision authority, permission scope, and escalation triggers for each AI system, including hosted‑mode compensating controls.

### **Example 2 — Human‑in‑the‑Loop Enforcement**  
AI proposes a configuration change, but the workflow engine requires human approval before applying it.

### **Example 3 — Identity Separation for Hosted‑Mode AI**  
Claude Desktop is run under a dedicated OS user with isolated directories and no access to browser sessions or SSH keys.

### **Example 4 — Permission Boundary Enforcement**  
AI attempts to access a restricted API and is blocked by IAM policies, triggering escalation.

### **Example 5 — Escalation Trigger in Workflow Engine**  
AI detects an anomaly but escalates because confidence is below the required threshold.

### **Example 6 — Continuity Safeguard for Edge Agents**  
An edge‑isolated AI agent stores workflow state in a cloud anchor to prevent loss during device failure.

---

## 6.3.5 Expected Outcomes

Organizations should expect:

- autonomy levels are consistently implemented across environments  
- AI systems operate only within approved decision and permission boundaries  
- hosted‑mode AI is isolated through compensating controls  
- escalation triggers reliably prevent unsafe or high‑risk actions  
- identity separation prevents privilege inheritance and identity collapse  
- continuity safeguards ensure AI systems fail safely  
- autonomy drift is detected early through monitoring and validation  
- implementation patterns are repeatable, auditable, and aligned with Section 6.2  

---

## 6.3.6 Notes

- Implementation guidance must be reviewed quarterly to ensure alignment with evolving AI architectures.  
- Hosted‑mode AI requires compensating controls due to identity collapse and lack of permission enforcement.  
- Implementation guidance must align with autonomy levels, decision authority, permission scope, and escalation triggers.  
- Organizations may define environment‑specific implementation patterns for dev, test, and prod.  
- Implementation guidance must be updated as new AI deployment models emerge.  

---

## 6.3.7 Cross‑References

### Internal AI-OGF Controls
- 6.1 Define Autonomy Levels  
- 6.2 Define Decision Authority, Permission Scope & Escalation Triggers  
- 7.2.1 Restrict Destructive Actions  
- 7.2.2 Require Multi‑Party Approval  
- 7.2.3 Validate AI‑Generated Infrastructure  
- 7.2.4 Validate AI‑Generated Identity and Access Controls  
- 7.2.5 Validate AI‑Generated Workflow Logic  
- 7.2.6 Define AI Blast‑Radius Boundaries  
- 7.2.7 Require Independent Health Checks & Fail‑Safe Defaults  

### External Standards (Informative References — To Be Developed)
Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AI-OGF Annex.

---

This document is part of the AI Operational Governance Framework (AI-OGF) and is protected under the AI-OGF Limited Use License.
Official source: https://rmanthey-mantheyco.github.io/ai-ogf/
