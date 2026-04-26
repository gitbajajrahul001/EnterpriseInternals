# Azure Architecture Playbook — Part 1

## Azure Networking Fundamentals: What Actually Happens (Not What You Think)


* * *

## Introduction


Most people start Azure networking by learning terms:

VNet. Subnet. NSG. Route Table.

And very quickly, they feel confident.

Until something breaks.

A connection that _should_ work doesn’t.  
Or worse — something works that **shouldn’t**.

That’s when it becomes clear:

> The problem is not lack of knowledge — it’s the wrong mental model.

This part is about fixing that.

* * *

## 1\. The First Mistake: Assuming Azure Is Secure by Default

# 

Let’s start with a simple setup:

*   One VNet
*   Three subnets: Web, App, DB
*   No NSGs

Now ask yourself:

Can Web talk to DB?

Most people hesitate.

The answer is:

Yes. Freely. Completely. By default.

* * *

### Why Azure Works This Way

# 

Because Azure optimizes for **connectivity first**, not restriction.

If Azure blocked everything by default:

*   Nothing would work out of the box
*   Every deployment would require full rule definition
*   Developer experience would be terrible

So Azure makes a trade-off:

> Everything can talk — until you say otherwise

* * *

### What This Breaks in Your Thinking

# 

People assume:

“I separated tiers, so I created security.”

No.

You created **structure**, not **control**.

* * *

### Real-World Impact

# 

In production environments, this leads to:

*   Web tier compromise → lateral movement to DB
*   Internal services exposed unintentionally
*   Data exfiltration via unrestricted outbound

* * *

### Architect Insight

# 

You don’t start with:

“How do I connect things?”

You start with:

> “What should NOT be allowed to talk?”

* * *

## 2\. Subnets: The Most Misunderstood Concept

# 

Let’s address this directly.

A subnet is not a security boundary.

It is a **policy attachment point**.

* * *

### Why Subnets Exist

# 

Subnets give you:

*   A place to apply NSGs
*   A place to apply routing policies
*   A way to organize workloads

That’s it.

* * *

### What People Get Wrong

# 

They think:

*   Web subnet is isolated from DB subnet
*   App subnet acts as a middle layer

None of this is true unless enforced.

* * *

### What Actually Happens

# 

If no NSGs exist:

*   Web can directly reach DB
*   App is not a “mandatory hop”
*   There is no enforced layering

* * *

### Why This Matters

# 

Because many architectures look like this on diagrams:

User → Web → App → DB

But in reality:

Web → DB (directly possible)

* * *

### Architect Insight

# 

Subnets don’t enforce architecture.

They **enable you to enforce architecture**.

* * *

## 3\. NSG: Where Security Actually Begins

# 

NSG is where your design starts becoming real.

Not before that.

* * *

### What NSG Really Does

# 

NSG answers one question:

> Should this packet be allowed?

It does not:

*   Decide where the packet goes
*   Understand application logic
*   Guarantee security by itself

* * *

### What People Miss

# 

NSG is evaluated twice:

*   Once when traffic leaves
*   Once when traffic arrives

* * *

### Why This Matters

# 

Let’s say:

*   Web allows outbound to App
*   App blocks inbound from Web

Result:

Traffic fails.

* * *

### Where People Fail in Debugging

# 

They check only one side.

This leads to:

*   “It should work” confusion
*   Time wasted in wrong areas

* * *

### Architect Insight

# 

Every flow must be allowed at:

*   Source (outbound)
*   Destination (inbound)

Missing either = failure

* * *

## 4\. Routing: The Silent Force Nobody Thinks About

# 

Most people think routing is something you “add”.

That’s wrong.

Routing is always happening.

* * *

### Default Behavior

# 

Azure automatically knows:

*   Which IP ranges belong to the VNet
*   How to route traffic internally

So even without any route tables:

Everything already has a path.

* * *

### The Real Role of UDR

# 

UDR is not for enabling routing.

It is for **breaking default routing and forcing a new path**.

* * *

