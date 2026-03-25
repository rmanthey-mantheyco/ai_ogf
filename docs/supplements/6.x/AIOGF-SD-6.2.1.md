---
title: 6.2.1 Define Autonomy Levels
nav_order: 1
parent: "6.x"
---

# AIOGF‑SD‑6.2.1 — Define Autonomy Levels

**Document Identifier:** AIOGF‑SD‑6.2.1  
**Related Control:** 6.2.1  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Framework Version:** 0.9 (Draft)  
**Document Version:** 1.6  
**Author:** Randy Manthey 
**Date:** March 2, 2026  
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

## 6.2.1.1 Purpose of the Practice

The purpose of defining **autonomy levels** is to establish consistent, organization‑wide boundaries for how AI systems may act. Autonomy levels classify:

- what actions an AI system may perform independently  
- what actions require human initiation  
- what actions require escalation or approval  
- how identity, permissions, and decision authority must be structured  
- how continuity and override mechanisms must function  

Autonomy levels ensure AI systems remain **controllable, observable, and interruptible** across all environments and deployment models.

---

## 6.2.1.2 Scope & Applicability

This guidance applies to any AI system capable of:

- executing or proposing operational actions  
- interacting with infrastructure, identity, or workflows  
- influencing automation or orchestration systems  
- operating in production, regulated, or critical environments  

It applies across:

- cloud, on‑prem, and hybrid environments  
- human‑initiated and AI‑initiated workflows  
- agentic systems and autonomous remediation systems  
- hosted‑mode, edge‑isolated, workflow‑embedded, and orchestration‑layer AI  

Stricter autonomy boundaries should be applied in:

- production environments  
- regulated data environments  
- environments with privileged identities  
- environments where AI can modify other AI systems  

---

## 6.2.1.3 Recommended Practice Statement

**Organizations should define explicit autonomy levels that govern what actions AI systems may perform independently, what requires human initiation, and what requires escalation, ensuring AI cannot act outside its approved operational boundaries.**

---

## 6.2.1.4 Rationale

Autonomy levels are required because AI systems can unintentionally:

- exceed intended operational scope  
- inherit human identity and privileges (hosted‑mode identity collapse)  
- chain actions across multiple systems (agentic orchestration)  
- influence workflow branching or retries  
- act without centralized monitoring  
- fail silently in edge‑isolated environments  
- create circular dependencies or cascading failures  

Without defined autonomy levels, AI systems may:

- act without human oversight  
- modify infrastructure or workflows  
- escalate privileges  
- create continuity or security risks  

Autonomy levels provide a consistent method to classify and govern AI behavior across the organization.

---

## 6.2.1.5 Implementation Guidance

The following guidance describes how organizations can implement autonomy levels in a repeatable, auditable, standards‑aligned manner.

---

### 6.2.1.5.1 Preconditions

Before defining autonomy levels, organizations should:

- define decision authority, permission scope, and escalation triggers  
- identify high‑risk actions requiring mandatory human approval  
- establish identity separation requirements  
- define workflow and system boundaries  
- enable logging and auditability for all AI actions  
- identify model‑specific risks (hosted‑mode, edge, agentic)  

---

### 6.2.1.5.2 Scope & Impact Analysis

For each AI system, organizations should:

1. **Classify the autonomy level**  
   - Level 0: No Autonomy  
   - Level 1: Assisted Autonomy  
   - Level 2: Bounded Autonomy  
   - Level 3: Conditional Autonomy  
   - Level 4: Independent Autonomy  

2. **Determine the risk level**  
   - *Low:* reversible, non‑production  
   - *Moderate:* operational, shared services  
   - *High:* privileged, identity, infrastructure, or workflow‑impacting  

3. **Define permitted vs. prohibited actions**  
   - explicitly allow only what is required  
   - explicitly deny high‑risk or privileged actions  

4. **Define escalation thresholds**  
   - risk  
   - uncertainty  
   - permission boundaries  
   - workflow boundaries  
   - continuity impacts  

5. **Route to the appropriate approval workflow**  
   - *Low:* automated validation  
   - *Moderate:* one reviewer  
   - *High:* two reviewers + justification  

---

### 6.2.1.5.3 Standards Alignment

Autonomy levels should align with:

- **Least‑privilege principles**  
  - AI should only act within explicitly defined boundaries  

- **Separation‑of‑duties requirements**  
  - AI cannot modify its own autonomy level  
  - requestor ≠ approver  

- **Identity and infrastructure governance policies**  
  - identity boundaries  
  - environment separation  
  - workflow approval gates  

- **Regulatory requirements**  
  - SOX, HIPAA, PCI DSS, GDPR  

Acceptable enforcement methods include:

- RBAC/ABAC  
- policy‑as‑code  
- API gateways  
- sandboxing and containerization  
- workflow approval gates  

