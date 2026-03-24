# AIOGF‑SD‑9.2.2 — AI‑Independent Fallback Paths

**Document Identifier:** AIOGF‑SD‑9.2.2  
**Related Control:** 9.2.2  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.6  
**Date:** March 24, 2026  
**Status:** Working Draft  

---

## Licensing & Usage Notice (Template v1.6)

[Same as template]

---

## 9.2.2.1 Purpose of the Practice

The purpose of this practice is to ensure that recovery remains possible even when AI systems are unavailable, degraded, or unsafe to use.  
AI‑independent fallback paths provide a human‑operable, deterministic method of restoring critical systems.

---

## 9.2.2.2 Scope & Applicability

This practice applies to:

- all critical recovery workflows  
- identity restoration  
- infrastructure provisioning  
- configuration repair  
- cross‑AI dependency breakpoints  

---

## 9.2.2.3 Recommended Practice Statement

Organizations must define and validate AI‑independent fallback paths for all critical recovery actions.

---

## 9.2.2.4 Rationale

AI systems may be:

- offline  
- corrupted  
- misconfigured  
- unable to authenticate  
- contributing to the outage  

Fallback paths ensure recovery remains possible under all conditions.

---

## Foundational Principle

Recovery must never depend solely on AI systems.

---

## 9.2.2.5 Implementation Guidance

Organizations should:

1. Identify all recovery steps requiring AI  
2. Define human‑operable alternatives  
3. Validate fallback paths regularly  
4. Ensure documentation is accessible during outages  
5. Train operators on manual recovery  

---

### 9.2.2.5.1 Preconditions

- documented recovery procedures  
- access to identity and credentials  
- offline documentation availability  

---

### 9.2.2.5.2 Scope & Impact Analysis

Evaluate:

- which systems require manual recovery  
- which dependencies must be bypassed  
- which AI systems cannot be trusted during outages  

---

### 9.2.2.5.3 Standards Alignment

Aligns with:

- continuity planning  
- disaster recovery  
- separation of duties  

---

### 9.2.2.5.4 Trust Relationship Evaluation

Evaluate:

- whether fallback paths bypass identity controls  
- whether manual recovery introduces new risks  

---

### 9.2.2.5.5 Privilege Escalation Assessment

Assess:

- whether fallback paths grant excessive privileges  

---

### 9.2.2.5.6 Automated Validation

Automated systems should:

- detect when fallback paths are required  
- validate manual recovery readiness  

---

### 9.2.2.5.7 Human Review Requirements

Human review is required for:

- fallback path approval  
- manual recovery execution  

---

### 9.2.2.5.8 Downstream Impact Analysis

Evaluate:

- impact on automation  
- impact on identity  
- impact on cross‑AI workflows  

---

### 9.2.2.5.9 Documentation Requirements

Document:

- fallback procedures  
- validation results  
- recovery outcomes  

---

## 9.2.2.6 Business Impact

Failure to define fallback paths may result in:

- unrecoverable outages  
- dependency on unavailable AI systems  
- extended downtime  

---

## 9.2.2.7 Expected Outcomes

Organizations should expect:

- predictable manual recovery  
- reduced dependency on AI  
- improved resilience  

---

## 9.2.2.8 Examples

### Example 1 — Manual Identity Restoration  
AI cannot restore identity policies.  
Fallback path uses human‑controlled identity recovery.

### Example 2 — Manual Infrastructure Provisioning  
AI‑based provisioning is offline.  
Operators provision infrastructure manually.

---

## 9.2.2.9 Alignment to External Frameworks

NIST AI RMF — Govern (partial)  
ISO/IEC 42001 — Operational Control (extension)

---

## 9.2.2.10 Notes

Fallback paths must be validated regularly.

---

## 9.2.2.11 Cross‑References

Internal AIOGF Controls:
- 9.2.1 AI‑Dependent Recovery Paths  
- 9.2.3 Circular Dependency Breakpoints  
