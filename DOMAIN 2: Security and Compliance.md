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
- **Compliance** needs for locations and industries differ
- **AWS Compliance** help you understand the control in place at AWS to maintain security and data protection in AWS along with assurance program that provide templates and control mappings to help customers establish the compliance of thei environments running on AWS
- **GDPR compliant status**: General Data Protection Regulation compliant status (Trạng thái tuân thủ Quy định bảo vệ dữ liệu chung)
- **AWS Artifact:** Help to find compliance information, on-demand access to AWS security and compliance documents and reports. Compliance requirements vary from service to service.
- Understand where to find compliance information
### Compliance & Security
- Security at every layer
- Integrate security services
- Secure connections

### Key Security Services
- **AWS WAF (Web Application Firewall):** Protects web applications from common exploits.
- **Amazon GuardDuty:** **Threat detection** service (monitors for malicious activity and unauthorized behavior).
- **AWS Shield:** Managed **DDoS** (Distributed Denial of Service) protection service.
- **Others:** Amazon Inspector, AWS Security Hub.

### Encryption
- **Encryption data in Transit:** Data moving between two different places.
- **Encryption data at Rest:** Stored data.
- **Key Point:** Who enables encryption depends on the service (Shared Responsibility Model).

### Logging, Auditing, and Monitoring
- **Amazon CloudWatch:** **Monitoring** service. Collects operational data, metrics, and logs.
- **AWS CloudTrail:** **Governance and Auditing**. Logs all API activity and events ("Who did what, when?").
- **AWS Config:** **Resource Inventory**. Audits and tracks resource configuration changes.

### Scenarios & Principles
- **Scenario:** Identify which IAM user deleted an Amazon EC2 instance?
    * **Answer:** **AWS CloudTrail**.
- **Best Practice:** Create a CloudTrail **trail for multi-Regions** to track all account activity.
- **Core Principle:** **Least-Privileged Access** (only give users the minimum permissions they need).

## 2.3 Identify AWS access management capabilities 
### Fundamentals
- Why do you need to control user access?
- How to control access to your AWS account.
- What is an AWS account. 
### Access Management Concepts
- **Why:** Control who can access what.
- **Principle of Least Privilege:** Give users only the exact permissions needed for their job, and nothing more.
### AWS Account root user
- Know how to secure your account root user and tasks required of your root user acount
    + Change account setting
    + Restore IAM User permissions
    + Activate IAM access to the Billing and Management console 
    + View tax invoices
    + Close your AWS account
    + Register as a seller
    + Configure S3 with MFA
    + Edit or delete S3 bucket policies
    + Sign up for AWS GovCloud 
    + Request AWS GovCloud account root user access keys
### AWS Account & Root User
- **AWS Account:** Container for your resources; where usage is billed.
- **Root User:**
    + The initial identity created with the account.
    + Has **complete, unrestricted access**.
    + **Do NOT** use for daily tasks.
- **Root User Best Practices:**
    + Use **Multi-Factor Authentication (MFA)**.
    + Rotate access keys and password.
    + Use an **admin user** (from IAM) for daily work.
- **Root User Tasks (Examples):**
    + Change account settings.
    + Restore IAM user permissions.
    + Activate IAM access to the Billing console.

### AWS IAM (Identity and Access Management)
- **IAM Users:**
    + An identity with long-term credentials (password, access keys).
    + Can enable MFA.
    + Can enforce password policies (complexity, rotation).
- **IAM Groups:**
    + A collection of IAM users.
    + Permissions are applied to the group, not individual users.
- **IAM Roles:**
    + An identity with **temporary credentials**.
    + **Assumed** by entities (users, services, other accounts).
    + **Use Cases:**
        + Granting temporary access to users.
        + **Cross-account access**.
        + Giving AWS services permission to act on your behalf (e.g., EC2 writing to S3).
- **IAM policies:**
    + Policiy types
    + IAM Policy Simulator
- **IAM integration** with other AWS services

### Amazon Cognito
- **Cognito User Pool:** A user directory (handles sign-up/sign-in).
- **Cognito Identity Pool:** Provides **temporary AWS credentials** for users (including social media logins or unauthenticated guests).

### IAM Policies
* **Managed Policies:** Created and managed by **AWS**.
* **Unmanaged (Inline) Policies:** Created and managed by **You** (customer).
* **IAM Policy Simulator:** A tool to **test and troubleshoot** policies.

### Resource-Based Policies (Example: S3)
* **Bucket Policy (S3):**
    * A **resource-based policy** attached directly to the S3 bucket.
    * Grants permission to other AWS accounts or IAM users.
* **User Policy:**
    * An **identity-based policy** attached to an IAM user/role to grant them access to S3.
* **MFA Delete:**
    * Prevents accidental object deletion.
    * Requires a user to authenticate with MFA to delete an object.
    * Requires **Versioning** to be enabled first.
## 2.4 Indentify components and resources for security
