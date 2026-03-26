---
title: Supplements
nav_order: 3
---

# Supplements (4.x–12.x)

The AI-OGF supplement system provides implementation‑ready guidance for each major control family.  
Supplements expand the core requirements with:

- Detailed implementation steps  
- Domain‑specific considerations  
- Examples and applied scenarios  
- Extended controls and operational patterns  
- Notes, exceptions, and environment‑specific variations  

All supplements are located in:

docs/supplements/

Each supplement folder (4.x–12.x) contains the documents for that control family.

## Linked Supplements

### 4.x — Principles
- [4.1 Transparency](4.x/AIOGF-SD-4.1.md)
- [4.2 Least Autonomy](4.x/AIOGF-SD-4.2.md)
- [4.3 Human Override](4.x/AIOGF-SD-4.3.md)
- [4.4 Isolation by Design](4.x/AIOGF-SD-4.4.md)
- [4.5 Dependency Awareness](4.x/AIOGF-SD-4.5.md)
- [4.6 Fail‑Safe Defaults](4.x/AIOGF-SD-4.6.md)
- [4.7 Workflow Layer Limits](4.x/AIOGF-SD-4.7.md)
- [4.8 Constrained Autonomy Envelope (CAE)](4.x/AIOGF-SD-4.8.md)
- [4.9 Compensating Controls for Life‑Determinant AI](4.x/AIOGF-SD-4.9.md)
- [4.10 Identity‑Bound Authority](4.x/AIOGF-SD-4.10.md)

### 5.x — Dependency Mapping
- [5.2.1 Map AI → Infrastructure](5.x/AIOGF-SD-5.2.1.md)
- [5.2.2 Map AI → AI](5.x/AIOGF-SD-5.2.2.md)
- [5.2.3 Map AI → Humans](5.x/AIOGF-SD-5.2.3.md)
- [5.2.4 Map Humans → AI](5.x/AIOGF-SD-5.2.4.md)
- [5.2.5 Circular Dependencies](5.x/AIOGF-SD-5.2.5.md)
- [5.3 Placeholder](5.x/AIOGF-SD-5.3.md)
- [5.4 Placeholder](5.x/AIOGF-SD-5.4.md)

### 6.x — Autonomy & Identity Controls
- [6.2.1 Define Autonomy Levels](6.x/AIOGF-SD-6.2.1.md)
- [6.2.2 Autonomy Boundary Enforcement](6.x/AIOGF-SD-6.2.2.md)
- [6.2.3 Autonomy Drift Detection](6.x/AIOGF-SD-6.2.3.md)
- [6.2.4 Autonomy Escalation Rules](6.x/AIOGF-SD-6.2.4.md)
- [6.3 Decision Authority & Escalation](6.x/AIOGF-SD-6.3.md)

### 7.x — Continuity and Safety Controls
- [7.2.1 Continuity Boundaries](7.x/AIOGF-SD-7.2.1.md)
- [7.2.2 Fallback Behavior](7.x/AIOGF-SD-7.2.2.md)
- [7.2.3 Drift Detection](7.x/AIOGF-SD-7.2.3.md)
- [7.2.4 Monitoring and Telemetry](7.x/AIOGF-SD-7.2.4.md)
- [7.2.5 Escalation Paths](7.x/AIOGF-SD-7.2.5.md)
- [7.2.6 Safe Mode Behavior](7.x/AIOGF-SD-7.2.6.md)
- [7.2.7 Destructive Action Controls](7.x/AIOGF-SD-7.2.7.md)

### 8.x — AI Workflow Layer Limits (AI‑WLL)
- [8.1 Purpose](8.x/AIOGF-SD-8.1.md)
  - 8.1.1 Rationale *(contained within 8.1)*
  - 8.1.2 Applicability *(contained within 8.1)*
- [8.2.1 Maximum Workflow Depth](8.x/AIOGF-SD-8.2.1.md)
- [8.2.2 Mandatory Human Checkpoints](8.x/AIOGF-SD-8.2.2.md)
- [8.2.3 Prohibited Recursive AI Calls](8.x/AIOGF-SD-8.2.3.md)
- [8.3.1 Cross‑AI Interaction Limits](8.x/AIOGF-SD-8.3.1.md)
- [8.3.2 Workflow Telemetry Requirements](8.x/AIOGF-SD-8.3.2.md)
- [8.3.3 Override & Rollback Requirements](8.x/AIOGF-SD-8.3.3.md)
- [8.4.1 Infrastructure Deployment Example](8.x/AIOGF-SD-8.4.1.md)
- [8.4.2 Remediation Example](8.x/AIOGF-SD-8.4.2.md)
- [8.5.1 Exceptions](8.x/AIOGF-SD-8.5.1.md)
- [8.5.2 Environment‑Specific Variations](8.x/AIOGF-SD-8.5.2.md)

### 9.x — AI‑Aware Continuity Planning
- [9.1 Purpose](9.x/AIOGF-SD-9.1.md)
- [9.2 Requirements](9.x/AIOGF-SD-9.2.md)
  - [9.2.1 AI Dependent Recovery Paths](9.x/AIOGF-SD-9.2.1.md)
  - [9.2.2 AI Independent Fallback Paths](9.x/AIOGF-SD-9.2.2.md)
  - [9.2.3 Circular Dependency Breakpoints](9.x/AIOGF-SD-9.2.3.md)

### 10.x — AI Isolation and Air Gaps
- [10.1 Purpose](10.x/AIOGF-SD-10.1.md)
- [10.2 Requirements](10.x/AIOGF-SD-10.2.md)
  - [10.2.1 Independent Hardware](10.x/AIOGF-SD-10.2.1.md)
  - [10.2.2 Robotics Based Maintenance](10.x/AIOGF-SD-10.2.2.md)
  - [10.2.3 Isolated Update Channels](10.x/AIOGF-SD-10.2.3.md)

### 11.x — AI Monitoring and Drift Detection
- [11.1 Purpose](11.x/AIOGF-SD-11.1.md)
- [11.2 Requirements](11.x/AIOGF-SD-11.2.md)
  - [11.2.1 Behavioral Drift](11.x/AIOGF-SD-11.2.1.md)
  - [11.2.2 Model Drift](11.x/AIOGF-SD-11.2.2.md)
  - [11.2.3 Autonomy Drift](11.x/AIOGF-SD-11.2.3.md)
  - [11.2.4 Memory Drift](11.x/AIOGF-SD-11.2.4.md)

### 12.x — Human Oversight and Intervention
- [12.1 Purpose](12.x/AIOGF-SD-12.1.md)
- [12.2 Requirements](12.x/AIOGF-SD-12.2.md)
  - [12.2.1 Manual Override](12.x/AIOGF-SD-12.2.1.md)
  - [12.2.2 Kill Switches](12.x/AIOGF-SD-12.2.2.md)
  - [12.2.3 Human Validated Checkpoints](12.x/AIOGF-SD-12.2.3.md)
