# AIOGF‑SD‑5.3 — Implementation Guidance

**Document Identifier:** AIOGF‑SD‑5.3  
**Related Control:** 5.3  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.4  
**Date:** February 25, 2026  
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

## 5.3.1 Purpose of the Practice

The purpose of this implementation guidance is to provide **practical, repeatable methods** for applying the dependency mapping requirements defined in Section 5.2. This includes:

- documenting AI‑to‑infrastructure, AI‑to‑AI, and AI‑to‑human dependencies  
- maintaining accurate dependency maps as systems evolve  
- integrating dependency mapping into operational workflows  
- ensuring dependencies remain visible to operators and governance teams  
- reducing continuity risk by improving dependency awareness  

This guidance ensures dependency mapping becomes a **living operational practice**, not a one‑time exercise.

---

## 5.3.2 Scope & Applicability

This supplement applies to:

- all AI‑enabled workflows  
- infrastructure‑integrated AI  
- agentic and multi‑agent systems  
- workflow‑embedded AI  
- human‑in‑the‑loop and human‑on‑the‑loop workflows  
- environments where AI generates or modifies infrastructure  

It is relevant for:

- operators  
- governance teams  
- workflow designers  
- engineering teams  
- auditors  

Dependency mapping must be applied consistently across development, test, staging, and production environments.

---

## 5.3.3 Recommended Practice Statement

**Organizations should implement structured, repeatable processes to identify, document, maintain, and review AI dependencies, ensuring dependency maps remain accurate, current, and operationally useful.**

---

## 5.3.4 Rationale

Dependency mapping requires ongoing maintenance because:

- AI systems evolve rapidly  
- workflows change frequently  
- new AI‑to‑AI interactions emerge over time  
- infrastructure dependencies shift as environments scale  
- human roles and approval paths change  
- circular dependencies may appear after updates  
- AI‑generated infrastructure introduces new dependencies automatically  

Without structured implementation guidance, dependency maps become outdated and lose continuity value.

---

## 5.3.5 Implementation Guidance

The following guidance describes how organizations can operationalize dependency mapping in a consistent, auditable manner.

---

### 5.3.5.1 Preconditions

Before implementing dependency mapping, organizations should:

- define dependency categories (AI‑to‑AI, AI‑to‑human, etc.)  
- establish a standard mapping format or template  
- identify authoritative sources for workflow and system state  
- ensure dependency maps can be stored and versioned  
- train operators on how to identify and document dependencies  

---

### 5.3.5.2 Scope & Impact Analysis

Dependency mapping must include:

- AI‑to‑infrastructure dependencies  
- AI‑to‑AI dependencies  
- AI‑to‑human dependencies  
- human‑to‑AI dependencies  
- circular dependencies  
- dependencies created by AI‑generated infrastructure  

Impact analysis should evaluate:

- how dependency changes affect workflows  
- how new AI systems alter dependency chains  
- how infrastructure migrations affect AI behavior  
- how human approval paths influence continuity  

---

### 5.3.5.3 Standards Alignment

Dependency mapping should align with:

- continuity and resilience planning  
- workflow governance  
- identity and access governance  
- change management processes  
- audit and compliance requirements  

Acceptable enforcement methods include:

- version‑controlled documentation  
- workflow‑integrated mapping steps  
- automated dependency scanners  
- architecture review gates  

---

### 5.3.5.4 Trust Relationship Evaluation

Dependency maps must document:

- trust boundaries between AI systems  
- human approval paths  
- cross‑AI validation patterns  
- escalation paths and fallback mechanisms  

Trust relationships should be reviewed during:

- architecture reviews  
- workflow design sessions  
- incident postmortems  

---

### 5.3.5.5 Privilege Escalation Assessment

Dependency mapping must identify:

- when AI systems indirectly escalate privileges  
- when AI‑to‑AI interactions expand blast radius  
- when human approvals become dependency bottlenecks  
- when AI‑generated infrastructure introduces new privileged paths  

---

### 5.3.5.6 Automated Validation

Organizations should use automated tools to:

- detect new or changed dependencies  
- identify circular dependencies  
- validate workflow and system relationships  
- detect AI‑generated infrastructure changes  
- compare current state to previous versions  

Tools may include:

- dependency graph analyzers  
- workflow simulators  
- architecture scanners  
- IaC validation tools  

---

### 5.3.5.7 Human Review Requirements

Human review is required when:

- new AI systems are introduced  
- workflows are modified  
- infrastructure changes occur  
- autonomy levels or permissions change  
- new AI‑to‑AI interactions are added  
- human approval paths change  

Reviewers must:

- validate dependency accuracy  
- confirm no circular dependencies exist  
- ensure fallback paths remain intact  
- document any deviations  

---

### 5.3.5.8 Downstream Impact Analysis

Dependency mapping must evaluate:

- continuity impacts  
- workflow impacts  
- identity and access impacts  
- monitoring and logging impacts  
- AI‑to‑AI propagation effects  

This analysis should be included in:

- change requests  
- deployment reviews  
- architecture reviews  

---

### 5.3.5.9 Documentation Requirements

Organizations must document:

- all identified dependencies  
- version history of dependency maps  
- changes introduced by new workflows or AI systems  
- AI‑generated infrastructure and its dependencies  
- review results and validation notes  

Dependency maps must be:

- stored in a durable, version‑controlled repository  
- accessible to operators and governance teams  
- included in continuity planning and risk assessments  

---

## 5.3.6 Expected Outcomes

Organizations should expect:

- accurate, current dependency maps  
- improved visibility into AI‑to‑AI and AI‑to‑human relationships  
- earlier detection of circular dependencies  
- improved continuity and resilience planning  
- better audit readiness  
- consistent mapping across teams and environments  

---

## 5.3.7 Examples

### **Example 1 — AI Remediation Workflow**  
A remediation AI depends on:  
- monitoring AI for alerts  
- infrastructure APIs for actions  
- human approval for high‑risk steps  

### **Example 2 — AI Deployment Pipeline**  
An AI code generator produces IaC that is validated by another AI before deployment.

### **Example 3 — Human Approval Path**  
A workflow requires human approval for AI‑generated changes; this is documented as a human‑to‑AI dependency.

### **Example 4 — Infrastructure Dependency**  
An AI system relies on a specific database cluster; the dependency is updated after a migration.

---

## 5.3.8 Notes

- Dependency maps must be stored in a durable, version‑controlled location.  
- Maps must be updated after incidents, outages, or workflow redesigns.  
- Dependency mapping is foundational for Sections 6, 7, 8, and 9.  
- This document is a prerequisite for 5.4 Examples.  

---

## 5.3.9 Cross‑References

### Internal AIOGF Controls
- 5.2 Dependency Mapping Requirements  
- 5.4 Examples  
- 6.2.1 Define Autonomy Levels  
- 6.2.2 Define Decision Authority  
- 6.2.3 Define Permission Scope  
- 6.2.4 Require Escalation Triggers  
- 6.3 Implementation Guidance  

### External Standards (Informative References — To Be Developed)
Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AIOGF Annex.
