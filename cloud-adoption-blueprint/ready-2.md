---
layout: default
title: Ready|Consulting Approach
---

# Ready Phase – Consulting Approach

The Ready phase is where the cloud foundation is implemented in alignment with the Plan phase.

In practice, this phase is not just about setting up a landing zone, but about:
- making foundational design decisions  
- enforcing governance early  
- avoiding patterns that lead to long-term operational issues  

---

## 🧭 How the Ready Phase is Approached

Cloud readiness is built on a set of interconnected pillars that establish a secure, governed, and scalable foundation.

In real-world engagements, this phase often exposes:
- gaps in planning  
- unclear ownership  
- conflicting requirements  

---

## 🔷 1. Resource Organization & Hierarchy

Hierarchy design is heavily influenced by governance, scale, and ownership.

### **Key Considerations:**

- Subscription design  (e.g., separate subscriptions for Prod, Non-Prod, and Shared Services instead of mixing workloads in a single subscription)
- Environment isolation  (e.g., isolating production workloads at subscription level vs keeping Dev/Test in shared environments)
- Placement of shared services  (e.g., hosting firewall, DNS, and identity services in a centralized “Platform” subscription)*  

### ⚠️ Common Challenge

- Multiple teams deploying into a single subscription  
- No clear separation between environments  
- Confusion around ownership boundaries  

### 🧠 Insight

Early hierarchy decisions impact:
- governance enforcement  
- access control boundaries  
- long-term scalability  

---

## 🔷 2. Identity & Access Management

IAM decisions directly influence security posture and operational control.

### **Key Considerations:**

- Role assignment strategy (e.g., assigning Contributor at resource group level instead of giving Owner at subscription level)
- Privileged access control  (e.g., limiting Owner access to platform admins and using Privileged Identity Management for elevation)
- Access lifecycle management  (e.g., periodic RBAC reviews or automated access expiry policies)

### ⚠️ Common Challenge

- Excessive use of Owner/Contributor roles  
- No enforcement of least privilege  
- Access granted but never reviewed  

### 🧠 Insight

IAM is often configured for convenience during setup, but becomes a major risk if not controlled early.

---

## 🔷 3. Network Architecture

Network design must balance security, scalability, and simplicity.

### **Key Considerations:**

- Topology choice  (e.g., hub-spoke architecture with centralized firewall vs flat network for smaller deployments)
- Connectivity approach  (e.g., starting with VPN connectivity and evolving to ExpressRoute for production workloads)
- Exposure model  (e.g., using Private Endpoints for PaaS services instead of exposing them via public IPs)

### ⚠️ Common Challenge

- Over-engineering network design for future scale  
- Public exposure of services due to lack of planning  
- Lack of segmentation between workloads  

### 🧠 Insight

Overly complex network designs often slow down adoption without providing proportional benefits.

---

## 🔷 4. Security Baseline

Security must be enforced consistently across the environment.

### **Key Considerations:**

- Mandatory controls  (e.g., enforcing encryption for storage accounts and managed disks)
- Identity-based security  (e.g., enforcing MFA and Conditional Access policies for all privileged users)
- Threat protection  (e.g., enabling Microsoft Defender for Cloud for workload protection)

### ⚠️ Common Challenge

- Security policies defined but not enforced  
- Different environments having inconsistent configurations  
- Security implemented after workloads are deployed  

### 🧠 Insight

Security gaps are rarely due to lack of tools — they are due to lack of enforcement.

---

## 🔷 5. Governance & Policy Enforcement

Governance establishes the guardrails for cloud usage.

### **Key Considerations:**

- Policy enforcement scope (e.g., enforcing region restrictions or tagging policies at management group level)
- Flexibility vs control  (e.g., allowing Dev environments more flexibility while restricting production deployments)
- Policy enforcement mode (e.g., starting with audit policies and moving to deny policies once baseline is stable)

### ⚠️ Common Challenge

