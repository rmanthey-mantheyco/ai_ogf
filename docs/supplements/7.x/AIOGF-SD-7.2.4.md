# AIOGF‑SD‑7.2.4 — Validate AI‑Generated Identity and Access Controls

**Document Identifier:** AIOGF‑SD‑7.2.4  
**Related Control:** 7.2.4  
**Framework:** AI Operational Governance Framework (AIOGF)  
**Author:** Randy Manthey  
**Version:** 1.3  
**Date:** March 6, 2026  
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

## 7.2.4.1 Purpose of the Practice

The purpose of this practice is to ensure that **AI‑generated identity and access control changes do not:**

- expand access beyond approved boundaries  
- violate least‑privilege or separation‑of‑duties (SoD) principles  
- introduce direct or indirect privilege‑escalation pathways  
- create new cross‑system access risks that impact continuity  

This practice supports **predictable identity behavior**, reduces blast radius, and preserves continuity when AI participates in identity administration.

---

## 7.2.4.2 Scope & Applicability

This guidance applies when AI systems:

- generate or modify identity policies (IAM policies, RBAC roles, ABAC rules)  
- propose or apply role assignments or group memberships  
- modify trust relationships (cross‑account, cross‑tenant, federation)  
- change permissions for human, service, or machine identities  
- operate in workflows that affect production, regulated, or critical environments  

It is applicable to:

- IAM teams  
- platform and cloud engineers  
- security and governance teams  
- AI platform owners and MLOps/LLMOps teams  
- any function approving or applying AI‑generated identity changes  

Stricter controls should be applied in:

- production environments  
- regulated environments  
- environments with privileged or break‑glass accounts  
- environments where AI can modify other AI or automation permissions  

---

## 7.2.4.3 Recommended Practice Statement

**Organizations should validate all AI‑generated identity and access control changes before execution** to ensure they align with least‑privilege and SoD principles, do not expand access beyond approved boundaries, and do not introduce privilege‑escalation or cross‑system access risks.

---

## 7.2.4.4 Rationale

AI‑generated identity changes can:

- unintentionally grant broader access than intended  
- create hidden privilege‑escalation paths (direct or indirect)  
- alter trust relationships in ways that bypass human review  
- enable lateral movement across systems or environments  
- impact continuity by granting AI the ability to disable safeguards  
- undermine recovery paths if AI can modify break‑glass or recovery identities  

Because AI can generate complex policies faster than humans can safely review them, **structured validation is required** to keep identity behavior predictable and aligned with governance.

---

## 7.2.4.5 Implementation Guidance

The following steps describe how organizations can implement this practice in a repeatable, auditable way.

---

### 7.2.4.5.1 Preconditions

Before allowing AI to propose or generate identity changes, organizations should:

- **Define a single source of truth for identities**  
  - IdP, HR system, directory service  
  - AI should read from, not redefine, identity sources.

- **Establish an approved role and permission catalog**  
  - Standard roles with documented permissions  
  - AI should compose from approved roles, not invent new ones.

- **Document SoD constraints and high‑risk combinations**  
  - “No user may both approve payments and modify vendor records.”  
  - “No identity may both deploy and approve production changes.”

- **Identify privileged access pathways**  
  - admin APIs, root accounts, break‑glass accounts  
  - tag these as *high‑risk*

- **Enable logging and change tracking for identity operations**  
  - all AI‑generated proposals and changes must be logged  
  - logs should include requester, approver, and before/after state

- **Define environment‑specific boundaries**  
  - “AI may not propose changes directly in production.”  
  - “AI may only propose changes in dev/test; humans promote to prod.”

---

### 7.2.4.5.2 Scope & Impact Analysis

For each AI‑generated identity change, organizations should:

1. **Classify the change type**  
   - new role or policy  
   - modification of existing role or policy  
   - new assignment (user/group/service → role)  
   - trust relationship change  
   - permission removal  

2. **Determine the risk level**  
   - *Low:* non‑privileged roles, non‑prod  
   - *Moderate:* shared services, internal apps  
   - *High:* privileged roles, prod, identity APIs, cross‑tenant access  

3. **Identify dependencies and blast radius**  
   - Does this identity control automation or other AI systems?  
   - Does it access IaC, CI/CD, or orchestration?  
   - Could this affect continuity or recovery paths?  

4. **Route to the appropriate validation workflow**  
   - *Low‑risk:* automated validation + logging  
   - *Moderate‑risk:* automated validation + one reviewer  
   - *High‑risk:* automated validation + two reviewers + explicit approval  

---

### 7.2.4.5.3 Standards Alignment

Organizations should align AI‑generated identity changes with:

- **Least‑privilege principles**  
  - grant only the minimum permissions required  
  - prefer read‑only or scoped roles  

- **Separation‑of‑duties requirements**  
  - requester ≠ approver  
  - no identity may both deploy and approve production changes  

- **Identity lifecycle policies**  
  - respect onboarding, transfer, and offboarding rules  
  - ensure temporary access has defined expiry  

- **Regulatory and compliance requirements**  
  - PCI DSS, SOX, HIPAA, GDPR  
  - ensure access to regulated data is justified and approved  

- **Environment‑specific constraints**  
  - “No direct write access to prod DBs from AI‑generated roles.”  

Acceptable methods include:

- RBAC templates and pre‑approved roles  
- ABAC for dynamic access  
- policy‑as‑code engines (OPA, Cedar, Rego)  

---

