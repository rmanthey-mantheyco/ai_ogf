---
title: 6.2.3 Autonomy Drift Detection
nav_order: 3
parent: "6.x"
---

# AIOGF‑SD‑6.2.3 — Define Permission Scope

**Document Identifier:** AIOGF‑SD‑6.2.3  
**Related Control:** 6.2.3  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.3  
**Date:** March 2, 2026  
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

## 6.2.3.1 Purpose of the Practice

The purpose of defining **permission scope** is to ensure AI systems operate under strict, enforceable boundaries that govern:

- what systems, tools, data, and identities they may access  
- what actions they may perform  
- what workflows they may influence  
- what environments they may operate in  

Permission scope enforces **least‑privilege**, prevents unauthorized access, and ensures AI systems cannot exceed their intended operational boundaries—even when autonomy or decision authority would otherwise allow action.

This practice also prevents:

- privilege inheritance in hosted‑mode AI  
- identity collapse  
- cross‑system or cross‑AI access expansion  
- unintended access to sensitive data or tools  
- silent failure modes that widen access unintentionally  

Permission scope applies across all AI deployment models, including cloud API AI, hosted‑mode AI, edge‑isolated agents, workflow‑embedded AI, and agentic orchestration layers.

---

## 6.2.3.2 Scope & Applicability

This guidance applies to any AI system capable of:

- accessing or modifying data  
- invoking tools, APIs, or system interfaces  
- using identities or credentials  
- interacting with workflows or automation engines  
- consuming compute, memory, or network resources  
- influencing downstream systems or other AI agents  

It applies across:

- cloud, on‑prem, and hybrid environments  
- human‑initiated and AI‑initiated workflows  
- agentic and autonomous remediation systems  
- identity, infrastructure, workflow, and data layers  

Stricter permission boundaries should be applied in:

- production environments  
- regulated data environments  
- environments with privileged identities  
- environments where AI can modify other AI systems  

---

## 6.2.3.3 Recommended Practice Statement

**Organizations should define and enforce explicit permission scopes that restrict AI systems to approved data, tools, identities, workflows, and resources, ensuring AI cannot access or modify anything outside its authorized domain.**

---

## 6.2.3.4 Rationale

Permission scope is required because AI systems can unintentionally:

- access sensitive systems or data  
- inherit human user privileges (hosted‑mode identity collapse)  
- chain tool calls across multiple systems  
- access workflow internals or execution paths  
- read local files, tokens, browser sessions, or SSH keys  
- exceed intended boundaries due to silent failure modes  
- act under compromised device or user identities  

Without defined permission scope, AI systems may:

- access or modify infrastructure  
- impersonate human identities  
- read sensitive or regulated data  
- influence workflows beyond intended boundaries  
- create continuity or security risks  

Hosted‑mode AI is especially vulnerable because it **cannot natively enforce permission boundaries** and inherits the user’s OS identity by default.

---

## 6.2.3.5 Implementation Guidance

The following guidance describes how organizations can implement permission scope in a repeatable, auditable, standards‑aligned manner.

---

### 6.2.3.5.1 Preconditions

Before defining permission scope, organizations should:

- define autonomy levels and decision authority  
- identify high‑risk systems, tools, and data  
- establish identity separation requirements  
- define workflow and system boundaries  
- enable logging and auditability for all access attempts  
- identify model‑specific risks (hosted‑mode, edge, agentic)  

---

### 6.2.3.5.2 Scope & Impact Analysis

For each AI system, organizations should:

1. **Classify the access type**  
   - data  
   - tools/APIs  
   - identity/credentials  
   - workflow/system interactions  
   - environmental resources  

2. **Determine the risk level**  
   - *Low:* non‑sensitive, reversible  
   - *Moderate:* shared services, internal systems  
   - *High:* privileged, production, identity, or infrastructure  

3. **Define permitted vs. prohibited access**  
   - explicitly allow only what is required  
   - explicitly deny everything else  

4. **Define compensating controls**  
   - hosted‑mode isolation  
   - edge‑agent data boundaries  
   - agentic cross‑AI restrictions  

5. **Route to the appropriate approval workflow**  
   - *Low:* automated validation  
   - *Moderate:* one reviewer  
   - *High:* two reviewers + justification  

---

### 6.2.3.5.3 Standards Alignment

Permission scope should align with:

- **Least‑privilege principles**  
  - AI should only access what is explicitly required  

- **Separation‑of‑duties requirements**  
  - AI cannot modify its own permission scope  

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
- network segmentation  
- sandboxing and containerization  
- filesystem permissions  
- resource limits  

