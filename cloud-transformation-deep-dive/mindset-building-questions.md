---

layout: default
title: Mindset Building Questions|Cloud Transformation

---

# Questions that make you Think 

---

## Question #1 

From those 10,000 VMs, what specific data points would you extract to make migration decisions?

---

### **Sample Answer**

- From the current estate, I would extract application-centric and decision-enabling data.
- This includes mapping each VM to its parent application, along with business criticality, compliance classification, environment, and exposure profile.
- I would also capture workload roles (web/app/db), platform and database details, and underlying OS and licensing information.
- Critically, I would focus on dependency mapping across applications, data flows, and external integrations to avoid breaking services during migration.
- Finally, I would analyze resource utilization patterns — CPU, memory, storage, and network — to enable right-sizing and accurate cost modeling.


#### **This Covers:**


- business view ✔
- technical view ✔
- risk view ✔
- cost view ✔
- dependency view ✔


**Remember**

> - *Inventory* tells you what exists
> - *Dependencies* tell you what matters
> - *Utilization* tells you what it should become

---

### **A Few Decision Markers**

#### **1. Dependency & Data Flow**

> Application → Other Applications / Services / Data Sources

👉 *This is the #1 cause of migration failures*

**You need:**

- upstream/downstream dependencies
- API calls
- DB connections
- batch jobs
- third-party integrations

#### **2. Resource Utilization & Sizing**

**You need:**

- CPU usage
- Memory usage
- Disk I/O
- Network throughput

👉 *Without this:
> - you cannot right-size
> - you cannot estimate cost
> - you cannot optimize


#### **3. OS, Lifecycle, and Supportability**

**You need:**

- OS version (EOL risk)
- patch status
- licensing type (Windows, SQL, Oracle, RHEL)

👉 *This directly impacts:

- migration feasibility
- cost
- risk

---

##  Question #2

You’ve completed **initial discovery**. Service Provider team comes to you and says:**

> “We have the inventory. Let’s start designing the Azure Landing Zone so we can move fast.”

**This is a trap**

Most organizations say:

> “Yes, let’s build landing zone”

---
### **Sample Answer**

- I would not start full landing-zone design purely from infrastructure inventory.
- We can begin a **baseline platform design track**, but the final landing zone must be informed by workload classification, regulatory boundaries, network dependencies, identity model, operating model, and regional/data residency requirements.
- In parallel, we should validate management group structure, subscription strategy, hybrid connectivity, IP plan, security guardrails, shared services, tagging, and IaC approach.
- The key is to avoid building a technically clean landing zone that does not match how the bank’s applications, compliance zones, and operating teams actually work.”

**Remeber**
> - A landing zone is not just a cloud build.
> - It is the technical expression of governance, security, operations, network, compliance, and workload strategy.

---

### **What “Baseline Platform Design Track” means**

**It means:**

Start building the cloud foundation in parallel — but only the parts that are stable, universal, and low-risk — without locking yourself into wrong decisions for workloads later.


#### **Think of it like this:**

You don’t wait 6 months to build anything. But you also don’t design everything upfront based on incomplete data.

**So you split:**

| Track | Purpose |
| --- | --- |
| Platform Track (Baseline) | Build core cloud foundation |
| Workload Track | Refine based on real application needs |

* * *

### **What you CAN design early (Baseline)**

These are **safe, foundational, and unlikely to change drastically**

#### **1\. Management Group Hierarchy (Initial Version)**

**Example:**

*   Root
    *   Platform
    *   Landing Zones
    *   Sandbox

👉 *Why safe?*
> Because structure can evolve, but initial separation is predictable.

* * *

#### **2\. Subscription Strategy (High-Level)**

**Example:**

*   Platform Subscription (shared services)
*   Connectivity Subscription
*   Identity Subscription
*   App Landing Zone Subscriptions

👉 You don’t need full app mapping yet — just **pattern**

* * *

#### **3\. Identity Foundation**

**Example:**

*   Entra ID (Azure AD) integration
*   RBAC baseline roles
*   PIM (Privileged Identity Management)

👉 Identity model is mostly **universal**

* * *

#### **4\. Core Security Guardrails (Baseline Policies)**

**Example:**

*   No public IP by default
*   Allowed regions
*   Enforced tagging
*   Encryption required

👉 These are **bank-level controls**, not workload-specific

* * *

#### **5\. Logging & Monitoring Foundation**

**Example:**

*   Central Log Analytics Workspace
*   Diagnostic settings baseline
*   Activity logs

👉 Needed regardless of workload

* * *

#### **6\. IaC Framework**

**Example:**

*   Terraform/Bicep structure
*   Git repo structure
*   CI/CD pipelines

👉 This is **how you build**, not what you build

* * *

### **What you should NOT finalize yet**

This is where most teams make mistakes.

#### **1\. Network Topology (final)**

*   Hub-spoke vs vWAN vs segmentation  

👉 Depends on:
>*   app communication
> *   latency
> *   regulatory zones



#### **2\. IP Addressing (final ranges)**

