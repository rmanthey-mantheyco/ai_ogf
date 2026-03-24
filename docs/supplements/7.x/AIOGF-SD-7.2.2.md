# AIOGF‑SD‑7.2.2 — Require Multi‑Party Approval

**Document Identifier:** AIOGF‑SD‑7.2.2  
**Related Control:** 7.2.2  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.3  
**Date:** March 6, 2026  
**Status:** Working Draft  

---

## 7.2.2.1 Purpose of the Practice

The purpose of this practice is to ensure that **high‑risk or destructive AI‑initiated actions cannot be executed without explicit approval from multiple independent human reviewers**.

Multi‑party approval (MPA) prevents:

- unilateral execution of high‑impact actions  
- privilege escalation by AI or compromised identities  
- cascading failures triggered by a single decision  
- bypassing safeguards through automation  
- insider threats or compromised accounts acting alone  

This practice ensures AI‑driven operations remain **accountable, reviewable, and aligned with organizational risk tolerance**.

---

## 7.2.2.2 Scope & Applicability

This guidance applies to any AI system capable of initiating or proposing actions that:

- affect production systems  
- modify identity or access controls  
- alter network or security configurations  
- delete or modify data  
- change infrastructure state  
- modify automation, CI/CD, or orchestration workflows  
- impact continuity or recovery paths  
- alter trust relationships  
- affect regulated or sensitive data environments  

It applies across:

- cloud, on‑prem, and hybrid environments  
- human‑initiated and AI‑initiated workflows  
- agentic systems and autonomous remediation systems  
- infrastructure, identity, security, and workflow layers  

Stricter MPA requirements should be applied in:

- production environments  
- regulated data environments  
- environments with privileged identities  
- environments where AI can modify other AI systems  

---

## 7.2.2.3 Recommended Practice Statement

**Organizations should require multi‑party approval for AI‑initiated actions that are destructive, irreversible, privileged, or have the potential to impact continuity, security, or recovery paths.**

---

## 7.2.2.4 Rationale

AI systems can unintentionally or autonomously:

- escalate privileges  
- misinterpret instructions  
- hallucinate destructive commands  
- disable safeguards  
- modify identity or access controls  
- alter infrastructure or network configurations  
- trigger cascading failures  
- bypass human oversight through automation  

Multi‑party approval ensures:

- independent verification  
- separation of duties  
- reduced blast radius  
- prevention of unilateral high‑risk actions  
- accountability and traceability  
- alignment with regulatory and governance requirements  

This practice mirrors **NIST’s longstanding requirement for dual authorization** for high‑risk operations.

---

## 7.2.2.5 Implementation Guidance

The following steps describe how organizations can implement multi‑party approval in a repeatable, auditable, standards‑aligned manner.

---

### 7.2.2.5.1 Preconditions

Before enabling multi‑party approval workflows, organizations should:

- **Define what actions require MPA**, such as:  
  - terminating production infrastructure  
  - modifying privileged roles  
  - altering trust relationships  
  - disabling MFA or logging  
  - deleting data or backups  
  - modifying firewall or network boundaries  
  - altering IaC templates used in production  
  - modifying AI system permissions  

- **Define reviewer roles and responsibilities**  
  - Reviewer 1: technical validation  
  - Reviewer 2: risk/governance validation  
  - Optional Reviewer 3: compliance or security  

- **Enforce separation of duties (SoD)**  
  - Requestor ≠ Approver  
  - AI ≠ Approver  
  - No single identity may approve all steps  

- **Enable audit logging**  
  - All approvals must be logged  
  - Logs must include identity, timestamp, justification  

- **Configure approval workflows in tooling**, such as:  
  - CI/CD  
  - IaC pipelines  
  - identity governance systems  
  - ticketing/GRC systems  

---

### 7.2.2.5.2 Scope & Impact Analysis

For each AI‑initiated action requiring approval, organizations should:

1. **Classify the action**  
   - destructive  
   - privileged  
   - irreversible  
   - cross‑system  
   - identity‑modifying  
   - continuity‑impacting  

2. **Determine the risk level**  
   - *Low:* reversible, non‑production  
   - *Moderate:* reversible but impactful  
   - *High:* irreversible, privileged, or production‑impacting  

3. **Determine the number of required approvers**  
   - *Low:* 1 approver  
   - *Moderate:* 2 approvers  
   - *High:* 2–3 approvers + justification  

4. **Identify dependencies and blast radius**  
   - Does the action affect automation?  
   - Does it affect other AI systems?  
   - Does it affect continuity or recovery?  