---

### 6.2.3.5.4 Trust Relationship Evaluation

Organizations should ensure:

- AI cannot modify trust boundaries  
- cross‑tenant or cross‑account access is prohibited unless explicitly approved  
- AI cannot expand its own blast radius  
- trust‑modifying actions require multi‑party approval  

Configuration guidance:

- require explicit allow‑lists for trust relationships  
- require MFA for approving trust boundary changes  

---

### 6.2.3.5.5 Privilege Escalation Assessment

Organizations should check whether the AI system is attempting:

- direct privilege escalation (admin/root roles)  
- indirect escalation (modifying systems that grant access)  
- lateral movement  
- accessing credential stores  
- impersonating human identities  
- modifying workflow or automation permissions  

Risk‑based tailoring:

- *High‑risk:* escalate + two reviewers  
- *Moderate‑risk:* escalate + one reviewer  
- *Low‑risk:* log + automated validation  

---

### 6.2.3.5.6 Automated Validation

Organizations should use automated tools to:

- detect unauthorized data access  
- validate tool/API allow‑lists  
- detect identity or credential misuse  
- validate workflow boundaries  
- detect resource overuse or unauthorized network access  
- detect privilege escalation  
- validate environment boundaries  

Acceptable technologies include:

- policy‑as‑code engines  
- identity governance tools  
- cloud governance analyzers  
- dependency graph analyzers  
- workflow simulators  

---

### 6.2.3.5.7 Human Review Requirements

Human review should be required when:

- AI attempts to access sensitive or regulated data  
- AI attempts to use privileged tools or APIs  
- AI attempts to modify identity or access controls  
- AI attempts to modify workflow logic  
- AI attempts to access resources outside its scope  
- AI operates in hosted‑mode or edge‑isolated environments  

Operational guidance:

- reviewers must see permitted vs. prohibited scope  
- reviewers must see before/after access impact  
- reviewers must not be the requester  
- reviewers must document justification  

---

### 6.2.3.5.8 Downstream Impact Analysis

Organizations should evaluate:

- whether access affects automation or AI workflows  
- whether it impacts continuity or DR plans  
- whether it affects monitoring or logging  
- whether it could cascade across systems  
- whether it affects identity or access governance  

Usability considerations:

- provide reviewers with dependency graphs  
- highlight irreversible impacts  
- flag cross‑system impacts  

---

### 6.2.3.5.9 Documentation Requirements

Organizations should document:

- the permission scope defined  
- the AI system’s identity and access profile  
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

## 6.2.3.6 Expected Outcomes

Organizations should expect:

- AI systems operate only within approved permission boundaries  
- hosted‑mode AI is isolated through compensating controls  
- identity separation prevents privilege inheritance  
- unauthorized access attempts are detected and blocked  
- workflow and system boundaries remain intact  
- permission scope is auditable and reviewable  
- permission drift is detected early  
- AI systems cannot modify their own permissions  

---

## 6.2.3.7 Examples

### **Example 1 — Data Access Scope**  
AI may read application logs but cannot access user directories or credential stores.

### **Example 2 — Tool and API Scope**  
AI may call a monitoring API but cannot run infrastructure provisioning tools.

### **Example 3 — Identity Scope**  
AI uses a dedicated service identity and cannot access the user’s browser session or SSH keys.

### **Example 3A — Hosted‑Mode Identity Collapse**  
Claude Desktop inherits the user’s OS identity and can access browser sessions, SSH keys, cloud tokens, and local files unless isolated through a separate OS account.

### **Example 4 — Workflow Interaction Scope**  
AI may choose between predefined remediation steps but cannot modify workflow logic.

### **Example 5 — Resource Scope**  
AI may run local inference but cannot open arbitrary outbound network connections.

---

## 6.2.3.8 Notes

- Permission scope must be reviewed quarterly to detect scope creep.  
- AI systems must not modify their own permission scope.  
- Hosted‑mode and edge‑isolated agents require additional identity and resource controls.  
- Permission scope must align with autonomy level and decision authority.  
- Hosted‑mode AI cannot enforce permission scope natively; compensating controls are mandatory.  
- Organizations may define environment‑specific variations for dev, test, and prod.  

---

## 6.2.3.9 Cross‑References

### Internal AI-OGF Controls
- 6.1 Define Autonomy Levels  
- 6.2 Define Decision Authority, Permission Scope & Escalation Triggers  
- 6.2.4 Require Escalation Triggers  
- 6.3 Implementation Guidance  
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
