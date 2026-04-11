---
layout: default
title: Stage 5
---
## Navigate This Series

| Stage | Link |
|------|------|
| Stage 0: Context Setting | [Open](stage-0.md) |
| Stage 1: Trigger & Problem Recognition | [Open](stage-1.md) |
| Stage 2: Scoping & Alignment | [Open](stage-2.md) |
| Stage 3: Current-State Assessment | [Open](stage-3.md) |
| Stage 4: Future-State Vision | [Open](stage-4.md) |
| Stage 5: Sourcing Strategy | [Open](stage-5.md) |
| Stage 6: RFI | [Open](stage-6.md) |
| Stage 7: RFP Creation | [Open](stage-7.md) |
| Stage 8–12: Execution | [Open](stage-8-12.md) |

---
# 🏢 Stage 5 — Sourcing Strategy Definition

## 🎯 Goal

Define:

How will Acme go to market to find the right partner(s)?

---

## 👥 Who Is Involved

| Role | Description |
|------|------------|
| Procurement Team | Sourcing specialists who manage vendor selection process |
| CIO / CTO | Chief Information Officer / Chief Technology Officer |
| Enterprise Architects | Provide architectural direction and constraints |
| Finance Team | Validate financial approach and constraints |
| Legal Team | Ensure contractual and compliance considerations |

---

## 🛠 What Happens in This Stage

### 1. Decide Engagement Model

Acme decides:

| Model |
|------|
| Single vendor (one partner does everything) |
| Multi-vendor (different vendors for migration, managed services, platform engineering) |

👉 Trade-off:

| Option | Trade-off |
|--------|----------|
| Single vendor | Simpler governance |
| Multi-vendor | Best-of-breed but complex coordination |

---

### 2. Decide Scope Packaging

Define how work is structured:

| Approach |
|----------|
| End-to-end transformation (strategy + migration + operations) |
| Migration project |
| Managed services (run operations) |
| Platform build |

---

### 3. Decide Commercial Model

How vendors will be paid:

| Model | Description |
|------|------------|
| Fixed price | Defined scope, fixed cost |
| Time & Material | Pay per effort |
| Managed services | Monthly recurring cost |
| Outcome-based | Linked to KPIs like cost reduction |

---

### 4. Define Vendor Qualification Criteria

What kind of vendors are eligible:

| Criteria |
|----------|
| Experience in large-scale cloud transformation |
| SAP (Systems, Applications, and Products in Data Processing) migration capability |
| Multi-cloud expertise (Azure, AWS, etc.) |
| Global delivery capability |

---

## 📦 Output

| Output |
|--------|
| Sourcing Strategy Document |
| Vendor selection approach defined |

--- 
# Now a Deeper Dive in each Section

# 🧠 Sourcing Strategy Decisions — How Enterprises Actually Decide

---

# 1️⃣ Decide Engagement Model

## ❓ What Is This?

How many vendors and how responsibilities are split.

---

## 🔑 Options

### A. Single Vendor Model

One vendor does:

| Scope |
|-------|
| Migration |
| Platform |
| Operations |

---

### B. Multi-Vendor Model

Different vendors for:

| Scope |
|-------|
| Migration |
| Managed services |
| Platform engineering |

---

## 🧠 Decision Framework

Ask 3 questions:

| Question | Guidance |
|----------|----------|
| How mature is the client? | Low maturity (like Acme) → Single vendor preferred<br>High maturity → Multi-vendor possible |
| How strong is internal governance? | Weak governance → Single vendor<br>Strong governance → Multi-vendor |
| Is speed critical? | Yes → Single vendor (faster execution)<br>No → Multi-vendor (more optimized) |

---

## 🎯 For ACME (Your Scenario)

👉 Recommended:

**Single Vendor (initially)**

### Why:

| Reason |
|--------|
| Already chaotic |
| Weak ITSM (Information Technology Service Management) |
| Poor accountability |

👉 Multi-vendor will increase chaos

---

# 2️⃣ Decide Scope Packaging

