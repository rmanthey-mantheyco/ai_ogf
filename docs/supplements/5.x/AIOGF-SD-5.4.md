# AIOGF‑SD‑5.4 — Examples

**Document Identifier:** AIOGF‑SD‑5.4  
**Related Control:** 5.4  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.4  
**Date:** February 25, 2026  
**Status:** Working Draft  

---

## 5.4.1 Purpose of the Practice

The purpose of this document is to provide **practical, real‑world examples** that illustrate how AI dependency mapping is applied across operational environments. These examples demonstrate:

- AI‑to‑infrastructure dependencies  
- AI‑to‑AI dependencies  
- AI‑to‑human dependencies  
- human‑to‑AI dependencies  
- circular dependencies  

These examples support understanding of the requirements in **Section 5.2** and the implementation guidance in **Section 5.3**, helping organizations visualize, validate, and document their own dependency structures.

---

## 5.4.2 Scope & Applicability

This supplement applies to:

- operational workflows involving AI systems  
- infrastructure‑integrated AI  
- agentic and multi‑agent systems  
- workflow‑embedded AI  
- human‑in‑the‑loop and human‑on‑the‑loop workflows  
- environments where AI generates, modifies, or depends on infrastructure or automation  

It is relevant for:

- operators  
- governance teams  
- auditors  
- engineering teams  
- workflow designers  

Organizations may extend these examples with environment‑specific scenarios.

---

## 5.4.3 Recommended Practice Statement

**Organizations should use real‑world examples to validate, train, and refine their AI dependency mapping processes, ensuring operators and governance teams can recognize AI‑to‑AI, AI‑to‑human, and circular dependencies in practice.**

---

## 5.4.4 Rationale

Examples are required because:

- dependency chains can be complex and difficult to visualize  
- AI‑to‑AI interactions may not be obvious without concrete scenarios  
- circular dependencies often emerge unintentionally  
- operators benefit from seeing real‑world patterns  
- governance teams require reference models for audits and reviews  

Examples ensure dependency mapping is understood not only conceptually but also practically.

---

## 5.4.5 Implementation Guidance

Organizations should use examples to:

- train operators on identifying dependency types  
- validate dependency maps during quarterly reviews  
- identify hidden or circular dependencies  
- test workflow resilience and continuity  
- support onboarding for governance and engineering teams  
- create internal reference libraries of common dependency patterns  

Examples should be updated as new AI‑enabled workflows emerge.

---

### 5.4.5.1 Preconditions

Before using examples for training or validation, organizations should:

- have a defined dependency mapping methodology (Section 5.2)  
- have implementation guidance in place (Section 5.3)  
- ensure operators understand dependency categories  
- maintain current dependency maps for comparison  

---

### 5.4.5.2 Scope & Impact Analysis

Examples should be used to analyze:

- how AI systems depend on infrastructure, humans, and other AI  
- how workflow changes affect dependency chains  
- how circular dependencies form and how to resolve them  
- how AI‑generated outputs create new dependencies automatically  

---

### 5.4.5.3 Standards Alignment

Examples support alignment with:

- dependency mapping requirements  
- continuity and resilience planning  
- workflow governance  
- identity and access governance  
- audit and review processes  

---

### 5.4.5.4 Trust Relationship Evaluation

Examples should highlight:

- trust boundaries between AI systems  
- human approval paths  
- cross‑AI validation patterns  
- escalation loops and failure modes  

---

### 5.4.5.5 Privilege Escalation Assessment

Examples should help identify:

- when AI systems indirectly escalate privileges  
- when AI‑to‑AI interactions expand blast radius  
- when human approvals become dependency bottlenecks  

---

### 5.4.5.6 Automated Validation

Examples should be used to test:

- dependency graph analyzers  
- workflow simulators  
- AI‑to‑AI interaction validators  
- circular dependency detection tools  

---

### 5.4.5.7 Human Review Requirements

Examples should be used to train reviewers to:

- identify missing dependencies  
- detect circular or hidden dependencies  
- validate AI‑generated dependency maps  
- understand escalation paths  

---

### 5.4.5.8 Downstream Impact Analysis

Examples should help teams evaluate:

- how dependency changes affect continuity  
- how AI‑generated infrastructure affects dependency chains  
- how human approvals influence workflow timing  
- how AI‑to‑AI interactions propagate across systems  

---

### 5.4.5.9 Documentation Requirements

Organizations should document:

- example scenarios used for training  
- dependency patterns identified  
- lessons learned  
- updates required to dependency maps  
- environment‑specific variations  

---

## 5.4.6 Expected Outcomes

Organizations should expect:

- improved operator understanding of dependency structures  
- more accurate and complete dependency maps  
- earlier detection of circular dependencies  
- improved audit readiness  
- better continuity planning  
- clearer understanding of AI‑to‑AI and AI‑to‑human relationships  

---

## 5.4.7 Examples

### **Example 1 — AI Remediation Workflow**  
A remediation AI depends on:  
- monitoring AI for alerts  
- infrastructure APIs for corrective actions  
- human approval for high‑risk remediation steps  

Demonstrates AI‑to‑AI, AI‑to‑infrastructure, and AI‑to‑human dependencies.

---

### **Example 2 — AI Deployment Pipeline**  
An AI code generator produces infrastructure as code that is:  
- validated by a second AI  
- approved by a human reviewer  
- deployed by an automation engine  

Demonstrates multi‑layer AI‑to‑AI dependencies and human approval paths.

---

### **Example 3 — Human Approval Dependency**  
A workflow requires human approval for AI‑generated configuration changes. The dependency map documents:  
- AI‑to‑human approval  
- human‑to‑AI context injection  
- escalation paths when approval is delayed  

Demonstrates human‑to‑AI and AI‑to‑human dependencies.

---

### **Example 4 — Infrastructure Dependency**  
An AI system relies on:  
- a specific database cluster  
- a message queue  
- a monitoring endpoint  

When the database cluster is migrated, the dependency map must be updated.

---

### **Example 5 — Circular Dependency**  
A workflow stalls because:  
- AI requires human approval  
- the human requires AI‑generated context  
- the context cannot be generated until approval is granted  

Demonstrates a circular dependency requiring redesign.

---

### **Example 6 — AI‑Generated Infrastructure**  
An AI system generates Terraform code that:  
- provisions new infrastructure  
- is validated by another AI  
- becomes part of the dependency chain  

Demonstrates how AI‑generated outputs create new dependencies automatically.

---

### **Example 7 — Escalation Loop**  
AI escalates an anomaly to a human operator, but the operator:  
- relies on AI to analyze the anomaly  
- cannot proceed without AI context  

Creates a mutual escalation loop.

---

## 5.4.8 Notes

- Examples should be updated as new AI workflows are introduced.  
- Organizations may add environment‑specific examples for internal training.  
- Examples should be reviewed during quarterly dependency map validation cycles.  
- This document supports understanding of Sections 5.2 and 5.3.  

---

## 5.4.9 Cross‑References

### Internal AIOGF Controls
- 5.2 Dependency Mapping Requirements  
- 5.3 Dependency Mapping Implementation Guidance  
- 6.2.1 Define Autonomy Levels  
- 6.2.2 Define Decision Authority  
- 6.2.3 Define Permission Scope  
- 6.2.4 Require Escalation Triggers  
- 6.3 Implementation Guidance  

### External Standards (Informative References — To Be Developed)
Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AIOGF Annex.
