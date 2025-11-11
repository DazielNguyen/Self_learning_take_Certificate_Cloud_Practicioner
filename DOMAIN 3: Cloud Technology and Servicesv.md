# **CERTIFICATE CLOUD PRACTITIONER**
## **DOMAIN 3: Cloud Technology and Services**
---
## **3.1 Define methods of deploying and operating in the AWS Cloud**

### Methods of Deploying & Operating
* **AWS Management Console:** Graphical interface (GUI).
* **AWS CLI (Command Line Interface):** API access via commands.
* **SDKs (Software Development Kits):** Programmatic API access (in code).
* **IaC (Infrastructure as Code):** Deploy via code (e.g., **CloudFormation**).

### Deployment Models
* **Cloud Native:** Fully in AWS.
* **Hybrid Environment:** Connects **on-premises data center** with AWS.

### Cloud Types
* **Public Cloud:** Available to the public (e.g., AWS, Azure, Google).
* **Multi-Cloud:** Using **more than one** public cloud.
* **Private Cloud:** Dedicated services (on-premises) meeting cloud criteria (e.g., **AWS Outposts**).
* **Hybrid Cloud:** Using **Public Cloud** + **Private Cloud** together.

### AWS Public vs. Private Services
* **Public Service:**
    * **Network:** Sits in the **AWS Public Zone**.
    * **Access:** Connects from the public internet.
    * **Example:** **Amazon S3**.
* **Private Service:**
    * **Network:** Sits in the **AWS Private Zone** (e.g., **Amazon VPC**).
    * **Access:** Isolated by default; no direct internet connection.
    * **Example:** **Amazon EC2** (by default).

### Connectivity Options
* **Public Internet:** Standard way to connect.
* **VPN (Virtual Private Network):** Secure connection over the internet.
* **AWS Direct Connect:** **Private, dedicated connection** to AWS.
* **Internet Gateway:** Allows communication between instances in a VPC and the public internet.

--- 
## **3.2 Define the AWS global infrastructure**
---

### Service Resilience
* **Globally Resilient:** Replicates across Regions. Region can fail, service is OK.
    * *Examples:* IAM, CloudFront, Route 53.
* **Regionally Resilient:** Replicates across AZs (in one Region). AZ can fail, service is OK.
    * *Examples:* EFS, AWS Batch.
* **Zonal Resilient:** Runs in a *single* AZ. AZ fails, service fails.
    * *Examples:* EBS, EC2.

### AWS Global Infrastructure
* **Region:**
    * A geographical area with **2+ Availability Zones**.
    * Data stays in the Region (unless you move it).
    * *Selection Criteria:* **Compliance** and **Latency** (proximity to users).
* **Availability Zone (AZ):**
    * **One or more** discrete data centers (isolated power, networking).
    * Connected via high-speed, redundant networking.
    * *Use Case:* **High Availability** (distribute resources across AZs).
* **Edge Location:**
    * Global endpoint for **caching content**.
    * Used by the CDN (Content Delivery Network).

### Region Extensions
* **Local Zones:** Extension of a Region, close to users.
* **AWS Wavelength:** Extension of a Region at a **carrier location** (for mobile/5G ultra-low latency).

### Edge Services: CloudFront vs. Global Accelerator
* **Both:** Use the AWS Global Network and Edge Locations; integrate with AWS Shield (DDoS).
* **Amazon CloudFront (CDN):**
    * **Caches** content (static & dynamic).
    * Serves content *from* the edge.
* **AWS Global Accelerator:**
    * **No caching**.
    * Improves **TCP/UDP** performance (proxies packets).
    * Provides a **static IP** and fast regional failover.

### Key Concepts
* **Availability Zones (AZs) = High Availability (HA)**.
* **Regions = Disaster Recovery (DR) & Compliance**.