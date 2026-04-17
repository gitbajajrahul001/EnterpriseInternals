---
layout: default
title: ACME|Ready
---

## 🔷 Phase 3: Ready (Day 60 → Day 90)

With a detailed plan in place, the focus shifted to building the **cloud foundation (Landing Zone)** that could support ACME Corp’s application landscape, compliance requirements, and operating model.

---

### **1. Initial Understanding (From Plan Phase)**

At the end of the Plan phase, the following assumptions were made:

- Compliance requirements would be enforced via architecture  
- Workloads could be segmented based on tagging (PCI, SOX, GDPR)  
- A shared platform model would enable centralized governance  
- Landing zone design would align cleanly with planned structure  

---

### **2. What We Discovered**

As implementation began, several real-world challenges emerged:

**Conflict Between Governance and Agility**

- Application teams expected rapid provisioning (e.g., spinning up environments on demand for development)
- Platform team enforced strict controls (e.g., approval workflows, restricted regions, limited access)

👉 Result:
- Delays in onboarding workloads  
- Friction between teams  

**Network Design Complexity**

- Initial plan: Hub-Spoke model with centralized firewall  

- Reality:
  - Some applications required direct internet access  
  - Others required private connectivity only  
  - Legacy integrations assumed flat network design  

👉 Example:

- Payment systems (PCI-DSS) required strict isolation  
- Customer portals required internet-facing endpoints  

**IAM Implementation Gaps**

- Plan assumed clear ownership boundaries  

- Reality:
  - Multiple teams requested elevated access  
  - Lack of clarity on role definitions  
  - Temporary access becoming permanent  

**Policy Enforcement Challenges**

- Policies defined during Plan phase (e.g., deny public IP, enforce tagging)

- Reality:
  - Policies blocking deployments  
  - Teams bypassing governance for speed  
  - Exceptions becoming common  

**Landing Zone Scope Creep**

- Initial scope:  
  - Core subscriptions  
  - Basic networking  
  - Identity and governance  

- Reality:
  - Additional requirements added:
    - Shared services (DNS, monitoring, logging)  
    - Security integrations  
    - Compliance-specific controls  

---

### 🧠 Key Insight

The Ready phase is where **design meets resistance** — from tools, teams, and real constraints.

---

### **3. Decisions Made**

**Decision 1: Refine Subscription & Environment Model**

Initial idea:
- Separate subscriptions per environment  

Revised approach:

- Platform subscriptions  (e.g., shared services, networking, security tools)
- Landing zone subscriptions  (e.g., workload-specific environments like Prod, Non-Prod)

**Decision 2: Implement Tiered Network Architecture**

Instead of a single rigid model:

- Hub-Spoke for regulated workloads  (e.g., PCI systems behind centralized firewall)
- Simplified VNet for non-critical workloads  (e.g., dev/test environments with controlled internet access)

**Decision 3: Introduce Role-Based IAM Model**

IAM was restructured:

- Platform team → Owner at platform layer  
- Application teams → Contributor at resource group level  
- Read-only access for audit teams  

**Decision 4: Shift Policy Enforcement Strategy**

Instead of strict enforcement from day one:

- Phase 1: Audit mode  (e.g., track violations without blocking deployments)
- Phase 2: Gradual enforcement  (e.g., deny policies for critical controls only)

**Decision 5: Introduce Compliance-Aligned Isolation**

Based on Plan phase tagging:

- PCI workloads → isolated subscriptions + network segmentation  
- SOX systems → enhanced logging and restricted access  
- GDPR workloads → region-bound deployment  

**Decision 6: Expand Landing Zone Scope**

Landing zone was expanded to include:

- Centralized logging  (e.g., logs aggregated across all subscriptions)
- Monitoring and alerting  (e.g., unified observability setup)
- Identity integration  (e.g., centralized identity provider with conditional access)


### **4. What Changed from Plan Phase**

| Plan Assumption | Ready Reality |
|----------------|-------------|
| Governance can be enforced strictly | Requires phased and adaptive enforcement |
| Network design is straightforward | Requires workload-specific variations |
| IAM roles are clearly defined | Needs iterative refinement |
| Landing zone scope is fixed | Expands with real requirements |
| Compliance tagging is sufficient | Requires architectural enforcement |

---

### 🧠 Key Insight

The Ready phase transforms plans into **working systems**, forcing adaptation to real-world constraints.

---

### **5. Final Output of Ready Phase**

At the end of this phase, ACME Corp had:

- Implemented landing zone architecture  
- Defined subscription and environment structure  
- Established IAM model with controlled access  
- Deployed network architecture with segmentation  
- Introduced governance and policy framework  
- Enabled centralized monitoring and logging  
- Established compliance-aligned isolation  

---

### 🔗 Transition to Adopt Phase

With the foundation in place:

- workloads could now be onboarded  
- migration execution could begin  
- real performance and operational challenges would surface  

This led into the **Adopt Phase**, where execution, migration, and stabilization would take place.

---

[⬅ Back to Series Home](index.md) | [⬅ Back to Plan-ACME](acme-plan.md) | [Next: Adopt-ACME ➡](acme-adopt.md)