5. **Route to the appropriate approval workflow**  
   Automated classification → human approval → execution  

---

### 7.2.2.5.3 Standards Alignment

Organizations should align multi‑party approval with:

- **NIST SP 800‑53 (AC‑3, AC‑6, AC‑17, CM‑5)**  
  - dual authorization  
  - separation of duties  
  - privileged access restrictions  

- **NIST CSF (PR.AC, PR.PT, DE.CM)**  
  - access control  
  - protective technologies  
  - monitoring and detection  

- **ISO/IEC 27001 (A.5.18, A.8.2, A.8.3)**  
  - privileged access management  
  - information access restriction  

Acceptable methods include:

- workflow approval gates  
- policy‑as‑code enforcement  
- RBAC/ABAC restrictions  
- just‑in‑time access provisioning  
- break‑glass workflows with mandatory review  

---

### 7.2.2.5.4 Trust Relationship Evaluation

Organizations should ensure:

- cross‑account or cross‑tenant actions require MPA  
- trust boundary modifications require two or more reviewers  
- AI cannot modify trust relationships without human approval  
- wildcard trust relationships are prohibited  
- reviewers validate identity assurance levels  

Configuration guidance:

- require MFA for approving trust changes  
- require explicit allow‑lists for cross‑domain actions  

---

### 7.2.2.5.5 Privilege Escalation Assessment

Organizations should check whether the AI‑initiated action:

- grants new privileges  
- modifies privileged roles  
- affects identity governance systems  
- impacts systems that can grant access  
- disables or modifies monitoring/logging  
- enables lateral movement  

Risk‑based tailoring:

- *High‑risk:* 2–3 reviewers  
- *Moderate‑risk:* 2 reviewers  
- *Low‑risk:* 1 reviewer  

---

### 7.2.2.5.6 Automated Validation

Organizations should use automated tools to:

- classify the action’s risk level  
- detect privilege escalation  
- simulate the impact  
- validate compliance with policy  
- detect dependency or continuity impacts  
- check for destructive or irreversible outcomes  

Acceptable technologies:

- IaC scanners  
- policy‑as‑code engines  
- cloud access analyzers  
- graph‑based dependency analyzers  
- identity governance tools  

---

### 7.2.2.5.7 Human Review Requirements

Human review should be required when:

- the action affects production  
- the action is irreversible  
- the action modifies privileged identities  
- the action alters trust boundaries  
- the action impacts continuity or recovery paths  
- the action affects regulated data  

Operational guidance:

- reviewers must see before/after impact  
- reviewers must document justification  
- reviewers must not be the requestor  
- reviewers must confirm reversibility or recovery plan  

---

### 7.2.2.5.8 Downstream Impact Analysis

Organizations should evaluate:

- whether the action affects automation or AI workflows  
- whether it impacts continuity or DR plans  
- whether it affects monitoring or logging  
- whether it could cascade across systems  
- whether it affects identity or access governance  

Usability considerations:

- provide reviewers with dependency graphs  
- highlight irreversible impacts  
- flag actions that affect multiple systems  

---

### 7.2.2.5.9 Documentation Requirements

Organizations should document:

- the action requested  
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

## 7.2.2.6 Expected Outcomes

Organizations should expect:

- high‑risk actions require multiple independent approvals  
- AI cannot unilaterally execute destructive or privileged actions  
- privilege‑escalation risks are reduced  
- continuity and recovery paths remain intact  
- operational blast radius is minimized  
- audit trails support investigations and compliance  

---

## 7.2.2.7 Examples

### **Example 1 — AI Requests to Terminate a Production Cluster**  
AI proposes terminating a cluster.  
Automated validation flags high risk.  
Two reviewers required.  
Reviewers approve termination with replacement plan.

### **Example 2 — AI Attempts to Modify a Privileged Role**  
AI proposes adding permissions to a privileged role.  
Automated analysis flags privilege escalation.  
Two reviewers reject the change.

### **Example 3 — AI Requests Cross‑Tenant Trust**  
AI proposes establishing trust between two cloud tenants.  
Automated validation flags cross‑domain risk.  
Two reviewers required — one security, one platform.  
Approved with monitoring and time‑bound restrictions.

---

## 7.2.2.8 Cross‑References

### Internal AIOGF Controls
- 7.2.1 Restrict Destructive Actions  
- 7.2.3 Validate AI‑Generated Infrastructure  
- 7.2.4 Validate AI‑Generated Identity and Access Controls  
- 7.2.5 Validate AI‑Generated Workflow Logic  

### External Standards (Informative References — To Be Developed)
Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AIOGF Annex.
