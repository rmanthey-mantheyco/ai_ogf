# AIOGF‑SD‑4.9 — Compensating Controls for Life‑Determinant AI

**Document Identifier:** AIOGF‑SD‑4.9  
**Related Principle:** 4.9  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.4  
**Date:** March 2026  
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

## 4.9.1 Purpose of the Practice

The purpose of this practice is to define the compensating controls required when AI systems operate in life‑determinant environments where their actions, recommendations, or automated adjustments can directly or indirectly affect human life, physical safety, or critical environmental stability.

These controls ensure AI can act at machine speed when necessary while remaining constrained by hard safety limits, independent safety systems, human authority, and enforceable autonomy boundaries. The goal is to prevent unsafe, unexpected, or out‑of‑bounds behavior while maintaining continuity in safety‑critical workflows.

---

## 4.9.2 Scope & Applicability

This practice applies to any AI system whose actions may influence:

- medical diagnosis, treatment, or dosage  
- autonomous vehicle control  
- industrial control systems (ICS/SCADA)  
- refinery, chemical, or energy operations  
- robotics and surgical systems  
- large‑scale facility operations  
- environmental stability or hazard prevention  

This practice is required whenever:

- AI must act faster than humans to prevent harm  
- AI operates within a Constrained Autonomy Envelope (CAE)  
- AI interacts with physical systems, actuators, or safety‑critical processes  
- human life or safety may be affected by AI decisions  

---

## 4.9.3 Recommended Practice Statement

Organizations **must implement compensating controls that constrain AI behavior, enforce safety boundaries, and ensure human authority remains intact** whenever AI operates in life‑determinant environments.

---

## 4.9.4 Rationale

In life‑determinant workflows, humans are often too slow to react:

- vehicles traveling at highway speeds  
- pressure valves in refineries  
- insulin pumps adjusting dosage  
- surgical robots maintaining precision  
- industrial regulators preventing catastrophic failure  

AI improves safety by reacting faster than humans — but only when constrained by:

- hard safety limits  
- independent safety controllers  
- human override  
- redundant validation  
- fail‑safe defaults  
- continuous monitoring and drift detection  

Without compensating controls, AI may exceed safe boundaries, drift into unsafe behavior, or act unpredictably in high‑risk environments.

---

## 4.9.5 Implementation Guidance

Organizations must implement a layered safety architecture combining autonomy constraints, hardware‑enforced limits, independent safety systems, human authority, and continuous monitoring. This includes:

- defining CAE boundaries during system design  
- enforcing hard safety limits at hardware or safety‑controller layers  
- requiring dual‑channel validation for high‑risk actions  
- implementing watchdog timers and redundant sensors  
- requiring human approval for actions outside the CAE  
- logging all AI actions for audit and post‑incident review  
- testing fail‑safe behavior regularly  

---

### 4.9.5.1 Preconditions

Before implementing this practice, organizations must have:

- a defined Constrained Autonomy Envelope (CAE)  
- identity‑bound authority for all AI actions  
- documented safety boundaries and operational limits  
- independent safety controllers or interlocks  
- monitoring and telemetry for safety‑critical behavior  
- escalation and override procedures  
- validated fallback and safe‑mode behavior  

---

### 4.9.5.2 Scope & Impact Analysis

For each life‑determinant AI system:

1. **Identify life‑determinant actions**  
   Any action that may affect human life, physical safety, or environmental stability.

2. **Define CAE boundaries**  
   Maximum/minimum values, rate‑of‑change limits, environmental constraints, operational boundaries.

3. **Identify hard safety limits**  
   Hardware‑enforced caps on dosage, pressure, torque, speed, temperature, electrical load.

4. **Identify independent safety controllers**  
   Interlocks, emergency stops, redundant sensors, watchdog timers, safety PLCs.

5. **Identify human‑in‑the‑loop requirements**  
   Actions requiring human approval, acknowledgment, or intervention.

6. **Identify dual‑channel validation requirements**  
   Secondary AI, rule‑based systems, redundant sensors, or human validation.

7. **Assess drift and anomaly risks**  
   Behavioral drift, model drift, autonomy drift, sensor drift.

8. **Define fail‑safe behavior**  
   Stop, alert, hand‑off, or revert to safe mode.

---

### 4.9.5.3 Standards Alignment

This practice aligns with:

- **Least autonomy** — AI autonomy is tightly constrained  
- **Human override** — humans remain the ultimate authority  
- **Isolation by design** — safety systems must be independent  
- **Fail‑safe defaults** — uncertainty triggers safe behavior  
- **Workflow layer limits** — AI cannot chain unsafe actions  
- **Constrained Autonomy Envelope (CAE)** — defines safe operating boundaries  
- **Identity‑bound authority** — high‑risk actions require accountable identities  

It also aligns with OSHA, NFPA, IEC 61508, ISO 13849, and industrial HMI safety standards.

