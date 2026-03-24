# AIOGF‑SD‑7.2.1 — Restrict Destructive and High‑Impact Actions

**Document Identifier:** AIOGF‑SD‑7.2.1  
**Related Control:** 7.2.1  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.3  
**Date:** March 6, 2026  
**Status:** Working Draft  

---

## 7.2.1.1 Purpose of the Practice

The purpose of this practice is to prevent AI systems from initiating **destructive, irreversible, or high‑impact actions** without explicit human authorization.

Destructive actions include operations that:

- permanently delete data  
- modify or destroy infrastructure  
- disable security controls  
- disrupt continuity or recovery paths  
- alter identity or access configurations in ways that cannot be automatically reversed  

This practice ensures AI systems cannot unintentionally cause operational harm, escalate incidents, or create cascading failures.

---

## 7.2.1.2 Scope & Applicability

This guidance applies to any AI system capable of:

- executing commands against infrastructure  
- modifying or deleting data  
- altering identity or access controls  
- modifying network configurations  
- changing security controls or monitoring systems  
- triggering workflows that affect production environments  
- interacting with automation systems (CI/CD, IaC, orchestration)  

It applies across:

- cloud, on‑prem, and hybrid environments  
- production, staging, and regulated environments  
- human‑initiated and AI‑initiated workflows  
- agentic systems and autonomous remediation systems  

Stricter controls should be applied in:

- production environments  
- regulated data environments  
- environments with privileged identities  
- environments where AI can modify other AI systems  

---

## 7.2.1.3 Recommended Practice Statement

**Organizations should restrict AI systems from performing destructive or irreversible actions unless those actions are explicitly authorized by a human through a validated approval workflow.**

---

## 7.2.1.4 Rationale

AI systems can unintentionally:

- misinterpret instructions  
- hallucinate destructive commands  
- escalate remediation beyond intended scope  
- disable or modify critical infrastructure  
- delete or corrupt data  
- disable monitoring or logging  
- modify identity or access controls  
- trigger cascading failures across dependent systems  

Restricting destructive actions ensures:

- predictable operational behavior  
- reduced blast radius  
- protection of continuity and recovery paths  
- prevention of irreversible harm  
- human oversight for high‑impact decisions  

---

## 7.2.1.5 Implementation Guidance

The following steps describe how organizations can implement this practice in a repeatable, auditable, standards‑aligned manner.

---

### 7.2.1.5.1 Preconditions

Before enabling AI to interact with operational systems, organizations should:

- **Define what constitutes a destructive action**, such as:  
  - deleting data  
  - terminating instances  
  - modifying firewall rules  
  - disabling MFA  
  - altering identity policies  
  - modifying IaC templates  
  - shutting down production services  

- **Create a destructive‑action classification matrix:**  
  - *Low‑risk:* reversible, non‑production  
  - *Moderate‑risk:* reversible but impactful  
  - *High‑risk:* irreversible, privileged, or production‑impacting  

- **Tag destructive APIs and operations**, e.g.:  
  - `TerminateInstance`  
  - `DeleteBucket`  
  - `DropTable`  
  - `DisableLogging`  

- **Ensure AI cannot directly call destructive APIs**  
- **Require routing through a human‑approved workflow**  
- **Require policy‑as‑code enforcement**  
- **Enable logging and auditability**  
  - All destructive‑action requests must be logged  
  - Logs must include AI identity, requestor, and context  

---

### 7.2.1.5.2 Scope & Impact Analysis

For each AI‑generated destructive action, organizations should:

1. **Identify the action type**  
   - data deletion  
   - infrastructure termination  
   - identity modification  
   - network/security configuration change  
   - workflow cancellation or override  

2. **Determine the impact level**  
   - Does this affect production?  
   - Does this affect regulated data?  
   - Does this affect continuity or recovery?  
   - Does this affect privileged identities?  

3. **Assess reversibility**  
   - Can the action be undone automatically?  
   - Does it require manual recovery?  
   - Is recovery time acceptable?  

4. **Route to the appropriate approval workflow**  
   - *Low‑risk:* automated validation + human confirmation  
   - *Moderate‑risk:* automated validation + one reviewer  
   - *High‑risk:* automated validation + two reviewers + justification  

---

### 7.2.1.5.3 Standards Alignment

Organizations should align destructive‑action controls with:

- **Least‑privilege principles**  
  - AI should not have direct access to destructive APIs  
  - AI should only *propose* destructive actions  

