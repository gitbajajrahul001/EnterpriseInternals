---
layout: default
title: ACME|Strategy
---

## 🔷 Phase 1: Strategy (Day 0 → Day 30)

The engagement began with aligning on ACME Corp’s initial vision for cloud adoption.

---

### **1. Initial Understanding (Client Perspective)**

ACME Corp approached the engagement with a clear but broad objective **Migrate all workloads to cloud to improve agility and reduce cost**

#### Observations:

- No clear workload prioritization  
- No distinction between migration and modernization  
- Assumption that cloud would automatically reduce cost  

---

### **2. What We Discovered**

Through stakeholder workshops and discovery sessions, several gaps emerged:

**Business Misalignment**

- Different regions had different priorities  (e.g., Europe focused on compliance, US focused on speed to market)
- No unified definition of success  

**Application Landscape Gaps**

- No centralized inventory of applications  
- Unknown dependencies between core banking and downstream systems  
- Multiple duplicate applications across regions  

**Compliance Complexity**

Regulatory requirements varied not just by region, but also by workload type:

- Customer Data Platforms (Retail Banking Apps) (e.g., subject to GDPR in EU and data protection laws in US)
- Payment Processing Systems (e.g., PCI-DSS requirements for handling card transactions)
- Financial Reporting Systems (e.g., SOX compliance for auditability and financial controls)
- Core Banking Systems (e.g., FFIEC guidelines for operational resilience and risk management)
- Trading & Investment Platforms (e.g., SEC regulations and audit requirements for transaction traceability)

**Key Gap Identified**

- Compliance requirements were understood in isolation  
- No mapping between **applications ↔ regulatory controls**  
- No clarity on how these requirements would translate into cloud design  

**Operational Readiness**

- Teams had limited cloud experience  
- No defined operating model  
- Heavy reliance on manual processes  

---

### 🧠 Key Insight

The challenge was not migration — it was lack of clarity on **what to move, how to move, and how regulatory requirements apply to each workload**

---

### **3. Decisions Made**

Based on discovery, the strategy was refined into structured decisions:

---

**Decision 1: Not All Workloads Will Move**

- Core banking systems retained due to regulatory and stability requirements (e.g., systems governed by FFIEC guidelines with strict operational controls)
- Customer-facing applications prioritized for migration  

**Decision 2: Map Workloads to Compliance Requirements**

Instead of treating compliance generically, workloads were mapped:

| Workload Type | Key Regulation | Impact on Cloud Design |
|--------------|--------------|------------------------|
| Payment Systems | PCI-DSS | Network isolation, encryption, restricted access |
| Financial Reporting | SOX | Logging, audit trails, access controls |
| Customer Data Apps | GDPR | Data residency, encryption, access governance |
| Core Banking | FFIEC | High availability, risk controls, operational monitoring |

**Decision 3: Define Clear Business Outcomes**

- Reduce environment provisioning time from weeks to hours  
- Enable faster release cycles for digital applications  
- Improve compliance visibility across workloads  

**Decision 4: Segment Workloads**

Applications were categorized into:

- Digital (high agility, lower regulatory constraints)  
- Core banking (high stability, high regulatory constraints)  
- Regulated workloads (strict compliance-driven design)  

**Decision 5: Define Risk & Resilience Expectations**

- Payment systems → near-zero downtime  
- Reporting systems → strict auditability  
- Customer apps → high scalability with moderate recovery tolerance  

**Decision 6: Establish Operating Model Direction**

- Move toward a **shared platform model**  *(central platform team enforcing compliance + application teams owning workloads)*

---

### **4. What Changed from Initial Assumptions**

| Initial Assumption | Reality |
|------------------|--------|
| All workloads will move to cloud | Only selected workloads prioritized |
| Compliance is a separate concern | Compliance is workload-specific and design-driven |
| Cloud will reduce cost immediately | Cost optimization is long-term |
| Strategy is a one-time activity | Strategy evolves with discovery |
| Applications are well understood | Significant gaps in inventory and dependencies |

---

### 🧠 Key Insight

Strategy evolved from a broad intent into a **workload-aware, compliance-driven direction**

---

### 🔗 Output of Strategy Phase

At the end of this phase, ACME Corp had:

- Defined business outcomes  
- Identified workloads for migration vs retention  
- Mapped workloads to regulatory requirements  
- Established initial operating model direction  
- Highlighted gaps requiring further analysis  

---

### 🔍 Transition to Plan Phase

The refined strategy now needed to be translated into:
- application-level decisions  
- migration sequencing  
- dependency mapping  
- compliance-driven architecture design  

This led into the **Plan Phase**, where assumptions would be tested further and execution structured.

---

[⬅ Back to Series Home](index.md) | [⬅ Back to Acme-Problem Statement](acme-overview.md) | [Next: Plan-ACME ➡](acme-plan.md)