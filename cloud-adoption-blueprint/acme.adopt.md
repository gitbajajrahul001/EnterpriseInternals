---
layout: default
title: ACME|Adopt
---


## 🔷 Phase 4: Adopt (Day 90 → Day 180)

With the landing zone in place, ACME Corp began executing workload migration and modernization in a phased manner.

---

### **1. Initial Understanding (From Ready Phase)**

At the start of the Adopt phase, the environment was assumed to be:

- Ready for workload onboarding  
- Governed through policies and IAM controls  
- Segmented based on compliance requirements  
- Equipped with monitoring and logging  

Migration execution was expected to follow the defined wave model.

---

### **2. What We Discovered**

As migration execution began, several practical challenges emerged:

**Migration Tooling Limitations**

- Azure Migrate (or equivalent tools) identified infrastructure  but missed application-level dependencies  
- Example:  
  - A customer portal migrated successfully  
  - But failed post-migration due to missing backend API dependency  

**Data Migration Bottlenecks**

- Large databases took significantly longer to migrate (e.g., multi-terabyte financial datasets)
- Continuous replication caused performance degradation in source systems  
- Cutover windows became difficult to maintain  

**Compliance Constraints Impacting Migration**

- PCI workloads could not be moved using standard migration patterns (e.g., required isolated environments and additional validation steps)
- SOX systems required audit logging before migration could proceed  

**Performance Variability Post-Migration**

- Applications showed different behavior in cloud:

  - CPU spikes due to incorrect VM sizing  
  - Increased latency due to network routing changes  

**Operational Readiness Gaps**

- Operations teams unfamiliar with cloud troubleshooting  
- Alerts configured but not actionable  
- Incident response slower than expected  

---

### 🧠 Key Insight

Migration success is not measured by “workloads moved”, but by **workloads functioning reliably in the new environment**

---

### **3. Decisions Made**

**Decision 1: Introduce Pilot-Based Migration**

Instead of executing full waves directly:

- Each wave started with pilot workloads  (e.g., migrating a subset of applications first to validate approach)

**Decision 2: Refine Migration Strategy Mid-Execution**

Initial assumptions were revisited:

| Application | Planned Strategy | Revised Execution |
|------------|----------------|------------------|
| Customer Portal | Rehost | Replatform (performance issues) |
| Reporting System | Replatform | Phased migration (data constraints) |
| Payment System | Retain | Partial modernization (API layer only) |

**Decision 3: Strengthen Data Migration Approach**

- Introduced staged data migration  (e.g., pre-load + incremental sync + final cutover)
- Scheduled migrations during low-usage windows  

**Decision 4: Adjust Migration Waves Dynamically**

Instead of fixed sequencing:

- Wave timelines adjusted based on:
  - migration success  
  - dependency resolution  
  - business readiness  

**Decision 5: Enhance Observability During Migration**

- Introduced workload-level monitoring  (e.g., application performance dashboards)
- Improved alerting  (e.g., actionable alerts instead of generic thresholds)

**Decision 6: Establish Stabilization Period**

After each migration wave:

- Defined stabilization window  (e.g., 2–4 weeks before next wave)

- Activities included:
  - issue resolution  
  - performance tuning  
  - cost optimization  

**Decision 7: Integrate Operations Early**

- Involved operations teams during migration  (e.g., shadow support during initial waves)
- Updated incident management processes for cloud  

---

### **4. What Changed from Ready Phase**

| Ready Assumption | Adopt Reality |
|-----------------|--------------|
| Landing zone is fully ready | Requires continuous adjustments |
| Migration waves will execute as planned | Requires dynamic sequencing |
| Tools will handle migration smoothly | Requires manual intervention and validation |
| Performance will remain consistent | Requires tuning and optimization |
| Operations are ready | Requires training and integration |

---

### 🧠 Key Insight

The Adopt phase transforms architecture into **operational reality**, exposing gaps that only execution can reveal.

---

### **5. Final Output of Adopt Phase**

At the end of this phase, ACME Corp had:

- Migrated and validated key workloads  
- Modernized selected applications  
- Established stable and optimized environments  
- Implemented refined migration patterns  
- Integrated workloads into operational processes  

---

### 🔗 Transition to Operate & Govern Phase

With workloads successfully running in cloud:

- focus shifts to continuous governance  
- cost optimization becomes ongoing  
- compliance enforcement becomes operational  

This leads into the **Operate & Govern Phase**, where the environment is sustained, controlled, and optimized over time.

---

[⬅ Back to Series Home](index.md) | [⬅ Back to ACME-Ready](acme-ready.md)