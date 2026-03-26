# AI Operational Governance Framework (AI‑OGF)

The **AI Operational Governance Framework (AI‑OGF)** is a standards‑aligned framework focused on the operational realities of AI systems. While existing frameworks such as NIST AI RMF and ISO/IEC 42001 address governance, ethics, and risk, AI‑OGF fills a critical gap: **how AI behaves in production environments** and how organizations maintain safety, continuity, and accountability when AI becomes part of everyday business operations.

AI‑OGF is under active development. This repository provides visibility into the framework’s structure, progress, and planned expansion.

---

## Why I Built the AI‑OGF

In my previous role, I supported teams across multiple business units, each with different levels of technical experience and different understandings of how their work impacted the broader environment. It became clear that many people did not fully grasp the implications of the systems they were building — especially when those systems incorporated AI.

I repeatedly saw gaps in awareness around:

- Intellectual property concerns  
- Downstream and upstream impacts of automation  
- What happens when AI‑enabled workflows fail  
- How AI unavailability or incorrect outputs can cascade into real operational risk  

As I progressed through my CISM studies, these concerns became even more pronounced. Continuity planning frameworks highlighted how unprepared most organizations are for a future where AI becomes deeply embedded in business processes.

At the same time, in my personal use of web‑based generative AI, I experienced outages and slowdowns firsthand. Even as a single user, it was frustrating to be blocked by an AI service that simply wasn’t available. In automation engineering, we design for failure — we expect it, plan for it, and build fallback paths. But I wasn’t seeing that same discipline applied to AI‑driven workflows.

The more I looked, the more I saw a pattern:  
**Organizations are adopting AI faster than they are understanding the risks.**

And in many cases, companies are either unaware, complicit, or somewhere in between when it comes to **owning the outcomes of AI‑initiated actions**. We’ve already seen examples — such as the AWS Kiro incident and other cases where AI systems made elevated or unauthorized changes without human approval — that demonstrate how quickly accountability can become blurred.

After reviewing the major AI governance frameworks, I realized something important:

### **There was a gap.**  
Existing frameworks provide essential guidance on ethics, governance, and risk — but they do not address the **operational layer** where AI interacts with infrastructure, identity systems, and automated workflows.

That’s why I created the AI‑OGF.

AI‑OGF provides organizations with a structured way to understand:

- How AI interacts with systems  
- How AI decisions propagate  
- How to maintain continuity when AI becomes a dependency  
- How to define and enforce autonomy boundaries  
- How to ensure accountability for every AI‑initiated action  

AI‑OGF is not meant to replace frameworks like NIST AI RMF or ISO/IEC 42001.  
It is designed to **complement** them by providing the operational clarity those frameworks do not address.

---

## Current Status

AI‑OGF is in an active buildout phase. The following components are complete or in progress:

### ✔ Front Matter  
- Foreword (placeholder)  
- Introduction  
- Document Conventions  
- Intended Audience  
- Normative & Informative References  
- Framework Structure  
- Purpose & Scope (including accountability and continuity awareness)

### ✔ Completed Supplement Families  
- **4.x Principles**  
- **5.x Dependency Mapping**  
- **6.x Autonomy & Identity Controls**  
- **7.x Continuity & Safety Controls**  
- **8.x Workflow Layer Limits (AI‑WLL)**  
- **9.x AI‑Aware Continuity Planning**  
- **10.x AI Isolation & Air‑Gaps**  
- **11.x AI Monitoring & Drift Detection** (including Memory Drift)  
- **12.x Human Oversight & Intervention**

### ✔ Repository Structure  
- `/docs/framework` — core framework documents  
- `/docs/supplements` — detailed implementation guidance  
- `/docs/annexes` — deep technical annexes (in progress)  
- `/docs/diagrams` — visual models and architecture diagrams (in progress)  
- `/docs/governance` — contributor terms, contributors list, governance artifacts  
- `/AIOGF-road-map.md` — future buildout plans  

---

## What AI‑OGF Covers

AI‑OGF focuses on the operational dimensions of AI governance, including:

- Autonomy levels and boundaries  
- Identity‑bound authority  
- AI → infrastructure dependencies  
- AI → AI dependencies  
- AI → human dependencies  
- Workflow safety and escalation  
- Continuity and fallback behavior  
- Drift detection and monitoring  
- Isolation and air‑gap strategies  
- Human oversight and intervention  
- Accountability for AI‑initiated actions  
- Kill switch architecture and safety interlocks (Annex K)  

AI‑OGF is **not prescriptive** and does **not replace** existing governance frameworks.  
It is designed to **complement** them by providing operational clarity and implementation‑level controls.

---

## How to Adopt This Framework

Organizations can adopt AI‑OGF incrementally. A recommended approach:

### **Step 1 — Map AI Dependencies**  
Identify where AI interacts with infrastructure, identity, humans, and other AI systems.

