# **CERTIFICATE CLOUD PRACTITIONER**
## **DOMAIN 1: Cloud Concepts - Define the benefits of the AWS Cloud**
### 1.1 Define the benefits of the AWS Cloud 
## What is AWS?
* **Definition:** World's most comprehensive cloud; 200+ services.
* **Value:** Lower costs, become more agile, innovate faster.

---

## 5 Criteria of Cloud Computing
1.  **On-Demand Self-Service:** Provision resources (servers, databases) without human interaction (via console, CLI, API).
2.  **Network Connectivity:** Access resources over the network (HTTP, VPN, SSH).
3.  **Resource Pooling:** AWS shares large pools of resources (servers, storage) among multiple customers.
    * This enables **Economies of Scale** (AWS buys in bulk, passes savings to you).
4.  **Elasticity:** Scale resources up or down to match demand.
5.  **Measured Service:** Monitor, control, and pay for only the resources you use.

---

## AWS Global Infrastructure
* **Core Components:** Regions, Availability Zones (AZs), Edge Locations.
* **Purpose:** Allows you to build resilient and **highly available** systems.

---

## Availability vs. Tolerance vs. Recovery
* **High Availability (HA):**
    * **What:** System recovers *quickly* from a failure.
    * **Example:** An active server and a standby server. If active fails, you "failover" to standby.
    * **Key:** **Minimal downtime** is possible.
* **Fault Tolerance (FT):**
    * **What:** System continues operating *during* a failure.
    * **Example:** Two *active* servers. If one fails, the other handles the load immediately.
    * **Key:** **No downtime.** (More expensive than HA).
* **Disaster Recovery (DR):**
    * **What:** The **plan and process** for how to recover *after* a major disaster.

---

## Scaling vs. Elasticity
* **Vertical Scaling (Scale Up):**
    * **What:** Increase the size of one resource (e.g., T2.micro -> T2.medium).
    * **Pro:** Simple.
    * **Con:** **Causes downtime** (requires a reboot).
* **Horizontal Scaling (Scale Out):**
    * **What:** Add *more* resources (e.g., add more T2.micro instances).
    * **How:** Uses a **Load Balancer** to distribute traffic.
    * **Con:** Must manage **session state** (use "sticky sessions").
* **Elasticity:**
    * **What:** **Automation + Horizontal Scaling**.
    * **How:** Uses services (like Auto Scaling) to automatically add/remove instances to match demand perfectly.

---
## **DOMAIN 2: Security and Compliance - Identify design principles of the AWS Cloud**
## AWS Well-Architected Framework
* **Definition:** AWS's best practices for architecting systems in the cloud.
* **Goal:** Build reliable, secure, efficient, and cost-effective systems.
* **Based on 6 Pillars:**
    1.  Operational Excellence
    2.  Security
    3.  Reliability
    4.  Performance Efficiency
    5.  Cost Optimization
    6.  Sustainability

---

### General Design Principles
* Stop guessing **capacity** (use **auto scaling**).
* Test systems at **production scale**.
* **Automate** your architecture.
* Allow for **evolutionary** changes.
* Use data to improve.
* Improve through **game days** (testing).

---

### The 6 Pillars

#### 1. Operational Excellence
* **Definition:** Ability to support development and run workloads effectively.
* **Principles:**
    * Perform **operations as code**.
    * Make frequent, small, **reversible changes**.
    * Refine operations procedures frequently.
    * **Anticipate failure**.
    * Learn from all operational failures.

#### 2. Security
* **Definition:** Ability to protect data, systems, and assets.
* **Principles:**
    * Implement a strong **identity foundation**.
    * Maintain **traceability**.
    * Apply security at **all layers**.
    * **Automate** security best practices.
    * Protect data **in transit** and **at rest**.
    * Keep people **away from data**.
    * Prepare for security events.

#### 3. Reliability
* **Definition:** Ability of a workload to perform its intended function correctly and consistently.
* **Principles:**
    * Automatically **recover from failure**.
    * **Test recovery** procedures.
    * **Scale horizontally** to increase availability.
    * Stop guessing capacity.
    * Manage change in **automation**.

#### 4. Performance Efficiency
* **Definition:** Ability to use computing resources efficiently.
* **Principles:**
    * Democratize advanced technologies.
    * Go **global in minutes**.
    * Use **serverless** architectures.
    * **Experiment** more often.
    * Consider mechanical sympathy.

#### 5. Cost Optimization
* **Definition:** Ability to run systems at the lowest price point for business value.

#### 6. Sustainability
* **Definition:** Focuses on environmental impacts (e.g., energy consumption).
* **Principles:**
    * Understand your impact.
    * Establish sustainability goals.
    * **Maximize utilization**.
    * Anticipate and adopt new, more efficient hardware and software offerings.
    * Use **managed services**.
    * Reduce the downstream impact of your cloud workloads.

---

### Other Key Concepts
* **AWS Well-Architected Tool:** A tool to review your workloads against AWS best practices.
* **Decouple:** Separate your components.
* **Parallelization:** Divide a job into simple forms and distribute the load (e.g., breaking down large datasets to be processed simultaneously).
---
## **DOMAIN 3: Cloud Technology and Services - Understand the benefits of and strategies for migration to the AWS Cloud**



## **DOMAIN 4: Billing, Pricing, and Support**

