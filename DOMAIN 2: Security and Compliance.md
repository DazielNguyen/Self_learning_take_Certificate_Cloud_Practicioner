# **CERTIFICATE CLOUD PRACTITIONER**
## **DOMAIN 2: Security and Compliance**
## 2.1 Understand the AWS shared responsibility model
## AWS Shared Responsibility Model

![orca-blog-what-is-shared-responsibility-model-image-2]()

- **AWS Responsibility:** Security **OF** the Cloud.
- **Customer Responsibility:** Security **IN** the Cloud.

### AWS is Responsible FOR:
- **Hardware / Global Infrastructure:** Regions, Availability Zones (AZs), Edge Locations.
- **Foundation Services:** Compute, Storage, Networking, Databases.
- **Software:** The hypervisor and software that runs the core services.
- **Example:** AWS is responsible for securing the physical **data centers**.

### Customer is Responsible IN:
- **Customer Data** (including backups).
- **Identity and Access Management (IAM)**.
- **Operating System (OS)**, Network, and Firewall configurations.
- Applications.
- Client-side data **encryption**.
- Server-side data **encryption**.
- Network traffic protection (e.g., SSL).

### Responsibility SHIFTS Based on Service
- The level of customer responsibility **changes** depending on the service.

#### Example: Database Patching
- **Unmanaged Service (e.g., Amazon EC2):**
    + The **Customer** is responsible for patching the OS and the database engine.
- **Managed Service (e.g., Amazon RDS):**
    + **AWS** is responsible for patching the OS and the database engine.
    + The Customer is still responsible for managing their data and access (IAM).

## 2.2 Understand AWS Cloud security, gorvernance, and compliance concepts
## AWS Security, Governance, and Compliance
### Understand
- Compliance needs for locations and industries differ
- AWS Compliance help you understand the control 
- AWS Artifact
- Understand where to find compliance information
### AWS Compliance
- **AWS Artifact:** On-demand access to AWS security and compliance reports (e.g., GDPR, ISO).
- **Key Point:** Compliance requirements vary from service to service.

### Key Security Services
* **AWS WAF (Web Application Firewall):** Protects web applications from common exploits.
* **Amazon GuardDuty:** **Threat detection** service (monitors for malicious activity and unauthorized behavior).
* **AWS Shield:** Managed **DDoS** (Distributed Denial of Service) protection service.
* **Others:** Amazon Inspector, AWS Security Hub.

### Encryption
* **Data in Transit:** Data moving between two different places.
* **Data at Rest:** Stored data.
* **Key Point:** Who enables encryption depends on the service (Shared Responsibility Model).

### Logging, Auditing, and Monitoring
* **Amazon CloudWatch:** **Monitoring** service. Collects operational data, metrics, and logs.
* **AWS CloudTrail:** **Governance and Auditing**. Logs all API activity and events ("Who did what, when?").
* **AWS Config:** **Resource Inventory**. Audits and tracks resource configuration changes.

### Scenarios & Principles
* **Scenario:** Identify which IAM user deleted an Amazon EC2 instance?
    * **Answer:** **AWS CloudTrail**.
* **Best Practice:** Create a CloudTrail **trail for multi-Regions** to track all account activity.
* **Core Principle:** **Least-Privileged Access** (only give users the minimum permissions they need).


## 2.3 Identify AWS access management capabilities 

## 2.4 Indentify components and resources for security