### Example

# 

Without UDR:

App → DB → direct

With UDR:

App → Firewall → DB

* * *

### Why This Matters

# 

Because people assume:

“If I add a firewall, traffic will pass through it.”

No.

Traffic only passes through firewall if:

> Routing forces it to

* * *

### Architect Insight

# 

Routing defines reality.

If routing is wrong, security design is irrelevant.

* * *

## 5\. The Problem of Asymmetric Routing

# 

This is where real systems start breaking.

* * *

### Scenario

# 

Forward path:

App → Firewall → DB

Return path:

DB → App (direct)

* * *

### What Happens

# 

Firewall sees:

*   Request (SYN)
*   But not response (SYN-ACK)

Later packets are dropped.

* * *

### Why

# 

Firewalls are stateful.

They track conversations.

If they don’t see both sides:

They assume something is wrong.

* * *

### Real-World Impact

# 

*   Intermittent failures
*   Timeouts
*   “It works sometimes” issues

* * *

### Architect Insight

# 

Always validate:

> Forward path AND return path

* * *

## 6\. DNS: The Layer Everyone Ignores (Until It Breaks Everything)

# 

Now we come to the most underestimated component.

DNS.

* * *

### What People Think DNS Does

# 

“Just resolves names to IPs”

* * *

### What DNS Actually Does

# 

DNS decides:

> Which architecture path your traffic will take

* * *

### Example

# 

Same connection string:

mydb.database.windows.net

* * *

### Case 1: Public Resolution

# 

Returns public IP

Flow:

App → Public Endpoint → Azure backbone → SQL

* * *

### Case 2: Private Resolution

# 

Returns private IP

Flow:

App → Private Endpoint → SQL

* * *

### Same code

### Completely different architecture

# 

* * *

### Why This Is Dangerous

# 

Because:

*   System works in both cases
*   One is secure, one is not
*   No obvious failure

* * *

### Architect Insight

# 

Wrong DNS does not always break systems.

Sometimes it silently bypasses your design.

* * *

## 7\. Private Endpoint: The Biggest Mental Trap

# 

Now we fix one major misunderstanding.

* * *

### What People Think

# 

“Private Endpoint puts the service inside my VNet”

* * *

### What Actually Happens

# 

Private Endpoint creates:

*   A NIC inside your VNet
*   With a private IP

But:

> The actual service remains inside Microsoft infrastructure

* * *

### So What Is It?

# 

It is a **proxy entry point**

* * *

### Real Flow

# 

App → Private Endpoint → Azure fabric → SQL

* * *

### What the Service Sees

# 

| Field | Value |
| --- | --- |
| Source IP | Private Endpoint IP |
| Not visible | Original client IP |

* * *

### Why This Matters

# 

You cannot:

*   Apply NSG on destination
*   Filter based on original VM IP
*   Treat it like VM-to-VM traffic

* * *

### Architect Insight

# 

Private Endpoint changes the model from:

Network control

to

Access control via:

*   Source restrictions
*   DNS
*   Identity

* * *

## 8\. The Core Truth That Connects Everything

# 

If you take one thing from this part, it should be this:

> Traffic flow is not controlled by one thing

It is controlled by layers:

| Layer | Responsibility |
| --- | --- |
| DNS | Where to go |
| NSG | Whether allowed |
| Routing | How to go |
| Firewall | Inspection |
| Identity | Who is allowed |

* * *

### Why People Struggle

# 

Because they try to solve problems at one layer.

Example:

Trying to fix routing issue with NSG.

Or:

Trying to enforce security only via Private Endpoint.

* * *

### Architect Insight

# 

You don’t design components.

You design **interactions between layers**.

* * *

## Final Thought

# 

Azure networking is not complex because there are too many services.

It is complex because:

*   Defaults are permissive
*   Behavior is layered
*   Failures are not always visible

Once you understand:

*   What is happening
*   Why it is happening
*   Where control actually exists

You stop reacting to problems.

You start predicting them.

And that is where architecture begins.