---
layout: default
title: Plan-Foundations
---

---
layout: default
title: Plan Phase – Foundations
---

# Plan Phase – Structuring the Path to Cloud Adoption

This section captures my understanding of the Plan phase by translating strategic intent into a structured execution approach, combining foundational concepts with practical considerations drawn from real-world scenarios.

## 🧭 What the Plan Phase Really Means

If the Strategy phase defines *why* and *what*, the Plan phase defines **how the organization will approach cloud adoption in a structured and controlled manner**

This phase translates high-level intent into:
- Workload-level decisions  
- Sequenced execution  
- Defined operating model  


## 🧱 Core Pillars of the Plan Phase

Cloud planning is built on a set of interconnected pillars that translate strategy into a structured and executable adoption roadmap.

### 🔹 1. Digital Estate Understanding

Before planning migration, it is essential to understand the current landscape.

#### Key Focus Areas:
- Application inventory  
- Infrastructure footprint  
- Dependencies between systems  
- Data flows and integrations  

#### 🧠 Insight

In most enterprises, documentation is incomplete or outdated.  
Actual understanding often comes from:
- stakeholder discussions  
- operational insights  
- monitoring data  

---

### 🔹 2. Application Rationalization (6Rs)

Each application must be evaluated and mapped to a migration approach.

#### Key Focus Areas:

| Strategy | Description |
|----------|------------|
| Rehost | Lift-and-shift with minimal changes |
| Replatform | Minor optimizations, leverage PaaS where possible |
| Refactor | Modify application to be cloud-native |
| Rearchitect | Redesign application significantly |
| Rebuild | Rewrite application from scratch |
| Retain / Replace | Keep on-prem or replace with SaaS |


#### 🧠 Insight

The 6Rs are not purely technical decisions — they are influenced by:
- business value  
- cost  
- timeline  
- risk tolerance  

---

### 🔹 3. Dependency Mapping (Critical Layer)

Understanding dependencies is essential before sequencing migration.

#### Key Questions:
- What systems communicate with each other?  
- Are there latency-sensitive integrations?  
- Are there on-prem dependencies?  


#### ⚠️ Common Challenge

Applications are often migrated without fully understanding dependencies, leading to:
- broken integrations  
- performance issues  
- unexpected failures  

---

### 🔹 4. Migration Waves & Sequencing

Cloud adoption is not a one-time activity — it is executed in phases.

#### Typical Wave Approach:

| Wave | Type |
|------|------|
| Wave 1 | Low-risk, non-critical workloads |
| Wave 2 | Medium complexity applications |
| Wave 3 | Business-critical systems |

### 🧠 Insight

Migration planning is fundamentally about **risk sequencing**, not just execution.

---

### 🔹 5. Cloud Operating Model

This defines how cloud environments will be structured and managed.

#### Common Models:

| Model | Description |
|------|-------------|
| Centralized | IT controls all cloud operations |
| Shared | Platform team provides common services |
| Decentralized | Individual teams manage workloads |

---

#### 🧠 Insight

Most organizations evolve over time:

Centralized → Shared → Federated → Autonomous  

The operating model should align with organizational maturity.

---

### 🔹 6. Organizational Alignment

Planning must account for how teams will function post-adoption.

#### Key Considerations:
- Role definitions  
- Ownership boundaries  
- DevOps adoption  
- Collaboration between teams  

#### 🧠 Insight

Without organizational alignment, even well-designed architectures fail during execution.

---

### 🔹 7. Cost & Financial Planning (FinOps)

Cloud introduces a shift from CapEx to OpEx, requiring new financial controls.

#### Key Areas:
- Budgeting and forecasting  
- Cost allocation (tagging)  
- Cost optimization strategies  


#### 🧠 Insight

Cloud cost is not just a financial concern — it directly influences architecture decisions.

---

### 🔹 8. Landing Zone Planning (Bridge to Next Phase)

The Plan phase sets the requirements for the Landing Zone (Ready phase).

#### Defines:
- Number of subscriptions  
- Environment separation (Dev / Prod)  
- Networking approach (Hub-Spoke, etc.)  
- Governance requirements  

---

#### 🔗 Connection

The output of the Plan phase directly feeds into:
> **Ready Phase (Landing Zone Design and Implementation)**

---

## 🔗 Plan Phase Summary

The Plan phase transforms strategy into a structured execution roadmap.

---

### Key Outputs:

- Application inventory and classification  
- Migration strategy (6Rs)  
- Dependency mapping  
- Migration wave plan  
- Operating model definition  
- Cost and governance considerations  


### 🧠 Key Insight

> Planning is not about creating a perfect roadmap — it is about reducing uncertainty and enabling controlled execution.

---

## 🔍 Closing Thoughts

The effectiveness of cloud adoption is heavily influenced by the quality of planning. 

A well-structured Plan phase ensures that:
- migration is predictable  
- risks are minimized  
- execution is aligned with business priorities  

---
[⬅ Back to Strategy](strategy-1.md) | [Next: Ready Phase ➡](ready.md)