### 7.2.4.5.4 Trust Relationship Evaluation

For AI‑generated changes that affect trust relationships, organizations should:

- **Review all new or modified trust boundaries**  
  - cross‑account, cross‑tenant, cross‑cloud  
  - federation configurations  

- **Require explicit allow‑lists**  
  - no wildcard trust  
  - only specific accounts/tenants/services may be trusted  

- **Require stronger assurance for high‑risk trust relationships**  
  - MFA for establishing or modifying trust  
  - multi‑party approval for cross‑tenant or cross‑org trust  

- **Validate that AI cannot silently expand trust**  
  - AI proposals must be surfaced to humans  
  - no direct AI‑to‑trust‑policy write in production  

---

### 7.2.4.5.5 Privilege Escalation Assessment

Organizations should explicitly check AI‑generated changes for:

- **Direct privilege escalation**  
  - granting admin/root roles  
  - granting permissions to modify identity systems  

- **Indirect privilege escalation**  
  - access to systems that can grant access (CI/CD, IaC, orchestration)  
  - access to modify logging, monitoring, or approval workflows  

- **Lateral movement paths**  
  - access to systems that can pivot into other environments  
  - access to shared secrets or credentials  

- **Recursive or inherited permissions**  
  - roles inheriting from broader roles  
  - group memberships granting privileged access  

Risk‑based tailoring:

- *High‑risk:* automated analysis + two reviewers  
- *Moderate‑risk:* automated analysis + one reviewer  
- *Low‑risk:* automated analysis + logging  

---

### 7.2.4.5.6 Automated Validation

Organizations should use automated tools to:

- analyze policy structure and syntax  
- detect overly permissive access (`*` actions/resources)  
- flag “allow all” patterns  
- identify privilege‑escalation paths  
- simulate access outcomes  
- compare before/after access graphs  
- detect drift from approved models  

Acceptable technologies include:

- cloud IAM analyzers  
- policy‑as‑code engines  
- static analysis tools for IAM policies  
- graph‑based access analysis platforms  

---

### 7.2.4.5.7 Human Review Requirements

Human review should be required when:

- the change affects production or regulated environments  
- the change modifies privileged or break‑glass roles  
- the change alters trust boundaries  
- the change impacts identities used by automation or AI systems  
- the change affects access to sensitive or regulated data  

Operational guidance:

- reviewers must be trained in IAM and SoD  
- reviewers must not be the requester  
- reviewers should see:  
  - before/after access comparison  
  - risk classification  
  - automated analysis results  
  - dependency and blast‑radius information  

---

### 7.2.4.5.8 Downstream Impact Analysis

Organizations should evaluate:

- **Automation and AI dependencies**  
  - does this identity control pipelines, IaC, or other AI systems?  
  - could this allow AI to modify its own safeguards?  

- **Continuity and recovery implications**  
  - does this identity affect backup, restore, or DR workflows?  
  - could it disable or alter recovery paths?  

- **Monitoring and auditability**  
  - will this change affect logging or alerting?  
  - could it allow suppression or modification of logs?  

Usability considerations:

- provide reviewers with visual dependency graphs  
- highlight high‑impact downstream systems  

---

### 7.2.4.5.9 Documentation Requirements

For each AI‑generated identity change, organizations should record:

- the proposed change (who/what, before/after)  
- the AI system or workflow that generated it  
- automated validation results and risk classification  
- human reviewer(s), comments, and decision  
- timestamps  
- any deviations from standard process  

Configuration guidance:

- store records in a system of record  
- ensure logs are immutable or tamper‑evident  
- retain records according to regulatory requirements  

---

## 7.2.4.6 Expected Outcomes

Organizations should observe:

- AI‑generated identity changes are consistently validated  
- privilege‑escalation risks are identified early  
- identity behavior remains predictable  
- unauthorized access expansion is reduced  
- changes align with least‑privilege and SoD principles  
- audit trails support investigations and compliance  
- confidence in AI‑assisted identity operations increases  

---

## 7.2.4.7 Examples

### **Example 1 — AI‑Generated Role in Dev**  
AI proposes a new “AppSupportDev” role.  
Automated tools flag no privileged actions; risk = low.  
Single reviewer approves; change is logged.

### **Example 2 — AI Modifies Prod Admin Policy**  
AI proposes adding `DeleteInstance` to a production admin role.  
Automated analysis flags high risk and potential escalation.  
Two reviewers reject the change; a scoped alternative role is created.

### **Example 3 — New Cross‑Account Trust**  
AI proposes a trust relationship between two cloud accounts.  
Trust is limited to a specific role and specific account.  
Multi‑party approval required; federation configuration reviewed; approved with monitoring.

### **Example 4 — Identity Used by Automation**  
AI proposes expanding permissions for a CI/CD service account.  
Downstream analysis shows it can now deploy to production.  
Risk elevated; additional controls added before approval.

---

## 7.2.4.8 Cross‑References

### Internal AIOGF Controls
- 7.2.1 Restrict Destructive Actions  
- 7.2.2 Require Multi‑Party Approval  
- 7.2.3 Validate AI‑Generated Infrastructure  
- 7.2.5 Validate AI‑Generated Workflow Logic  

### External Standards (Informative References — To Be Developed)
Cross‑framework mappings to NIST CSF, NIST SP 800‑53, ISO/IEC 27001, ISO/IEC 42001, CIS Controls, and SOC 2 will be added in a future AIOGF Annex.