---

### 4.9.5.4 Trust Relationship Evaluation

Evaluate:

- whether AI trusts sensor data without redundancy  
- whether AI trusts other AI systems for safety‑critical decisions  
- whether safety controllers trust AI inputs  
- whether trust relationships cross system or vendor boundaries  
- whether trust changes after model updates or retraining  

Trust must be explicit, validated, and continuously monitored.

---

### 4.9.5.5 Privilege Escalation Assessment

AI may escalate privileges unintentionally through:

- AI‑to‑AI workflow chains  
- inherited authority from orchestration layers  
- misconfigured identity systems  
- AI‑generated configuration or control signals  

Organizations must detect:

- **Direct escalation** — AI attempts unsafe actions  
- **Indirect escalation** — AI influences systems with higher authority  
- **Lateral escalation** — AI actions affect adjacent safety systems  

---

### 4.9.5.6 Automated Validation

Automated checks must verify:

- CAE boundaries are enforced  
- safety limits cannot be exceeded  
- redundant sensors agree within tolerance  
- watchdog timers are active  
- override and emergency stop systems are functional  
- drift indicators remain within safe thresholds  
- out‑of‑bounds actions trigger alerts and fallback  

---

### 4.9.5.7 Human Review Requirements

Human review is required when:

- AI requests actions outside the CAE  
- AI triggers safety boundaries  
- dual‑channel validation disagrees  
- drift indicators exceed thresholds  
- override or emergency stop is activated  
- autonomy state changes (manual → autonomous)  

Reviewers must have:

- visibility into autonomy state  
- clear autonomy indicators (visual/audible)  
- authority appropriate to the risk level  

---

### 4.9.5.8 Downstream Impact Analysis

Organizations must evaluate how compensating controls affect:

- workflow continuity  
- physical system stability  
- monitoring and observability  
- identity and access boundaries  
- AI‑to‑AI dependency chains  
- escalation and fallback behavior  

Safety controls must not create hidden continuity risks.

---

### 4.9.5.9 Documentation Requirements

Organizations must document:

- CAE boundaries and safety limits  
- independent safety controllers  
- dual‑channel validation mechanisms  
- override and emergency stop procedures  
- drift detection thresholds  
- autonomy indicators and acknowledgment requirements  
- quarterly reviews of safety controls  
- updates after model retraining or system changes  

All documentation must be retained for auditability and incident response.

---

## 4.9.6 Expected Outcomes

When implemented correctly, organizations will observe:

- AI systems acting safely within defined boundaries  
- predictable and reversible autonomous behavior  
- reduced risk of catastrophic failure  
- clear human authority and intervention capability  
- reliable detection of unsafe or unexpected behavior  
- strong continuity in life‑determinant workflows  

---

## 4.9.7 Examples

### **Example 1 — Medical AI**
AI may adjust insulin dosing within safe limits but cannot exceed dosage caps or override clinician approval.

### **Example 2 — Autonomous Vehicles**
AI may brake or steer to avoid collisions but cannot exceed speed limits or disable safety systems.

### **Example 3 — Industrial Valves**
AI may adjust flow rates but cannot exceed pressure limits enforced by mechanical interlocks.

### **Example 4 — Facility Operations**
AI may optimize HVAC or electrical load but cannot override emergency shutdown systems.

### **Example 5 — Visible Autonomy Indicators**
An AI system controlling refinery valves displays:  
- **Green:** AI active within safe limits  
- **Yellow:** Approaching boundary  
- **Red:** Boundary exceeded, human intervention required  
- **Blue:** Fallback mode  

Operators must acknowledge autonomy state before AI enters autonomous mode.

---

## 4.9.8 Notes

- AI must never be the only safety layer.  
- Compensating controls must be reviewed quarterly.  
- CAE boundaries must be updated after model retraining.  
- Independent safety systems must be tested regularly.  
- This principle applies to all workflow models.  

---

## 4.9.9 Cross‑References

### **Internal AIOGF Controls**

- **4.2 Least Autonomy** — autonomy must be minimized in life‑determinant contexts.  
- **4.3 Human Override** — override capability is mandatory.  
- **4.7 Workflow Layer Limits** — prevents unsafe workflow chaining.  
- **4.8 Constrained Autonomy Envelope (CAE)** — defines the safe operating boundary.  
- **4.10 Identity‑Bound Authority** — high‑risk actions require accountable identities.  
- **5.2.x Dependency Mapping** — AI‑to‑AI and AI‑to‑Human dependencies must respect safety boundaries.  
- **6.2.x Autonomy Boundaries** — autonomy levels must align with CAE.  
- **7.3.x Destructive Action Controls** — irreversible actions require compensating controls.  

### **External Standards (Informative References — To Be Developed)**  
OSHA, NFPA, IEC 61508, ISO 13849, ISO 42001, NIST CSF, NIST SP 800‑53.