- Overly restrictive policies blocking deployments  
- No governance leading to inconsistent environments  
- Lack of tagging and cost attribution  

### 🧠 Insight

Effective governance enables controlled flexibility rather than restricting innovation.

---

## 🔷 6. Cost Management Foundations

Cost control must be designed into the environment.

### **Key Considerations:**

- Cost ownership (e.g., assigning cost responsibility to application teams via tagging or subscription ownership)
- Budget controls (e.g., setting budget alerts for each subscription or cost center)
- Cost visibility  (e.g., dashboards showing cost by application, environment, or department)

### ⚠️ Common Challenge

- No clear ownership of cloud spend  
- Lack of visibility into usage patterns  
- Reactive cost management after overspending  

### 🧠 Insight

Cost issues are often driven by lack of accountability, not just high consumption.

---

## 🔷 7. Monitoring & Observability

Observability must be implemented as part of the foundation.

### **Key Considerations:**

- Centralized logging (e.g., sending logs from all subscriptions to a central Log Analytics workspace)
- Alerting strategy  (e.g., defining alerts for CPU usage, failed deployments, or application errors)
- Visibility across environments  (e.g., unified dashboards across Dev, Test, and Prod environments)

### ⚠️ Common Challenge

- Logs collected but never reviewed  
- Excessive alerts leading to alert fatigue  
- Fragmented monitoring across teams  

### 🧠 Insight

Observability is only valuable when it leads to actionable insights and response mechanisms.

---

## 🔷 8. Resilience & Backup

Resilience must be validated, not just configured.

### **Key Considerations:**

- Backup configuration (e.g., enabling VM backups using Recovery Services Vault with defined schedules)
- Recovery validation  (e.g., periodically testing restore scenarios for critical workloads)
- Availability design  (e.g., deploying workloads across Availability Zones for high availability)

### ⚠️ Common Challenge

- Backups configured but never tested  
- Misalignment between expected and actual recovery capabilities  
- Over-reliance on default configurations  

### 🧠 Insight

Resilience is proven through testing, not configuration.

---

## 🔷 9. Landing Zone Implementation

The landing zone is where all foundational decisions are brought together.

### **Key Considerations:**

- Alignment with planned architecture (e.g., ensuring subscriptions, networking, and IAM match the Plan phase design)
- Enforcement of governance (e.g., policies applied consistently across all environments)
- Readiness for workload onboarding (e.g., ability to deploy workloads without manual intervention or reconfiguration)

### ⚠️ Common Challenge

- Partial landing zone implementation  
- Skipping governance for faster deployment  
- Inconsistency across environments  

### 🧠 Insight

A landing zone is only complete when it can support **consistent, repeatable workload deployment**.

---

## ⚠️ Handling Real-World Challenges in Ready Phase

### **Common Scenarios**

| Situation | Approach |
|----------|---------|
| Conflicting design preferences | Align based on simplicity and business priorities |
| Over-engineering | Start simple and evolve incrementally |
| Missing governance | Introduce baseline policies early |
| Security vs agility conflict | Define controlled flexibility |

---

## 🔗 Summary

### 📄 Key Outputs

The Ready phase should result in:

- Implemented landing zone  
- Defined resource hierarchy  
- IAM and access controls  
- Network architecture setup  
- Security and governance enforcement  
- Cost management baseline  
- Monitoring and observability setup  
- Backup and resilience configuration  

### 🧠 Key Insight

The Ready phase is not just about building the foundation — it is about building it **correctly the first time to avoid long-term rework**.

### 🔍 Closing Thoughts

Most challenges observed in later phases can be traced back to decisions made during the Ready phase.

A well-executed foundation ensures:
- consistency  
- security  
- scalability  

and enables smooth transition into workload adoption.

---

[⬅ Back to Ready Foundations](ready-1.md) | [Next: Adopt Phase ➡](adopt-1.md)