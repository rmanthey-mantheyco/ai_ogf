# AIOGF‑SD‑6.2.2 — Define Decision Authority

**Document Identifier:** AIOGF‑SD‑6.2.2  
**Related Control:** 6.2.2  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.3  
**Date:** March 2, 2026  
**Status:** Working Draft  

---

## 6.2.2.1 Purpose of the Practice

The purpose of defining **decision authority** is to establish clear, enforceable boundaries for what decisions an AI system is permitted to make independently and what decisions require human approval, escalation, or contextual validation.

Decision authority ensures:

- AI systems do not exceed their intended decision‑making scope  
- high‑risk or identity‑impacting decisions require human approval  
- decision‑making aligns with organizational risk tolerance  
- autonomy levels, permission scope, and escalation triggers work together  
- decisions remain observable, auditable, and reversible  
- continuity is preserved when AI systems fail or degrade  
- hosted‑mode and edge‑isolated agents cannot act under inherited privileges  

Decision authority defines **what decisions** the AI may make, while autonomy defines **how** the AI may act.

---

## 6.2.2.2 Scope & Applicability

This guidance applies to any AI system capable of:

- making operational, analytical, or workflow decisions  
- influencing infrastructure, identity, or workflow logic  
- selecting remediation or diagnostic actions  
- initiating or approving actions  
- interacting with automation or orchestration systems  
- operating in production, regulated, or critical environments  

It applies across:

- cloud, on‑prem, and hybrid environments  
- human‑initiated and AI‑initiated workflows  
- agentic and autonomous remediation systems  
- identity, infrastructure, workflow, and data layers  

Stricter decision‑authority boundaries should be applied in:

- production environments  
- regulated data environments  
- environments with privileged identities  
- environments where AI can modify other AI systems  

---

## 6.2.2.3 Recommended Practice Statement

**Organizations should define explicit decision‑authority boundaries that specify which decisions AI systems may make independently, which require escalation, and which require human approval, ensuring AI cannot make decisions outside its authorized domain.**

---

## 6.2.2.4 Rationale

Decision authority is required because AI systems can unintentionally:

- make decisions that exceed their intended scope  
- inherit human identity and privileges (hosted‑mode identity collapse)  
- chain decisions across multiple systems (agentic orchestration)  
- influence workflow branching, retries, or escalation paths  
- make decisions without centralized oversight  
- produce incorrect or incomplete decisions due to silent failure modes  
- act under compromised device or user identities  

Without defined decision authority, AI systems may:

- approve actions without human review  
- modify workflows or infrastructure  
- escalate privileges  
- create continuity or security risks  

Decision authority ensures predictable, reviewable, and auditable decision‑making boundaries.

---

## 6.2.2.5 Implementation Guidance

The following guidance describes how organizations can implement decision authority in a repeatable, auditable, standards‑aligned manner.

---

### 6.2.2.5.1 Preconditions

Before defining decision authority, organizations should:

- define autonomy levels and permission scope  
- identify high‑risk decisions requiring mandatory human approval  
- establish authoritative sources for workflow and system state  
- ensure AI systems can pause, escalate, or transfer control  
- enable logging and auditability for all decisions  
- identify model‑specific risks (hosted‑mode, edge, agentic)  

---

### 6.2.2.5.2 Scope & Impact Analysis

For each AI system, organizations should:

1. **Classify the decision type**  
   - advisory  
   - operational  
   - scoped independent  
   - conditional  
   - independent  

2. **Determine the risk level**  
   - *Low:* reversible, non‑production  
   - *Moderate:* operational, shared services  
   - *High:* privileged, identity, infrastructure, or workflow‑impacting  

3. **Define permitted vs. prohibited decisions**  
   - explicitly allow only what is required  
   - explicitly deny high‑risk or privileged decisions  

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

### 6.2.2.5.3 Standards Alignment

Decision authority should align with:

- **Least‑privilege principles**  
  - AI should only make decisions explicitly authorized  

- **Separation‑of‑duties requirements**  
  - AI cannot approve its own decisions  
  - requestor ≠ approver  

- **Identity and infrastructure governance policies**  
  - identity boundaries  
  - environment separation  
  - workflow approval gates  

