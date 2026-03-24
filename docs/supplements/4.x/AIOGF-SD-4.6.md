# AIOGF‑SD‑4.6 — Fail‑Safe Defaults

**Document Identifier:** AIOGF‑SD‑4.6  
**Related Principle:** 4.6  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.4  
**Date:** March 2026  
**Status:** Working Draft  

---

## 4.6.1 Purpose of the Practice

The purpose of this practice is to ensure that AI systems default to the safest possible behavior whenever uncertainty, ambiguity, missing data, conflicting signals, or system failures occur. Fail‑safe defaults prevent AI from “guessing,” improvising, or taking unbounded actions when operating conditions fall outside expected parameters.

This principle ensures AI behavior remains predictable, reversible, and aligned with organizational intent even under degraded or unexpected conditions.

---

## 4.6.2 Scope & Applicability

This practice applies to:

- All AI systems that take actions, make decisions, or trigger workflows  
- Agentic systems, workflow‑embedded AI, hosted‑mode AI, and cloud API AI  
- Systems interacting with infrastructure, humans, or other AI systems  
- Safety‑critical, compliance‑critical, and operationally sensitive environments  
- Any system requiring escalation, fallback, or safe‑mode behavior  

Fail‑safe defaults must be defined for all autonomy levels, including supervised, constrained, and semi‑autonomous systems.

---

## 4.6.3 Recommended Practice Statement

Organizations **must ensure AI systems default to the safest possible behavior** when encountering uncertainty, missing information, conflicting data, or operational anomalies.

---

## 4.6.4 Rationale

AI systems often operate in environments where:

- data may be incomplete or inconsistent  
- sensors may fail or drift  
- upstream systems may be unavailable  
- workflows may exceed expected depth  
- dependencies may degrade or fail  
- autonomy boundaries may be approached  

Without fail‑safe defaults, AI may:

- take unsafe or irreversible actions  
- exceed intended authority  
- misinterpret ambiguous inputs  
- trigger cascading failures  
- bypass human oversight  
- drift into unpredictable behavior  

Fail‑safe defaults ensure AI behavior remains safe, bounded, and reversible under all conditions.

---

## 4.6.5 Implementation Guidance

Organizations must implement a structured, repeatable process to define, validate, and enforce fail‑safe behavior. This includes:

- defining safe fallback states  
- enforcing escalation when uncertainty is detected  
- requiring human approval for ambiguous or high‑risk actions  
- validating fallback behavior during design reviews  
- testing fail‑safe mechanisms regularly  
- integrating fail‑safe logic into workflow engines and orchestration layers  

---

### 4.6.5.1 Preconditions

Before implementing this practice, organizations must have:

- defined autonomy levels and CAE boundaries  
- dependency maps for AI → AI and AI → Humans  
- monitoring and telemetry for anomaly detection  
- escalation and override procedures  
- identity‑bound authority for all AI actions  
- a continuity model for degraded or failed states  

---

### 4.6.5.2 Scope & Impact Analysis

For each AI system:

1. **Identify uncertainty conditions**  
   Missing data, conflicting signals, low confidence, sensor drift, dependency failures.

2. **Define safe fallback behavior**  
   Stop, alert, hand‑off, revert to safe mode, or request human input.

3. **Define escalation triggers**  
   When uncertainty exceeds thresholds or boundaries are approached.

4. **Define prohibited actions**  
   Actions AI must never take under uncertainty.

5. **Define recovery behavior**  
   How AI resumes normal operation after fallback.

6. **Assess downstream impact**  
   How fail‑safe behavior affects humans, infrastructure, and other AI systems.

---

### 4.6.5.3 Standards Alignment

This practice aligns with:

- **Least Autonomy** — AI must not act beyond safe limits  
- **Human Override** — humans intervene when uncertainty occurs  
- **Isolation by Design** — fail‑safe behavior prevents cross‑system propagation  
- **Dependency Awareness** — uncertainty often arises from dependency failures  
- **Constrained Autonomy Envelope (CAE)** — uncertainty triggers CAE fallback  
- **Identity‑Bound Authority** — fallback actions must match identity permissions  

Fail‑safe defaults are foundational to safety‑critical standards such as IEC 61508 and ISO 13849.

---

### 4.6.5.4 Trust Relationship Evaluation

Evaluate:

- whether AI trusts data sources without redundancy  
- whether AI trusts other AI systems during uncertainty  
- whether trust relationships cross system or vendor boundaries  
- whether trust changes after model updates  
- whether fallback behavior depends on external systems  

Trust must be explicit, validated, and continuously monitored.

---

### 4.6.5.5 Privilege Escalation Assessment

AI may escalate privileges unintentionally during uncertainty through:

- fallback workflows that trigger privileged systems  
- AI‑to‑AI delegation  
- inherited authority from orchestration layers  
- ambiguous or missing constraints  

Organizations must detect:

- **Direct escalation** — AI attempts privileged fallback actions  
- **Indirect escalation** — AI influences systems with higher authority  
- **Lateral escalation** — AI fallback affects adjacent workflows  

---

### 4.6.5.6 Automated Validation

Automated checks must verify:

- fallback behavior activates under uncertainty  
- prohibited actions are blocked  
- escalation triggers fire correctly  
- override mechanisms are functional  
- drift indicators remain within safe thresholds  
- AI does not exceed CAE boundaries during fallback  

---

### 4.6.5.7 Human Review Requirements

Human review is required when:

- AI enters fallback or safe mode  
- uncertainty exceeds thresholds  
- AI requests human input to proceed  
- fail‑safe boundaries are modified  
- fallback behavior affects safety‑critical systems  

Reviewers must have:

- visibility into uncertainty conditions  
- clear indicators of fallback state  
- authority appropriate to the risk level  

---

### 4.6.5.8 Downstream Impact Analysis

Organizations must evaluate how fail‑safe defaults affect:

- workflow continuity  
- AI‑to‑AI dependency chains  
- human oversight and intervention  
- infrastructure stability  
- escalation and recovery behavior  

Fail‑safe behavior must not create hidden continuity risks.

---

### 4.6.5.9 Documentation Requirements

Organizations must document:

- uncertainty conditions and thresholds  
- fallback and safe‑mode behavior  
- escalation and override rules  
- prohibited actions under uncertainty  
- quarterly reviews of fail‑safe behavior  
- updates after model retraining or system changes  

All documentation must be retained for auditability and incident response.

---

## 4.6.6 Expected Outcomes

When implemented correctly, organizations will observe:

- predictable and safe AI behavior under uncertainty  
- reduced risk of unsafe or irreversible actions  
- clear escalation and override pathways  
- improved continuity and blast‑radius control  
- stronger alignment between AI behavior and human intent  
- safer AI‑to‑AI and AI‑to‑Human interactions  

---

## 4.6.7 Examples

### **Example 1 — Medical AI**
If sensor data is missing or inconsistent, AI halts dosage adjustments and alerts a clinician.

### **Example 2 — Autonomous Vehicles**
If environmental sensors disagree, AI slows the vehicle and requests human control.

### **Example 3 — Industrial Control**
If pressure readings conflict, AI stops adjustments and reverts to safe mode.

### **Example 4 — Facility Operations**
If HVAC sensors drift, AI freezes optimization and escalates to an operator.

---

## 4.6.8 Notes

- Fail‑safe behavior must be reviewed quarterly.  
- Fallback logic must be tested regularly.  
- Fail‑safe defaults are required for CAE and compensating controls.  
- AI must never “guess” under uncertainty.  

---

## 4.6.9 Cross‑References

### **Internal AIOGF Controls**

- **4.2 Least Autonomy** — fallback reduces autonomy under uncertainty.  
- **4.3 Human Override** — humans must intervene during fallback.  
- **4.5 Dependency Awareness** — uncertainty often arises from dependency failures.  
- **4.7 Workflow Layer Limits** — fallback prevents unsafe workflow chaining.  
- **4.8 Constrained Autonomy Envelope (CAE)** — uncertainty triggers CAE fallback.  
- **4.9 Compensating Controls** — fail‑safe defaults are mandatory in life‑determinant AI.  
- **4.10 Identity‑Bound Authority** — fallback actions must match identity permissions.  
- **5.2.x Dependency Mapping** — fallback behavior depends on dependency health.  
- **6.2.x Autonomy Boundaries** — fallback enforces autonomy limits.  
- **7.2.x Continuity Controls** — fallback supports continuity during failures.  

### **External Standards (Informative References — To Be Developed)**  
IEC 61508, ISO 13849, ISO 42001, NIST CSF, NIST SP 800‑53.
