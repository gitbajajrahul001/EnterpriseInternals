---
layout: default
title: Ready|Foundations
---

# Ready Phase – Establishing the Cloud Foundation

This section captures the Ready phase by defining the foundational environment required to enable secure, scalable, and governed cloud adoption.

---

## 🧭 What the Ready Phase Really Means

If the Plan phase defines *how cloud adoption will be structured*, the Ready phase defines **where and how workloads will be deployed in a controlled cloud environment**.

This phase establishes the **Landing Zone**, which acts as the foundation for all subsequent workloads.

---

## 🧱 Core Pillars of the Ready Phase

Cloud readiness is built on a set of interconnected pillars that establish the foundational environment for secure and scalable adoption.

---

## 🔷 1. Resource Organization & Hierarchy

A clear hierarchy is required to organize and manage cloud resources effectively.

### **Key Focus Areas:**

- Management group structure(e.g., Root → Platform → Landing Zones → Sandbox)
- Subscription strategy (e.g., separate subscriptions for Prod, Dev, Shared Services)
- Resource group organization (e.g., grouping resources by application, environment, or lifecycle)

### 🧠 Insight

A well-defined hierarchy enables:
- consistent governance  
- scalable resource management  
- separation of concerns across environments  

---

## 🔷 2. Identity & Access Management

Identity forms the foundation of security in cloud environments.

### **Key Focus Areas:**

- Centralized identity provider (e.g., Microsoft Entra ID as a single identity source)
- Role-based access control (e.g., assigning Reader, Contributor roles at subscription or resource group level)
- Least privilege access model (e.g., restricting admin access and granting only required permissions)

### 🧠 Insight

Identity is the primary control plane for:
- access management  
- policy enforcement  
- security posture  

---

## 🔷 3. Network Architecture

Networking defines how resources communicate within and outside the cloud environment.

### **Key Focus Areas:**

- Virtual network design  (e.g., separate VNets for Hub and Spokes)
- Hub-Spoke topology  (e.g., central hub for firewall, DNS, shared services; spokes for workloads)
- Connectivity with on-prem environments  (e.g., VPN Gateway or ExpressRoute)
- Private vs public access  (e.g., using Private Endpoints instead of exposing services publicly)

### 🧠 Insight

Network design establishes:
- isolation boundaries  
- secure communication paths  
- connectivity patterns across workloads  

---

## 🔷 4. Security Baseline

A foundational security posture must be established before workloads are deployed.

### **Key Focus Areas:**

- Encryption (e.g., disk encryption, storage encryption, TLS for data in transit)
- Threat protection  (e.g., Microsoft Defender for Cloud, endpoint protection)
- Secure configuration standards (e.g., disabling public access, enforcing secure ports)
- Identity-driven security controls (e.g., MFA, Conditional Access policies)

### 🧠 Insight

Security is most effective when embedded into the foundation, rather than added later.

---

## 🔷 5. Governance & Policy Enforcement

Governance ensures that cloud usage remains controlled and aligned with organizational standards.

### **Key Focus Areas:**

- Policy definitions and enforcement  (e.g., restricting regions, enforcing tagging, denying public IP creation)
- Tagging standards  (e.g., Environment=Prod, Owner=AppTeam, CostCenter=Finance)
- Resource compliance rules  (e.g., enforcing encryption, approved VM sizes)
- Environment restrictions  (e.g., limiting production deployments to specific subscriptions)

### 🧠 Insight

Governance enables:
- controlled flexibility  
- compliance adherence  
- standardized operations  

---

## 🔷 6. Cost Management Foundations

Cost controls must be embedded from the beginning.

### **Key Focus Areas:**

- Budget setup  (e.g., monthly spend limits per subscription)
- Cost allocation via tagging  (e.g., mapping cost to departments or applications)
- Cost visibility and reporting  (e.g., dashboards showing spend trends and anomalies)

### 🧠 Insight

Early cost governance ensures:
- transparency  
- accountability  
- sustainable cloud usage  

---

## 🔷 7. Monitoring & Observability

Visibility into the environment is essential for operations and troubleshooting.

### **Key Focus Areas:**

- Logging and monitoring setup  (e.g., Azure Monitor, Log Analytics workspace)
- Metrics and alerting  (e.g., CPU alerts, application latency thresholds)
- Centralized observability  (e.g., aggregating logs across subscriptions into a single workspace)

### 🧠 Insight

Observability provides the foundation for:
- operational stability  
- incident response  
- performance optimization  

---

## 🔷 8. Resilience & Backup Foundations

Basic resilience capabilities must be defined before workload deployment.

### **Key Focus Areas:**

- Backup strategy  (e.g., VM backups using Recovery Services Vault)
- Data protection policies  (e.g., retention policies for backups and logs)
- Availability considerations  (e.g., Availability Zones, region replication)

### 🧠 Insight

Resilience planning ensures that:
- data is protected  
- recovery mechanisms are defined  
- downtime impact is minimized  

---

## 🔷 9. Landing Zone Definition

The Landing Zone brings together all foundational elements into a cohesive environment.

### **Defines:**

- Environment structure  (e.g., Dev / Test / Prod separation)
- Network and connectivity model  (e.g., hub-spoke with centralized firewall)
- Identity and access model  (e.g., RBAC with centralized identity)
- Governance and policy framework  (e.g., policies applied at management group level)

### 🔗 Connection

The Landing Zone enables the **Adopt Phase**, where workloads are migrated and deployed.

---

## 🔗 Ready Phase Summary

The Ready phase establishes the foundation required for cloud adoption.

### 📄 Key Outputs:

- Defined resource hierarchy  
- Identity and access model  
- Network architecture design  
- Security and governance baseline  
- Cost management setup  
- Monitoring and observability configuration  
- Backup and resilience setup  
- Landing Zone definition  

### 🧠 Key Insight

The Ready phase ensures that cloud adoption begins on a **secure, governed, and scalable foundation**.

### 🔍 Closing Thoughts

A well-designed foundation enables:
- consistent deployment patterns  
- controlled growth  
- reduced operational risk  

The quality of the Ready phase directly impacts the success of all subsequent phases.

---
[⬅ Back to Series Home](index.md) | [⬅ Back to Plan-Foundation](plan-1.md) | [Next: Adopt-Foundations ➡](adopt-1.md)