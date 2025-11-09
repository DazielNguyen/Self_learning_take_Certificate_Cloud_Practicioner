# **CERTIFICATE CLOUD PRACTITIONER**
## **DOMAIN 1: Cloud Concepts - Define the benefits of the AWS Cloud**
## 1.1 Define the benefits of the AWS Cloud 
### What is AWS?
* **Definition:** World's most comprehensive cloud; 200+ services.
* **Value:** Lower costs, become more agile, innovate faster.

---

### 5 Criteria of Cloud Computing
1.  **On-Demand Self-Service:** Provision resources (servers, databases) without human interaction (via console, CLI, API).
2.  **Network Connectivity:** Access resources over the network (HTTP, VPN, SSH).
3.  **Resource Pooling:** AWS shares large pools of resources (servers, storage) among multiple customers.
    * This enables **Economies of Scale** (AWS buys in bulk, passes savings to you).
4.  **Elasticity:** Scale resources up or down to match demand.
5.  **Measured Service:** Monitor, control, and pay for only the resources you use.

---

### AWS Global Infrastructure
* **Core Components:** Regions, Availability Zones (AZs), Edge Locations.
* **Purpose:** Allows you to build resilient and **highly available** systems.

---

### Availability vs. Tolerance vs. Recovery
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

### Scaling vs. Elasticity
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
## **1.2 Identify design principles of the AWS Cloud**
### AWS Well-Architected Framework
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
## **1.3 Understand the benefits of and strategies for migration to the AWS Cloud**
### AWS Cloud Adoption Framework (CAF)
* **What:** Comprehensive approach for successful cloud transformation.
* **Purpose:** Provides best practices; improves cloud readiness.
* **6 Perspectives:**
    * Business
    * People
    * Governance
    * Platforms
    * Security
    * Operations
* **Benefits:** 
    + Reduce business risk through imporved reliability, increase performance, and enhance security. 
    + Increase operational efficiency by reducing costs and increase productivity 
    + Can grow by creating new productsa and services to reach new customers or new markets. 
    + Improve performance by improving your sustainability and transparency

---

### Cloud Adoption Stages
1.  **Project:** Evaluating AWS for specific needs.
2.  **Foundation:** Moving first applications; building a landing zone.
3.  **Migration:** Defining roles; establishing a Cloud Center of Excellence (CCOE).
4.  **Reinvention:** All new projects start in AWS.

---

### 7 Migration Strategies (The 7 R's)
* **Retire:** Decommission applications.
* **Retain:** Keep applications in the source environment.
* **Rehost (Lift and Shift):** Migrate without changes.
* **Relocate:** Move a large number of servers.
* **Repurchase (Drop and Shop):** Move to a different product (e.g., SaaS).
* **Replatform (Lift, Tinker, and Shift):** Migrate with some cloud optimizations.
* **Refactor / Re-architect:** Rebuild the application for cloud-native features.

---

### Migration Services & Scenarios

#### Scenario 1: Financial App (Low Latency, Changing Data)
* **Good Choices:**
    * **Amazon EFS** (Elastic File System): Scalable file storage for EC2.
    * **Amazon RDS** (Relational Database Service): Managed relational database.
* **Bad Choices:**
    * **Amazon S3:** Higher latency (public zone).
    * **AWS Snowball Edge:** For large, bulk data migration, not live access.

#### Scenario 2: NoSQL Database (Scalable, Fast, Reliable)
* **Answer:** **Amazon DynamoDB**.
* **Keywords:** NoSQL, non-relational, key-value, document database (JSON).

* **Answer:** **Amazon RDS**.
* **Keywords:** Just as relational