---

### 6.2.1.5.4 Trust Relationship Evaluation

Organizations should ensure:

- AI cannot modify trust boundaries  
- cross‑tenant or cross‑account actions require human approval  
- AI cannot expand its own blast radius  
- trust‑modifying actions require multi‑party approval  

Configuration guidance:

- require explicit allow‑lists for trust‑related actions  
- require MFA for approving trust boundary changes  

---

### 6.2.1.5.5 Privilege Escalation Assessment

Organizations should check whether the AI system is attempting:

- direct privilege escalation  
- indirect escalation (modifying systems that grant access)  
- lateral movement  
- modifying workflow or automation permissions  
- modifying identity or access controls  
- modifying other AI systems  

Risk‑based tailoring:

- *High‑risk:* escalate + two reviewers  
- *Moderate‑risk:* escalate + one reviewer  
- *Low‑risk:* log + automated validation  

---

### 6.2.1.5.6 Automated Validation

Organizations should use automated tools to:

- detect autonomy drift  
- validate autonomy boundaries  
- detect recursive or cross‑AI action chains  
- simulate action outcomes  
- detect privilege escalation  
- validate workflow boundaries  
- check for destructive or irreversible outcomes  

Acceptable technologies include:

- policy‑as‑code engines  
- identity governance tools  
- workflow simulators  
- dependency graph analyzers  
- cloud governance analyzers  

---

### 6.2.1.5.7 Human Review Requirements

Human review should be required when:

- AI attempts actions outside its autonomy level  
- AI attempts privileged or high‑risk actions  
- AI attempts to modify identity or access controls  
- AI attempts to modify workflow logic  
- AI operates in hosted‑mode or edge‑isolated environments  

Operational guidance:

- reviewers must see permitted vs. prohibited actions  
- reviewers must see before/after impact  
- reviewers must not be the requester  
- reviewers must document justification  

---

### 6.2.1.5.8 Downstream Impact Analysis

Organizations should evaluate:

- whether autonomy affects automation or AI workflows  
- whether it impacts continuity or DR plans  
- whether it affects monitoring or logging  
- whether it could cascade across systems  
- whether it affects identity or access governance  

Usability considerations:

- provide reviewers with dependency graphs  
- highlight irreversible impacts  
- flag cross‑system impacts  

---

### 6.2.1.5.9 Documentation Requirements

Organizations should document:

- the autonomy level assigned  
- the AI system’s operational boundaries  
- automated validation results  
- risk classification  
- reviewer identities and decisions  
- timestamps  
- justification for approval or rejection  
- deviations from standard process  

Configuration guidance:

- store documentation in a system of record  
- ensure logs are immutable  
- retain records per regulatory requirements  

---

## 6.2.1.6 Expected Outcomes

Organizations should expect:

- AI systems operate only within approved autonomy boundaries  
- autonomy drift is detected early  
- hosted‑mode AI is isolated through compensating controls  
- unauthorized actions are detected and blocked  
- workflow and system boundaries remain intact  
- autonomy levels are auditable and reviewable  
- AI systems cannot modify their own autonomy level  

---

## 6.2.1.7 Examples

### **Example 1 — Level 0 (No Autonomy)**  
AI provides a risk assessment report, but a human must manually apply any changes.

### **Example 2 — Level 1 (Assisted Autonomy)**  
A human requests “restart service,” and the AI executes the restart but cannot initiate it independently.

### **Example 3 — Level 2 (Bounded Autonomy)**  
AI may restart services or rotate logs but cannot deploy infrastructure.

### **Example 4 — Level 3 (Conditional Autonomy)**  
AI remediates incidents automatically but escalates before modifying infrastructure.

### **Example 5 — Level 4 (Independent Autonomy)**  
AI autonomously scales infrastructure but cannot modify IAM policies.

---

## 6.2.1.8 Notes

- Autonomy levels must be reviewed quarterly to detect drift.  
- AI systems must not exceed their assigned autonomy level.  
- Hosted‑mode and edge‑isolated agents require additional identity and continuity controls.  
- Autonomy levels must align with decision authority, permission scope, and escalation triggers.  
- Organizations may define environment‑specific variations for dev, test, and prod.  

---

## 6.2.1.9 Cross‑References

### Internal AIOGF Controls
- 6.2.2 Define Decision Authority  
- 6.2.3 Define Permission Scope  
- 6.2.4 Require Escalation Triggers  
- 6.3 Implementation Guidance  

### External Standards (Informative References — To Be Developed)
Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AIOGF Annex.


---

This document is part of the AI Operational Governance Framework (AIOGF) and is protected under the AI-OGF Limited Use License.
Official source: https://rmanthey-mantheyco.github.io/ai-ogf/
