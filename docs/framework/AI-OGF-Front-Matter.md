# AI‑OGF — Front Matter

**Document Identifier:** AIOGF‑00‑Front‑Matter  
**Framework Version:** 0.9 (Draft)  
**Document Version:** 1.6  
**Author:** Randy Manthey  
**Last Updated:** March 2026  
**Status:** Working Draft  
© 2025–2026 Randy Manthey. All Rights Reserved.

## Table of Contents
- [1. Foreword](#1-foreword)
- [2. Introduction](#2-introduction)
  - [2.1 Document Conventions](#21-document-conventions)
  - [2.2 Intended Audience](#22-intended-audience)
  - [2.3 Normative and Informative References](#23-normative-and-informative-references)
  - [2.4 Framework Structure](#24-framework-structure)
    - [2.5 AI Deployment Models](#25-ai-deployment-models-informative)
    - [2.5.1 Local / Standalone AI](#251-local--standalone-ai)
    - [2.5.2 Cloud API / Gateway AI](#252-cloud-api--gateway-ai)
    - [2.5.3 SaaS‑Embedded AI](#253-saas-embedded-ai)
    - [2.5.4 WebUI / Hosted Application AI](#254-webui--hosted-application-ai)
    - [2.5.5 Agentic / Orchestration Layer AI](#255-agentic--orchestration-layer-ai)
    - [2.5.6 Hybrid / Distributed AI](#256-hybrid--distributed-ai)
    - [2.5.7 Embedded / Device‑Integrated AI](#257-embedded--device-integrated-ai)
    - [2.5.8 Batch / Offline AI](#258-batch--offline-ai)
- [3. Purpose and Scope](#3-purpose-and-scope)
  - [3.1 Purpose](#31-purpose)
  - [3.2 Scope](#32-scope)
    - [3.2.1 In Scope](#321-in-scope)
    - [3.2.2 Out of Scope](#322-out-of-scope)

---

## Linked Supplements

### 4.x — Principles
- [4.1 Transparency](../supplements/4.x/AIOGF-SD-4.1.md)
- [4.2 Least Autonomy](../supplements/4.x/AIOGF-SD-4.2.md)
- [4.3 Human Override](../supplements/4.x/AIOGF-SD-4.3.md)
- [4.4 Isolation by Design](../supplements/4.x/AIOGF-SD-4.4.md)
- [4.5 Dependency Awareness](../supplements/4.x/AIOGF-SD-4.5.md)
- [4.6 Fail‑Safe Defaults](../supplements/4.x/AIOGF-SD-4.6.md)
- [4.7 Workflow Layer Limits](../supplements/4.x/AIOGF-SD-4.7.md)
- [4.8 Constrained Autonomy Envelope (CAE)](../supplements/4.x/AIOGF-SD-4.8.md)
- [4.9 Compensating Controls for Life‑Determinant AI](../supplements/4.x/AIOGF-SD-4.9.md)
- [4.10 Identity‑Bound Authority](../supplements/4.x/AIOGF-SD-4.10.md)

### 5.x — Dependency Mapping
- [5.2.1 Map AI → Infrastructure](../supplements/5.x/AIOGF-SD-5.2.1.md)
- [5.2.2 Map AI → AI](../supplements/5.x/AIOGF-SD-5.2.2.md)
- [5.2.3 Map AI → Humans](../supplements/5.x/AIOGF-SD-5.2.3.md)
- [5.2.4 Map Humans → AI](../supplements/5.x/AIOGF-SD-5.2.4.md)
- [5.2.5 Circular Dependencies](../supplements/5.x/AIOGF-SD-5.2.5.md)
- [5.3 Placeholder](../supplements/5.x/AIOGF-SD-5.3.md)
- [5.4 Placeholder](../supplements/5.x/AIOGF-SD-5.4.md)

### 6.x — Autonomy & Identity Controls
- [6.2.1 Define Autonomy Levels](../supplements/6.x/AIOGF-SD-6.2.1.md)
- [6.2.2 Autonomy Boundary Enforcement](../supplements/6.x/AIOGF-SD-6.2.2.md)
- [6.2.3 Autonomy Drift Detection](../supplements/6.x/AIOGF-SD-6.2.3.md)
- [6.2.4 Autonomy Escalation Rules](../supplements/6.x/AIOGF-SD-6.2.4.md)
- [6.3 Decision Authority & Escalation](../supplements/6.x/AIOGF-SD-6.3.md)

### 7.x — Continuity and Safety Controls
- [7.2.1 Continuity Boundaries](../supplements/7.x/AIOGF-SD-7.2.1.md)
- [7.2.2 Fallback Behavior](../supplements/7.x/AIOGF-SD-7.2.2.md)
- [7.2.3 Drift Detection](../supplements/7.x/AIOGF-SD-7.2.3.md)
- [7.2.4 Monitoring and Telemetry](../supplements/7.x/AIOGF-SD-7.2.4.md)
- [7.2.5 Escalation Paths](../supplements/7.x/AIOGF-SD-7.2.5.md)
- [7.2.6 Safe Mode Behavior](../supplements/7.x/AIOGF-SD-7.2.6.md)
- [7.2.7 Destructive Action Controls](../supplements/7.x/AIOGF-SD-7.2.7.md)

### 8.x — AI Workflow Layer Limits (AI‑WLL)

- [8.1 Purpose](../supplements/8.x/AIOGF-SD-8.1.md)  
  - 8.1.1 Rationale *(contained within 8.1)*  
  - 8.1.2 Applicability *(contained within 8.1)*   
  - [8.2.1 Maximum Workflow Depth](../supplements/8.x/AIOGF-SD-8.2.1.md)  
  - [8.2.2 Mandatory Human Checkpoints](../supplements/8.x/AIOGF-SD-8.2.2.md)  
  - [8.2.3 Prohibited Recursive AI Calls](../supplements/8.x/AIOGF-SD-8.2.3.md)
  - [8.3.1 Cross‑AI Interaction Limits](../supplements/8.x/AIOGF-SD-8.3.1.md)  
  - [8.3.2 Workflow Telemetry Requirements](../supplements/8.x/AIOGF-SD-8.3.2.md)  
  - [8.3.3 Override & Rollback Requirements](../supplements/8.x/AIOGF-SD-8.3.3.md) 
  - [8.4.1 Infrastructure Deployment Example](../supplements/8.x/AIOGF-SD-8.4.1.md)  
  - [8.4.2 Remediation Example](../supplements/8.x/AIOGF-SD-8.4.2.md)  
  - [8.5.1 Exceptions](../supplements/8.x/AIOGF-SD-8.5.1.md)  
  - [8.5.2 Environment‑Specific Variations](../supplements/8.x/AIOGF-SD-8.5.2.md)


### 9.x — AI Aware Continuity Planning
- [9.1 Purpose](../supplements/9.x/AIOGF-SD-9.1.md)
- [9.2 Requirements](../supplements/9.x/AIOGF-SD-9.2.md)  
  - [9.2.1 AI Dependent Recovery Paths](../supplements/9.x/AIOGF-SD-9.2.1.md)  
  - [9.2.2 AI Independent Fallback Paths](../supplements/9.x/AIOGF-SD-9.2.2.md)  
  - [9.2.3 Circular Dependency Breakpoints](../supplements/9.x/AIOGF-SD-9.2.3.md)

### 10.x — AI Isolation and Air Gaps
- [10.1 Purpose](../supplements/10.x/AIOGF-SD-10.1.md)
- [10.2 Requirements](../supplements/10.x/AIOGF-SD-10.2.md)  
  - [10.2.1 Independent Hardware](../supplements/10.x/AIOGF-SD-10.2.1.md)  
  - [10.2.2 Robotics Based Maintenance](../supplements/10.x/AIOGF-SD-10.2.2.md)  
  - [10.2.3 Isolated Update Channels](../supplements/10.x/AIOGF-SD-10.2.3.md)

### 11.x — AI Monitoring and Drift Detection
- [11.1 Purpose](../supplements/11.x/AIOGF-SD-11.1.md)
- [11.2 Requirements](../supplements/11.x/AIOGF-SD-11.2.md)  
  - [11.2.1 Behavioral Drift](../supplements/11.x/AIOGF-SD-11.2.1.md)  
  - [11.2.2 Model Drift](../supplements/11.x/AIOGF-SD-11.2.2.md)  
  - [11.2.3 Autonomy Drift](../supplements/11.x/AIOGF-SD-11.2.3.md)
  - [11.2.4 Memory Drift](../supplements/11.x/AIOGF-SD-11.2.4.md)

### 12.x — Human Oversight and Intervention
- [12.1 Purpose](../supplements/12.x/AIOGF-SD-12.1.md)
- [12.2 Requirements](../supplements/12.x/AIOGF-SD-12.2.md)  
  - [12.2.1 Manual Override](../supplements/12.x/AIOGF-SD-12.2.1.md)  
  - [12.2.2 Kill Switches](../supplements/12.x/AIOGF-SD-12.2.2.md)  
  - [12.2.3 Human Validated Checkpoints](../supplements/12.x/AIOGF-SD-12.2.3.md)

---

## 1. Foreword
*To be completed after the framework is finalized.  
This section introduces the AI‑OGF, its origin, and its purpose in modern AI‑enabled environments.*

---

## 2. Introduction
The AI Operational Governance Framework (AI‑OGF) provides a structured, standards‑aligned approach for governing AI systems across autonomy, identity, dependency mapping, workflow safety, and operational continuity.

AI‑OGF is organized into major control families (4.x–12.x), supported by supplemental documents that provide detailed implementation guidance.

---

### 2.1 Document Conventions
The AI‑OGF uses a hierarchical numbering system aligned with ISO and NIST standards.  
“Must,” “shall,” and “required” indicate mandatory requirements.  
“Should” indicates recommended practices.  
Supplemental documents expand on specific controls and are referenced by section number.

---

### 2.2 Intended Audience
This framework is designed for:
- CISOs  
- CTOs  
- AI platform owners  
- Engineering leaders  
- Risk & compliance teams  
- Operational technology leaders  
- AI governance and safety officers  

---

### 2.3 Normative and Informative References
**Normative references** are required for compliance.  
**Informative references** provide additional context.  
(References will be added as the framework matures.)

---

### 2.4 Framework Structure
AI‑OGF is organized into the following major sections:

- **4.x Principles**  
- **5.x Dependency Mapping**  
- **6.x Autonomy & Identity Controls**  
- **7.x Continuity & Safety Controls**  
- **8.x AI Workflow Layer Limits (AI‑WLL)**  
- **9.x AI‑Aware Continuity Planning**  
- **10.x AI Isolation & Air‑Gaps**  
- **11.x AI Monitoring & Drift Detection**  
- **12.x Human Oversight & Intervention**  
- **Glossary**  
- **Index**  

---

### 2.5 AI Deployment Models (Informative)

AI systems are deployed through a variety of architectural patterns, each with distinct operational characteristics, dependency structures, and governance implications. Understanding these deployment models is essential for applying the AI Operational Governance Framework (AI‑OGF) consistently across diverse environments.

The following eight deployment models represent the most common patterns observed in enterprise, cloud, agentic, and embedded AI systems. These models are descriptive rather than prescriptive and are provided to establish a shared reference for interpreting the principles and supplements that follow.

---

#### 2.5.1 Local / Standalone AI
**Definition:**  
AI that runs entirely on a local device or isolated server, without external network dependencies.

**Examples:**  
- Desktop LLM applications  
- Local inference engines (e.g., Ollama, LM Studio)  
- Air‑gapped robotics  
- Edge‑isolated inference nodes  

**Governance relevance:**  
- Strong isolation and minimal external dependencies  
- Reduced exposure to external drift  
- Local identity and permission boundaries  
- Emphasis on fail‑safe defaults and safe‑mode behavior  

---

#### 2.5.2 Cloud API / Gateway AI
**Definition:**  
AI accessed through API calls to a cloud provider or gateway service.

**Examples:**  
- OpenAI API  
- Azure OpenAI Service  
- Anthropic Claude API  
- AWS Bedrock  

**Governance relevance:**  
- External dependency chains must be mapped  
- Identity‑bound authority and API key governance  
- Workflow depth and recursion limits  
- Monitoring for external model updates and drift  

---

#### 2.5.3 SaaS‑Embedded AI
**Definition:**  
AI capabilities embedded within SaaS platforms where the underlying model is not directly visible or controllable.

**Examples:**  
- Microsoft 365 Copilot  
- Salesforce Einstein  
- ServiceNow AI  
- Zendesk AI  

**Governance relevance:**  
- Governance focuses on *usage*, not model internals  
- Requires compensating controls for opaque systems  
- Identity and permission scoping is critical  
- Monitoring for unexpected behavior or drift  

---

#### 2.5.4 WebUI / Hosted Application AI
**Definition:**  
AI accessed through a browser‑based interface rather than an API or programmatic agent.

**Examples:**  
- ChatGPT web  
- Claude web  
- Gemini web  
- Perplexity web  

**Governance relevance:**  
- Human‑in‑the‑loop by default  
- Limited autonomy and workflow depth  
- Requires human override and checkpoint controls  
- Browser identity and session governance  

---

#### 2.5.5 Agentic / Orchestration Layer AI
**Definition:**  
AI systems capable of calling tools, APIs, or other AIs, often operating as autonomous or semi‑autonomous agents.

**Examples:**  
- MCP (Model Context Protocol) agents  
- LangChain agents  
- AutoGen  
- CrewAI  
- Function‑calling LLMs  

**Governance relevance:**  
- Highest autonomy and recursion risk  
- Requires Workflow Layer Limits (AI‑WLL)  
- Requires Constrained Autonomy Envelope (CAE)  
- Cross‑AI dependency mapping  
- Identity‑bound authority and escalation rules  

---

#### 2.5.6 Hybrid / Distributed AI
**Definition:**  
AI that spans multiple environments or layers, combining local, cloud, SaaS, or agentic components.

**Examples:**  
- Local agent + cloud API  
- Edge inference + cloud refinement  
- On‑prem LLM + SaaS orchestration  
- Multi‑AI pipelines  

**Governance relevance:**  
- Complex dependency chains  
- Multiple identity and permission domains  
- Cross‑AI interaction limits  
- Multi‑layer continuity and fallback planning  

---

#### 2.5.7 Embedded / Device‑Integrated AI
**Definition:**  
AI integrated into hardware, robotics, IoT devices, industrial equipment, or autonomous systems.

**Examples:**  
- Autonomous drones  
- Industrial robotics  
- Smart appliances  
- Automotive AI systems  

**Governance relevance:**  
- Physical‑world safety implications  
- Isolation and air‑gap requirements  
- Fail‑safe defaults and safe‑mode behavior  
- Strict continuity and override controls  

---

#### 2.5.8 Batch / Offline AI
**Definition:**  
AI used in scheduled pipelines, ETL flows, or offline inference processes where outputs are generated asynchronously.

**Examples:**  
- Batch scoring pipelines  
- ETL‑embedded AI transformations  
- Offline model evaluation  
- Scheduled inference jobs  

**Governance relevance:**  
- Transparency of inputs and outputs  
- Dependency mapping for upstream/downstream systems  
- Drift detection across batches  
- Monitoring for silent failures or degraded performance  

---

**Note:**  
A single AI system may fit more than one deployment model. These categories are intended to support consistent interpretation of AI‑OGF principles and supplements across varied architectures.

---

## 3. Purpose and Scope

### 3.1 Purpose
The purpose of the AI‑OGF is to ensure AI systems operate safely, predictably, and under human authority by defining autonomy boundaries, dependency structures, workflow limits, continuity requirements, and operational safeguards.

A core objective of the AI‑OGF is to ensure **clear accountability for all AI‑initiated actions**. The framework establishes the expectation that organizations—not AI systems, not engineers, and not vendors—retain responsibility for outcomes resulting from AI behavior. AI‑OGF provides the structure necessary for organizations to understand, assign, and maintain accountability across the full lifecycle of AI‑driven operations.

The AI‑OGF also aims to build **organizational awareness of continuity considerations** as AI becomes increasingly integrated into business processes. As AI systems replace or augment human roles, new dependencies and potential points of failure emerge. The framework highlights these risks and provides guidance to ensure continuity planning evolves alongside AI adoption, preventing operational blind spots and ensuring resilience in AI‑dependent environments.

### 3.2 Scope
The AI‑OGF applies to all AI systems that interact with infrastructure, humans, or other AI systems.  
It is designed as an operational governance framework focused on autonomy boundaries, dependency structures, workflow safety, and continuity.

**AI‑OGF is not intended to be prescriptive**, nor does it replace existing AI governance or risk frameworks such as the NIST AI RMF, ISO/IEC 42001, or other organizational, regulatory, or industry‑specific standards.

Instead, AI‑OGF is designed to **complement and integrate with** these frameworks by providing operational, implementation‑level guidance for environments where AI interacts with infrastructure, identity systems, and automated workflows.

#### 3.2.1 In Scope
- Autonomy levels and boundaries  
- Identity‑bound authority  
- Dependency mapping  
- Workflow safety  
- Continuity and fallback  
- Drift detection and monitoring  
- Isolation and air‑gap strategies  
- Human oversight and intervention  

#### 3.2.2 Out of Scope
- Ethical AI and fairness  
- HR or personnel policy  
- Legal compliance specifics  
- Data governance and privacy frameworks  
- Model training ethics or bias mitigation  
- Organizational culture or change management  
- Full‑stack AI risk management (covered by frameworks such as NIST AI RMF)


---

## Glossary
*(To be developed)*

---

## Index
*(To be developed)*

This document is part of the AI Operational Governance Framework (AI-OGF) and is protected under the AI‑OGF Limited Use License.  
Official source: https://rmanthey-mantheyco.github.io/ai-ogf/