#### Scenario 3: Microsoft SQL Server (Cost-Optimized, Standard License)
* **Answer:** Launch an **EC2 instance** using a **Windows Server AMI** bundled with **SQL Server Standard**.
* **Reason:** You do not need to buy/manage your own license.
* **Why Not RDS?** More expensive (it's a managed service).
* **Why Not Aurora?** Only supports MySQL and PostgreSQL.

---

### Data Backups
* **Service:** **Amazon S3 Glacier** storage classes.
* **Use:** Lowest-cost for archiving large data.
* **Consider:** Retrieval fees and retrieval times.

---
## **1.4 Billing, Pricing, and Support**

### Cloud Economics
* Shifts technical resources **away from on-premises** infrastructure management (servers, cooling, data centers).
* Adopts a **consumption model** (pay only for what you consume).
* Uses AWS **economies of scale** for lower costs.
* **Benefit:** Frees up technical resources to focus on other activities (optimizing resource utilization, creating more efficient applications, developing better end-user experience, and more areas that will help your organization streamline operations and generatin more revenue).

---

### Total Cost of Ownership (TCO)
* **Key Concept:** Migrating to AWS trades **Capital Expenses (CapEx)** for **variable expenses (OpEx)**.

* **Four Parts of TCO:**
    1.  **Capital Expenses (CapEx):** Long-term purchases (buildings, servers, power backups).
    2.  **Operational Expenses (OpEx):** Day-to-day operating costs (utilities, server maintenance).
    3.  **Labor Costs:** Staffing for on-premises data centers (technicians).
    4.  **Software Licensing:** How existing licenses are affected by the move.

---

### How to Reduce Costs
* Stop provisioning for **peak demand**; use benchmarking and testing.
* Use **automation**.
* Scale **horizontally** to meet demand (instead of running at peak capacity 24/7).
* Use **AWS Managed Services** (reduces cost of ownership and technical workload).
* **Right-sizing** resources.
* Data segmentation (reduces compliance scope and audit time).

---
## Domain 1
### Bonus Question & Some Keyword to Remember


- **AWS DMS (Database Migration Service)** is used to transpose relational databases from one location to another. Can use AWS DMS to migrate between sources, including between on premises and the cloud. However, AWS DMS does not actually transport the data.

- **AWS Snowball Edge** is a device that can migrate petabyte-scale datasets at fast speed. Snowball Edge devices also have onboard compute capabilities. You can use Snowball Edge to migrate petabyte-scale datasets from on-premises to AWS in a cost-effective way.

- **AWS Migration Hub** is used to plan and track the progress of migrations. Migration Hub is not used for the actual data migration.

- **AWS SCT (Schema Conversion Tool)** is used to convert existing database schemas from one database engine to a different database engine. The AWS SCT is not used to migrate petabyte-scale datasets into AWS.

- **AWS Well-Architected Framework:** The **Well-Architected Framework** helps cloud architects to **build secure, efficient, high-performing, and resilient infrastructures** on AWS. The Well-Architected Framework is **primarily focused** on the **technical point of view**, rather than a combination of technical and business points of view.

- **AWS Control Tower** would help the company set up and govern an AWS multi-account environment that follows AWS best practices. However, AWS Control Tower does not provide guidance on moving to the AWS Cloud.

- **AWS CAF (Cloud Adoption Framework)** identifies capabilities in six perspectives that support successful transitions to the AWS Cloud. The six perspectives include business, people, governance, platform, security, and operations.

- **AWS Trusted Advisor:** Trusted Advisor inspects an AWS environment and makes recommendations about improvements and changes that can be made. The recommendations can help to increase security, reduce costs, and improve system performance and availability. However, Trusted Advisor does not provide guidance on how to move to the AWS Cloud.

- **AWS AppSync** is a fully managed GraphQL service that is used to connect applications to data sources. AWS AppSync is not for architectural advice.

- **AWS DataSync**: Can use DataSync to move data. However, DataSync does not provide the database schema management that is required in the scenario.

- **AWS AppConfig** gives you the ability to create, manage, and quickly deploy application configurations. AWS AppConfig does not assist with best practices in architecture design.

- **AWS WA Tool (Well-Architected Tool)** is used to improve your architecture using AWS best practices. The AWS WA Tool can provide guidance on architecture design for a new application.

- **Amazon Inspector**: You can use Amazon Inspector to scan workloads for software vulnerabilities and unintended network exposure. Amazon Inspector does not provide guidance on architecture design.

- **Amazon S3 File Gateway** connects on-premises software appliances to AWS Cloud storage so that you can store and retrieve objects in Amazon S3.

- **AWS Direct Connect** is a network connection from your on-premises data center to the cloud. You can use Direct Connect to move data. However, Direct Connect does not provide the database schema management that is required in the scenario.

- **AWS offers pay-as-you-go pricing** for more than 200 cloud services. Pay-as-you-go pricing requires no upfront payments, and you only pay for what you use.

- **Reserved Instance** pricing is available with no upfront payments. However, the pricing is a fixed model based on the reserved capacity. Reserved Instance pricing is not variable based on usage.

- **Rightsize Instances:** To rightsize might reduce costs. However, this solution does not address the requirement for no upfront payments.

- **Operational Excellence**: The principle to perform operations as code is a design principle of the operational excellence pillar. By performing operations as code, you limit human error and enable consistent responses to events.

- **Elasticicty:** The AWS Cloud gives you the ability to stop planning capacity and let it automatically scale up when needed and scale down as demand goes down. This elasticity could stop you from having underutilized resources.

- **Loose coupling**: Loose coupling, or decoupling, refers to the design principle of separating resources in the design architecture. Decoupling your architecture prevents your entire system from failing if one component fails.

- **Anticipate failure**: Anticipate failure is a principle of the operational excellence pillar of the Well-Architected Framework. To anticipate failure, you can perform test exercises to **identify potential sources of failure**.

---
### Flashcard
> What are the 5 criteria of cloud computing?

**On-demand self-service, network connectivity, resource pooling, elasticity, and that resource usage must be monitored and billed.**

> What is high availability? 

**High availability is a way to design your systems to have the ability to keep your systems up and running and providing service as often as possible.**

> What is fault tolerance? 

**Fault tolerance is the actual ability of a system to keep operating in the event of a failure.**

> What are the two ways to scale? 

**Vertically and horizontally.**

> What type of scaling is adding more instances of the same size? 

**Horizontal**.

> What type of scaling is adding a larger instance size? 

**Vertical.**

> What are the 6 pillars of the AWS Well-Architected Framework? 

**Operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability.**

> What are the 7 migration strategies? 

- **Retire** is for applications that you want to decommission or retire.
- **Retain** is for applications that you want to keep in the source environment or applications that are not ready to be migrated.
- **Rehost**, also known as lift and shift, is for applications to be migrated without making any changes to the application.
- **Relocate** is for a large number of servers that are made up of one or more applications.
Repurchase, also known as drop-and-shop, is for applications with a different version or product and provides more value than the existing infrastructure.
- **Replatform**, also known as lift, tinker, and shift, is for applications that need some level of optimization in order to operate efficiently or to take advantage of AWS capabilities.
- **Refactor** or **re-architect** is for applications that you want to migrate to AWS and take full advantage of the cloud-native features to improve agility, performance, and scalability.

> What are the four parts of total cost of ownership (TCO) in AWS for this exam? 

- **Operational expenses (OpEx)** are your day-to-day operating costs such as utilities, printer toner, coffee, and snacks. 
- **Capital Expenses (CapEx)** are the costs associated with creating the long-term benefits such as purchasing a building, servers, printers, storage, and backups. CapEx items are generally purchased once, and are expected to be used by your organization for years.
- **Labor costs** are the costs assocaited with staffing an on-premises environment or data center such as the network operation center technicians, who are responsbile for installation, configuration, troubleshooting, and management of your servers and infrastructure.
- **Software licensing costs** are the cost and the impact of migrating software licensing costs to AWS.

> When you migrate from an on-premises environment and traditional servers to AWS, are you trading capital expenses for variable expenses? 

**Yes.**