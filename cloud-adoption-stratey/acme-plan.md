---
layout: default
title: ACME|Plan
---

## 🔷 Phase 2: Plan (Day 30 → Day 60)

With a refined strategy in place, the focus shifted to translating direction into **application-level execution decisions**.

---

### **1. Initial Understanding (Post-Strategy State)**

At the end of Strategy, ACME Corp had:

- Identified workload categories  
- Mapped workloads to regulatory requirements  
- Defined high-level priorities  

However, this view was still:

- high-level  
- assumption-driven  
- not validated at application level  

---

### **2. What We Discovered**

As detailed assessment began, several challenges emerged:

**Application Inventory Reality**

- Initial estimate: ~250 applications  
- Actual discovery: ~420+ applications  

- Multiple undocumented services  
  *(e.g., batch jobs, reporting scripts, middleware components)*  

**Dependency Complexity**

- Core banking tightly coupled with reporting systems  
- Payment systems dependent on legacy authentication services  
- Hidden dependencies discovered during workshops  

**Compliance Tagging Gap (Critical)**

Although workloads were mapped to regulations in Strategy:

- No tagging existed at application level  
- No classification of environments based on compliance  

**Example Gap**

- A reporting system (SOX) shared infrastructure with non-critical apps  
- Payment services (PCI-DSS) exposed through shared network paths  

This created immediate design concerns for the Ready phase.

---

### 🧠 Key Insight

Strategy identified *what matters* — Plan revealed **how complex the estate actually is**

---

### **3. Decisions Made**

**Decision 1: Create Application Classification Model**

Applications were classified across multiple dimensions:

| Dimension | Example Values |
|----------|----------------|
| Business Criticality | High / Medium / Low |
| Complexity | High / Medium / Low |
| Compliance | PCI-DSS / SOX / GDPR / None |
| Deployment Type | VM / Container / PaaS |

**Decision 2: Introduce Compliance Tagging (Critical Upgrade)**

Every application was tagged with compliance requirements:

| App | Tags |
|----------|----------------|
| Payment Gateway |PCI-DSS, High Criticality  |
| Financial Reporting | SOX, Medium Criticality |
| Customer Portal | GDPR, High Criticality |
|  |  |


**Impact of Compliance Tagging**

This directly influenced:

- Network segmentation  (e.g., PCI-DSS workloads requiring isolated network zones)
- IAM controls  (e.g., SOX systems requiring tighter access governance and auditability)
- Region placement  (e.g., GDPR-tagged applications restricted to approved EU regions)
- Landing zone design  (e.g., compliance-aware environment separation and policy enforcement)

**Decision 3: Refine Migration Strategy (6Rs in Practice)**

Initial assumptions were adjusted as application-level analysis progressed:

| Application | Initial Plan | Revised Decision |
|------------|-------------|-----------------|
| Customer Portal | Replatform | Rehost *(timeline constraint)* |
| Payment System | Rehost | Retain temporarily *(PCI-DSS constraints)* |
| Reporting System | Rehost | Replatform *(cloud database optimization)* |

🧠 **Insight**

> *6Rs decisions are rarely final — they evolve with deeper discovery, technical validation, and business constraints.*

**Decision 4: Define Migration Waves (Compliance-Aware)**

Migration waves were restructured based on risk, complexity, and regulatory sensitivity:

| Wave | Type | Example Workloads |
|------|------|------------------|
| Wave 1 | Low-risk, non-regulated | Internal tools, development environments |
| Wave 2 | Medium complexity | Customer portals *(GDPR)* |
| Wave 3 | Regulated workloads | Financial reporting systems *(SOX)* |
| Wave 4 | Highly sensitive workloads | Payment processing systems *(PCI-DSS, deferred)* |

**Decision 5: Sequence Migration Based on Dependencies**

Migration sequencing was adjusted to reflect actual dependency chains:

- Authentication services prioritized before dependent applications  
- Reporting systems deferred until core banking interfaces were understood  
- Shared middleware components scheduled ahead of consuming workloads  

**Decision 6: Define Early Landing Zone Requirements**

The Plan phase now provided explicit inputs into the Ready phase:

- PCI-DSS workloads required isolated network boundaries  
- SOX systems required centralized logging, audit trails, and tighter access controls  
- GDPR workloads required region-aware deployment patterns  
- Shared services required clear separation from workload environments  

---

### **4. What Changed from Strategy Phase**

| Strategy Assumption | Plan Reality |
|-------------------|------------|
| Applications are broadly understood | Inventory expanded significantly |
| Dependencies are manageable | Hidden coupling increased planning complexity |
| Compliance is mapped conceptually | Compliance must be enforced at workload level |
| Migration approach is defined | Migration strategy requires continuous refinement |

---

### 🧠 Key Insight

Planning transformed strategy into **constraint-aware execution design**

---

### **5. Final Output of Plan Phase**

At the end of this phase, ACME Corp had:

- A significantly refined application inventory  
- A multi-dimensional classification model  
- Compliance-tagged workloads  
- Refined migration strategy (6Rs)  
- Dependency-aware migration sequencing  
- Defined migration waves  
- Explicit design inputs for the landing zone  

---

### 🔗 Transition to Ready Phase

The Plan phase made it clear that:

- Compliance requirements needed architectural enforcement  
- Network and IAM design would become central decision points  
- Governance could not be deferred  

This led into the **Ready Phase**, where the landing zone would be designed and implemented to support these constraints.

---

[⬅ Back to Series Home](index.md) | [⬅ Back to Strategy-ACME](acme-strategy.md) | [Next: Ready-ACME ➡](acme-ready.md)