## ❓ What Is This?

How you bundle the work.

---

## 🔑 Options

### A. End-to-End Transformation

One scope:

| Scope |
|-------|
| Strategy |
| Migration |
| Platform |
| Operations |

---

### B. Split Scope

Separate:

| Scope |
|-------|
| Migration project |
| Managed services |
| Platform build |

---

## 🧠 Decision Framework

| Question | Guidance |
|----------|----------|
| Do you know your future state clearly? | No → End-to-end (vendor helps define)<br>Yes → Split scope possible |
| Do you want flexibility later? | Yes → Split scope<br>No → End-to-end |
| Do you trust vendors deeply? | Low trust → Split scope<br>High trust → End-to-end |

---

## 🎯 For ACME

👉 Recommended:

**Phased End-to-End**

### Meaning:

| Phase |
|-------|
| Start with: Assessment + migration |
| Then: Platform + operations |

### Why:

| Reason |
|--------|
| Acme is not mature enough to split cleanly |
| But full lock-in is also risky |

---

# 3️⃣ Decide Commercial Model

## ❓ What Is This?

How vendors get paid.

---

## 🔑 Options

| Model | Description | Good For |
|------|------------|----------|
| Fixed Price | Defined scope, fixed cost | Well-defined work |
| Time & Material (T&M) | Pay for effort | Uncertain scope |
| Managed Services | Monthly recurring cost | Operations |
| Outcome-Based | Pay based on results (e.g., cost reduction) | Rare but powerful |

---

## 🧠 Decision Framework

| Question | Guidance |
|----------|----------|
| Is scope clear? | Yes → Fixed price<br>No → T&M |
| Is work ongoing? | Yes → Managed services |
| Do you want risk transfer? | Yes → Fixed price / outcome-based<br>No → T&M |

---

## 🎯 For ACME

👉 Recommended mix:

| Area | Model |
|------|-------|
| Migration | T&M (uncertain complexity) |
| Platform build | Fixed price (partially defined) |
| Operations | Managed services |

👉 This is very common in real world

---

# 4️⃣ Define Vendor Qualification Criteria

## ❓ What Is This?

Who is even allowed to bid?

---

## 🧠 Think in 4 Dimensions

### 1. Technical Capability

| Capability |
|------------|
| Cloud expertise (Azure, AWS) |
| SAP migration experience |
| Automation capability |

---

### 2. Scale Experience

| Criteria |
|----------|
| 10,000+ VMs experience |
| Global client handling |

---

### 3. Delivery Capability

| Capability |
|------------|
| Global presence |
| 24/7 support |
| Skilled workforce |

---

### 4. Financial & Stability

| Criteria |
|----------|
| Long-term engagement capability |
| Financial stability |

---

## 🎯 For ACME

Minimum criteria:

| Requirement |
|-------------|
| Proven large-scale cloud migration experience |
| SAP transformation expertise |
| Multi-cloud capability |
| Strong automation & platform engineering practice |
| Global delivery model |

---

# 🧩 Is There a Standard Pattern?

👉 YES — here’s the simplified pattern used in real enterprises:

| Decision Area | Typical Choice |
|--------------|---------------|
| Engagement Model | Single Vendor (initially) |
| Scope Packaging | Phased End-to-End |
| Commercial Model | Hybrid (T&M + Fixed + Managed) |
| Vendor Criteria | High experience + scale |

---

# ⚡ Key Insight (Very Important)

These decisions are not independent.

They are linked:

| Decision | Impact |
|----------|--------|
| Single vendor | Easier fixed pricing |
| Multi-vendor | Requires strong governance |
| T&M | Needs trust and oversight |
| Fixed price | Requires clarity |

---

# 🧠 How You Should Think Going Forward

Whenever you face such decisions, ask:

| Question |
|----------|
| What is the current maturity? |
| What is the risk tolerance? |
| What is the speed vs control trade-off? |
| What is the internal capability? |

---

[⬅ Back to Series Home](index.md) | [Next: Stage 6 ➡](stage-6.md)