- **Separation‑of‑duties requirements**  
  - AI cannot approve its own destructive actions  
  - Requestor and approver must be different identities  

- **Identity lifecycle and access governance**  
  - Only authorized humans may approve destructive actions  
  - Temporary elevated access must expire automatically  

- **Regulatory requirements**  
  - SOX, HIPAA, PCI DSS, GDPR  
  - Many require human oversight for irreversible actions  

Acceptable enforcement methods include:

- policy‑as‑code  
- RBAC/ABAC  
- workflow approval gates  
- just‑in‑time access provisioning  

---

### 7.2.1.5.4 Trust Relationship Evaluation

Organizations should ensure:

- AI cannot modify trust boundaries without human approval  
- destructive actions cannot be triggered across trust domains  
- cross‑tenant or cross‑account destructive actions require multi‑party approval  
- AI cannot escalate privileges by modifying trust relationships  

Configuration guidance:

- disable wildcard trust relationships  
- require explicit allow‑lists for destructive operations  
- require MFA for approving cross‑domain destructive actions  

---

### 7.2.1.5.5 Privilege Escalation Assessment

Organizations should check whether the destructive action:

- grants AI access to privileged APIs  
- allows AI to disable safeguards  
- enables lateral movement  
- modifies identity or access controls  
- affects systems that can grant additional access  
- impacts monitoring, logging, or approval workflows  

Risk‑based tailoring:

- *High‑risk:* two reviewers + justification  
- *Moderate‑risk:* one reviewer + automated analysis  
- *Low‑risk:* automated analysis + human confirmation  

---

### 7.2.1.5.6 Automated Validation

Organizations should use automated tools to:

- detect whether the action is destructive  
- classify the action’s risk level  
- simulate the impact  
- validate compliance with policy  
- check for privilege escalation  
- check for dependency or continuity impacts  

Acceptable technologies:

- IaC scanners  
- policy‑as‑code engines  
- cloud access analyzers  
- graph‑based dependency analyzers  
- drift detection tools  

---

### 7.2.1.5.7 Human Review Requirements

Human review should be required when:

- the action affects production  
- the action is irreversible  
- the action impacts privileged identities  
- the action modifies trust boundaries  
- the action affects continuity or recovery paths  

Operational guidance:

- reviewers must see before/after impact  
- reviewers must document justification  
- reviewers must not be the requestor  
- reviewers must confirm reversibility or recovery plan  

---

### 7.2.1.5.8 Downstream Impact Analysis

Organizations should evaluate:

- whether the destructive action affects automation or AI workflows  
- whether it impacts continuity or DR plans  
- whether it affects monitoring or logging  
- whether it could cascade across systems  
- whether it affects identity or access governance  

Usability considerations:

- provide reviewers with dependency graphs  
- highlight irreversible impacts  
- flag actions that affect multiple systems  

---

### 7.2.1.5.9 Documentation Requirements

Organizations should document:

- the destructive action requested  
- the AI system that generated it  
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

## 7.2.1.6 Expected Outcomes

Organizations should expect:

- AI cannot directly perform destructive actions  
- destructive actions require human approval  
- privilege‑escalation risks are reduced  
- continuity and recovery paths remain intact  
- destructive actions are predictable and auditable  
- operational blast radius is minimized  

---

## 7.2.1.7 Examples

### **Example 1 — AI Attempts to Delete a Storage Bucket**  
AI proposes deleting a bucket.  
Automated validation flags irreversible data loss.  
High‑risk workflow triggered.  
Two reviewers required; action rejected.

### **Example 2 — AI Proposes Terminating a Production Instance**  
AI identifies a “stuck” instance and proposes termination.  
Automated analysis shows it is part of a cluster.  
Reviewer approves termination with replacement plan.

### **Example 3 — AI Attempts to Modify Firewall Rules**  
AI proposes opening a port for troubleshooting.  
Automated validation flags security risk.  
Reviewer approves temporary rule with auto‑revert timer.

---

## 7.2.1.8 Cross‑References

### Internal AIOGF Controls
- 7.2.2 Require Multi‑Party Approval  
- 7.2.3 Validate AI‑Generated Infrastructure  
- 7.2.4 Validate AI‑Generated Identity and Access Controls  
- 7.2.5 Validate AI‑Generated Workflow Logic  

### External Standards (Informative References — To Be Developed)
Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AIOGF Annex.