👉 Without dependency + scale clarity → rework later



#### **3\. Subscription-per-app strategy (final)**

👉 Depends on:

> *   org structure
> *   ownership
> *   cost model

#### **4\. Security exceptions**

👉 You don’t know yet:

> *   which apps need internet
> *   which need special ports

#### **5\. Region strategy (final)**

👉 Depends on:

> *   data residency
> *   DR requirements
> *   app latency

---
### **Real-world example (this will click)**

#### **Wrong approach**

**Team says:**

> “Let’s design full hub-spoke, IP schema, 200 subscriptions, firewall rules…”

👉 3 months later:

> *   SAP needs different network
> *   compliance needs region split
> *   apps break due to wrong segmentation

→ **Rework**

#### **Correct approach (Baseline Track)**

**You say:**

> “Let’s build identity, governance, logging, basic MG structure, IaC — and keep network and workload boundaries flexible until validated.”

---

### **Simple mental model**

#### **Build early:**

*  Controls
*  Governance
*  Tooling

#### **Delay slightly:**

*   Topology
*   Segmentation
*   Workload placement

#### **Define in Baseline:**

*   Management group structure (initial)
*   Subscription pattern (platform vs landing zones)
*   Tagging strategy (MANDATORY early)
*   Security baseline policies
*   Identity model
*   Logging/monitoring
*   IaC framework


*Baseline platform design* is building what you are confident about — while deliberately postponing what depends on unknowns.
---

## **Question #3**

You’ve started baseline platform work. Meanwhile, discovery team comes back and says:

“We found multiple applications where:"
> 
> *   no clear owner exists
> *   dependencies are unclear
> *   some VMs haven’t been accessed in months
> *   duplicate environments exist (shadow IT)

👉 What do you do with these workloads?

>You don’t “wait” — you classify and act in parallel

* * *

### **Sample Answer:** 
  
- We shouldn’t block the transformation waiting for complete clarity on these workloads.
- I would classify them into three categories — candidates for retirement, candidates for further investigation, and low-risk workloads that can be used for early migration validation.
- For VMs with no activity or unclear ownership, we can initiate a structured decommissioning validation process with defined timelines and business sign-off.
- In parallel, we should engage application teams and escalate where needed, but not make overall progress dependent on them.
- This approach allows us to reduce estate complexity early, unlock cost savings, and keep the transformation moving while resolving unknowns in a controlled manner.”
  

### **Why this is strong**

#### You didn’t block progress

> Critical for large programs
> 

#### You introduced classification

> This is architect thinking
> 
#### You turned a problem into an advantage

> Cleanup = cost savings + simplification

#### You added control (validation before delete)
> 
> CISO + CIO comfort
> 

---

#### **Key mindset shift**

> ❌ “We need clarity before moving”  
> ✅ “We move forward while systematically creating clarity”
> 
---

### **Further explaining (No Owner Scenario)**

If no direct application owner exists, we shift from _application ownership_ to _organizational accountability_.


#### **Practicle Approach in Real transformations**

*   100% clarity → never happens
*   70% clarity + strong controls → progress happens
 
> - You don’t rely on “finding owners”. 
> - You create a governed fallback ownership model


#### **You do this Instead:**

#### **1\. Use CMDB / Org Mapping (if available)**


 > *   Map VM → Cost center / Business unit
 > *   Identify → BU head + App portfolio owner + Infra owner
 
👉 Someone always owns the budget

#### **2\. Introduce “Default Ownership Escalation**

> If no owner: Escalate to:

> *   Application Portfolio Owner OR
> *   Business Unit Head OR
> *   CIO delegate

👉 You don’t ask:

> “Who owns this app?”

👉 You ask:

> “Who is accountable if we delete this?”

#### **3\. Define a Formal Decommission Policy**

Example:

 > *   Notify stakeholders (email + ticket)
 > *   30-day observation window
 > *   No activity + no claim → mark as decommission candidate
 > *   Final approval: Infra Head / CIO office / Governance board
> 


#### **4\. Use Data to Support Decision**

Example:

> *   No login activity
> *   No network traffic
> *   No dependency calls
> *   No monitoring alerts
> 

👉 This reduces fear-based resistance

#### **5\. Implement “Soft Decommission First”**

Before deleting:

> *   Shutdown VM
> *   Keep snapshot/backup
> *   Monitor impact for X days

👉 If no issue → delete permanently

---

### **Sample Response(No Owner Sceanrio)**

- In cases where application ownership is unclear, we shift to an accountability model based on business unit or cost ownership.
- We define a structured decommissioning process with notifications, observation windows, and escalation to the CIO or designated governance body if no owner is identified.
- Decisions are supported by usage and dependency data, and we follow a staged approach — starting with shutdown and monitoring before final deletion.
-  This ensures we can safely reduce unused assets without blocking progress due to ownership gaps.”
   
---
### **Key Mindset Shift**

> - ❌ “No owner → we can’t act”  
> - ✅ “No owner → escalate accountability and act with governance”

You don’t wait for perfect org structures. You design around enterprise chaos.

---