- **Regulatory requirements**  
  - SOX, HIPAA, PCI DSS, GDPR  

Acceptable enforcement methods include:

- policy‑as‑code  
- workflow approval gates  
- RBAC/ABAC restrictions  
- just‑in‑time access controls  

---

### 6.2.2.5.4 Trust Relationship Evaluation

Organizations should ensure:

- AI cannot make trust‑modifying decisions  
- cross‑tenant or cross‑account decisions require human approval  
- AI cannot expand its own blast radius  
- trust‑modifying decisions require multi‑party approval  

Configuration guidance:

- require explicit allow‑lists for trust‑related decisions  
- require MFA for approving trust boundary changes  

---

### 6.2.2.5.5 Privilege Escalation Assessment

Organizations should check whether the AI system is attempting:

- direct privilege escalation (admin/root decisions)  
- indirect escalation (decisions that modify systems granting access)  
- lateral movement  
- modifying workflow or automation permissions  
- modifying identity or access controls  
- modifying other AI systems  

Risk‑based tailoring:

- *High‑risk:* escalate + two reviewers  
- *Moderate‑risk:* escalate + one reviewer  
- *Low‑risk:* log + automated validation  

---

### 6.2.2.5.6 Automated Validation

Organizations should use automated tools to:

- detect unauthorized decision attempts  
- validate decision boundaries  
- detect recursive or cross‑AI decision chains  
- simulate decision outcomes  
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

### 6.2.2.5.7 Human Review Requirements

Human review should be required when:

- AI attempts high‑risk or privileged decisions  
- AI attempts to modify identity or access controls  
- AI attempts to modify workflow logic  
- AI attempts to modify infrastructure  
- AI attempts decisions outside its scope  
- AI operates in hosted‑mode or edge‑isolated environments  

Operational guidance:

- reviewers must see permitted vs. prohibited decisions  
- reviewers must see before/after impact  
- reviewers must not be the requester  
- reviewers must document justification  

---

### 6.2.2.5.8 Downstream Impact Analysis

Organizations should evaluate:

- whether the decision affects automation or AI workflows  
- whether it impacts continuity or DR plans  
- whether it affects monitoring or logging  
- whether it could cascade across systems  
- whether it affects identity or access governance  

Usability considerations:

- provide reviewers with dependency graphs  
- highlight irreversible impacts  
- flag cross‑system impacts  

---

### 6.2.2.5.9 Documentation Requirements

Organizations should document:

- the decision authority assigned  
- the AI system’s decision profile  
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

## 6.2.2.6 Expected Outcomes

Organizations should expect:

- AI systems make only authorized decisions  
- high‑risk decisions require human approval  
- hosted‑mode AI is isolated through compensating controls  
- unauthorized decision attempts are detected and blocked  
- workflow and system boundaries remain intact  
- decision authority is auditable and reviewable  
- decision drift is detected early  
- AI systems cannot modify their own decision authority  

---

## 6.2.2.7 Examples

### **Example 1 — Advisory Decision Authority**  
AI analyzes a configuration file and recommends changes, but a human must apply them.

### **Example 2 — Operational Decision Authority**  
AI selects which diagnostic commands to run after a human initiates a troubleshooting workflow.

### **Example 3 — Scoped Independent Decision Authority**  
AI independently restarts a failing service but cannot deploy new infrastructure.

### **Example 4 — Conditional Decision Authority**  
AI quarantines a suspicious workload but escalates before deleting or modifying it.

### **Example 5 — Independent Decision Authority**  
AI autonomously scales infrastructure based on load but cannot modify IAM or workflow logic.

---

## 6.2.2.8 Notes

- Decision authority must be reviewed quarterly to detect drift.  
- AI systems must not exceed their assigned decision authority.  
- Hosted‑mode and edge‑isolated agents require additional identity and continuity controls.  
- Decision authority must align with autonomy level, permission scope, and escalation triggers.  
- Organizations may define environment‑specific variations for dev, test, and prod.  

---

## 6.2.2.9 Cross‑References

### Internal AIOGF Controls
- 6.1 Define Autonomy Levels  
- 6.2 Define Decision Authority, Permission Scope & Escalation Triggers  
- 6.2.3 Define Permission Scope  
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
Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AIOGF Annex.