### **Step 2 — Define Autonomy Levels**  
Assign autonomy tiers and enforce boundaries.

### **Step 3 — Implement Workflow Controls**  
Add checkpoints, override, rollback, and telemetry.

### **Step 4 — Establish Continuity Plans**  
Define AI‑dependent and AI‑independent recovery paths.

### **Step 5 — Monitor for Drift**  
Track behavioral, model, autonomy, and memory drift.

### **Step 6 — Enforce Human Oversight**  
Implement override, kill switches, and human‑validated checkpoints.

### **Step 7 — Isolate Critical AI Systems**  
Use independent hardware, robotics‑based maintenance, and isolated update channels.

### **Step 8 — Review & Iterate**  
AI‑OGF is designed for continuous improvement.

---

## AI‑OGF Maturity Model (Level 1 → Level 5)

| Level | Description |
|-------|-------------|
| **1 — Unaware** | No AI governance; AI actions are uncontrolled and unmonitored. |
| **2 — Aware** | Basic understanding of AI risks; minimal controls in place. |
| **3 — Defined** | Autonomy levels, workflow limits, and oversight mechanisms established. |
| **4 — Managed** | Drift detection, continuity planning, and isolation controls implemented. |
| **5 — Optimized** | Full operational governance with kill switches, annex‑aligned architectures, and continuous improvement. |

---

## Risk‑Based Adoption Matrix

| AI Risk Level | Required Controls | Optional Enhancements |
|---------------|------------------|------------------------|
| **Low** | Autonomy levels, basic telemetry | Behavioral drift monitoring |
| **Medium** | Workflow limits, checkpoints, override | Model drift, memory drift |
| **High** | Kill switches, isolation, fallback paths | Robotics maintenance, air‑gaps |
| **Critical** | Full AI‑OGF implementation | Annex K kill switch architecture |

---

## Developer‑Friendly Quick‑Start Guide

### **1. Identify the AI System**
- What does it do?  
- What systems does it touch?  
- What privileges does it require?

### **2. Assign an Autonomy Level**
Use the 6.x autonomy controls.

### **3. Add Workflow Controls**
- Depth limits  
- Checkpoints  
- Override  
- Rollback  
- Telemetry  

### **4. Add Drift Monitoring**
Implement the 11.x drift categories.

### **5. Add Human Oversight**
Use 12.x controls:
- Manual override  
- Kill switches  
- Human‑validated checkpoints  

### **6. Document Everything**
Use the supplement templates for consistency.

---

## Roadmap

The full roadmap is maintained in:

**[AIOGF Road‑Map](docs/AIOGF-road-map.md)**

---

## Governance

AI-OGF is developed under a structured governance model to ensure consistency, quality, and long‑term maintainability.  
All governance documents are located in:

**`/docs/governance/`**

### Governance Documents
- [Contributor Terms of Use](docs/governance/contributor-terms.md)  
- [Contributors](docs/governance/contributors.md)  
- [AIOGF Road‑Map](docs/AIOGF-road-map.md)  

### Contribution Process
AI-OGF is currently in a controlled development phase.  
Public contributions are welcome, but all submissions must:

- Follow the Contributor Terms  
- Use the approved templates  
- Maintain alignment with framework structure and terminology  
- Undergo review and approval by the framework owner  

A Pull Request Template is provided to guide contributors through the required steps.

### Recognition
Approved contributors may be acknowledged on the **Contributors** page.  
Recognition does not imply ownership of contributed material; all contributions remain governed by the AI‑OGF Limited Use License.

### Licensing
All contributions and framework materials are governed by the  
**AI‑OGF Limited Use License** (see [LICENSE.md](docs/LICENSE.md)).


---

## Contact

For contribution‑related questions or submissions, please use the link below:

[Submit an AI‑OGF Request](mailto:ai-ogf@mantheyco.com?subject=AI-OGF%20Request&body=Please%20select%20the%20type%20of%20request%20you%20are%20submitting%20and%20provide%20the%20required%20details%20below:%0A%0ARequest%20Type%20(choose%20one):%0A-%20Contribution%20Submission%0A-%20Permission%20Request%0A-%20Collaboration%20Inquiry%0A-%20General%20Question%0A%0ARequired%20Information:%0A-%20Your%20name%0A-%20Your%20organization%20(if%20applicable)%0A-%20A%20description%20of%20your%20request%20or%20intended%20use%0A-%20Whether%20the%20use%20is%20internal,%20external,%20or%20commercial%0A-%20Any%20timelines%20or%20context%20that%20may%20be%20relevant%0A%0AThank%20you%20for%20your%20submission.)

## Disclaimer

The AI‑OGF framework is provided for informational and educational purposes only. It does not constitute legal, regulatory, compliance, or professional advice. All use of this framework is at the user's own risk. No warranty of any kind is provided, and the author assumes no responsibility for any outcomes resulting from its use. Organizations remain fully responsible for their own governance, risk, compliance, and implementation decisions.

