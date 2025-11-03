# **CERTIFICATE CLOUD PRACTITIONER**
## **DOMAIN 1: Cloud Concepts**
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
## **DOMAIN 2: Security and Compliance**
## **DOMAIN 3: Cloud Technology and Services**
## **DOMAIN 4: Billing, Pricing, and Support**

