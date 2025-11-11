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

---
## **3.3 Identify AWS compute resources**
---

### Amazon EC2 (Elastic Compute Cloud)
* **Definition:** Virtualization as a Service (IaaS).
* **Architecture:**
    * **EC2 Instances:** Virtual machines.
    * **EC2 Hosts:** Physical servers (managed by AWS).
    * **Shared Hosts:** Default. Shared hardware, but instances are isolated.
    * **Dedicated Hosts:** Pay for the entire physical host.
* **Resilience:** **Availability Zone resilient**. (Fails if the AZ fails).

### EC2 Storage
* **Instance Store:**
    * **Temporary** storage physically attached to the host.
    * Data is **lost** if the instance stops, terminates, or moves.
* **EBS (Elastic Block Store):**
    * **Persistent** network-attached storage.
    * **Resilience:** Availability Zone resilient (EBS volume and EC2 instance must be in the same AZ).

### EC2 Instance Types (Categories)
* **General Purpose:** Balanced CPU, memory, storage (default).
* **Compute Optimized:** High-performance CPU (media, ML, gaming).
* **Memory Optimized:** Large datasets in memory (databases).
* **Accelerated Computing:** Hardware accelerators (GPUs, FPGAs).
* **Storage Optimized:** High I/O, data warehousing.
* **Burstable Instances:** Low baseline CPU with "burst credits" for spikes.

### EC2 Configuration
* **AMI (Amazon Machine Image):**
    * Template for launching an instance.
    * **Golden AMI:** A custom, pre-configured AMI (e.g., with security patches, software).
* **Instance Metadata:**
    * **Data *about* your instance** (Instance ID, IP address, etc.).
    * Accessed via: `http://169.254.169.254/latest/meta-data`
* **Instance User Data:**
    * Scripts run *after* the instance starts (for automated configuration).

### Containers
* **Concept:** Runs as a process *within* the host OS (shares the OS).
* **vs. EC2:** Containers are more lightweight (no guest OS) than EC2 instances (full VM).
* **Services:**
    * **ECS (Elastic Container Service):** AWS-managed container orchestration.
    * **EKS (Elastic Kubernetes Service):** AWS-managed Kubernetes.

### Serverless Compute
* **AWS Lambda (FaaS - Function as a Service):**
    * Run small pieces of code (functions) without managing servers.
    * **Event-driven** (e.g., triggers on an S3 upload).
    * Billed for execution duration.

### High Availability & Scalability
* **Auto Scaling Groups:**
    * Automatically adds (scales out) or removes (scales in) EC2 instances to meet demand.
    * Provides **elasticity**.
* **ELB (Elastic Load Balancing):**
    * Distributes incoming traffic across multiple instances/AZs.
    * **Types:** Classic (CLB), Application (ALB), Network (NLB), Gateway (GWLB).
    * **HA:** Places a node in each AZ it serves.

---
## **3.4 Identify AWS compute resources**
---

### Amazon RDS (Relational Database Service)
* **What:** Managed database service (Database as a Service).
* **Engines:** MySQL, MariaDB, PostgreSQL, Oracle, Microsoft SQL Server, Aurora.
* **Storage:** Dedicated storage per instance.
* **Single-AZ:** Instance and storage in one AZ (vulnerable to failure).
* **Multi-AZ:**
    * **Standby replica** in a different AZ.
    * **Synchronous Replication** (high availability).
* **Read Replicas:**
    * Read-only copy for performance.
    * **Asynchronous Replication**.

### Amazon Aurora
* **What:** Managed database compatible with MySQL & PostgreSQL.
* **Architecture:** **Cluster** (1 primary, 0+ read replicas).
* **Storage:** **Shared cluster volume** (faster, more available).
* **Aurora Serverless:**
    * No instances to manage.
    * Scales using **ACUs** (Aurora Capacity Units).
    * Can pause (go to 0 ACUs) to save cost (pay only for storage).
* **Global Databases:**
    * Replicates data globally (< 1 second) across Regions.
    * Used for Disaster Recovery (DR) and low-latency global reads.

### Amazon DynamoDB
* **What:** Managed **NoSQL** database (key-value, document).
* **Service Type:** **Public service**.
* **Scaling:**
    * **Provisioned Capacity:** You set read/write capacity.
    * **On-Demand:** AWS handles scaling for you.
* **Resilience:** Highly resilient (multi-AZ) by default; **Global Tables** for cross-Region.

### In-Memory Databases
* **Amazon ElastiCache:**
    * **What:** Managed in-memory cache.
    * **Engines:** **Redis**, **memcacheD**.
    * **Use Cases:** Improve read performance, store user **session states**.
* **Amazon DynamoDB Accelerator (DAX):**
    * **What:** In-memory cache **specifically for DynamoDB**.
    * **Speed:** **Microsecond** latency (vs. millisecond for DynamoDB).
    * **Reads:** **Eventually consistent** (not strongly consistent).

### Amazon Redshift
* **What:** Petabyte-scale **data warehouse**.
* **Type:** **OLAP** (Online Analytical Processing).
* **Storage:** **Column-based** (good for analytic queries).
* **NOT for:** OLTP (Online Transaction Processing).
* **Redshift Spectrum:** Query data directly in **Amazon S3**.

### Database Migration
* **AWS Snow Family (Physical Devices):**
    * **Snowcone:** ~8 TB.
    * **Snowball Edge:** Terabytes to Petabytes (has **Storage** and **Compute** options).
    * **Snowmobile:** Petabytes to Exabytes (shipping container).
* **AWS DMS (Database Migration Service):**
    * **What:** Managed service to migrate databases (replicates data).
    * **Downtime:** Very low.
    * **Schema Conversion Tool (SCT):** Helps move between *different* database engines.
* **AWS DataSync:**
    * **What:** Fast, **online data transfer**.
    * **Use:** Moves data from on-premises to S3, EFS, or FSx.

---
## **3.5 Identify AWS network resources**
---

### Amazon VPC (Virtual Private Cloud)
* **What:** Your own **private data center** in the cloud.
* **Control:** You choose IP ranges, create **subnets**, configure **route tables**.
* **Resilience:** A **Regional service** (spans multiple AZs).

### VPC Types
* **Default VPC:**
    * Created by AWS in each Region.
    * **Public by default**.
    * Has a default subnet in each AZ.
* **Custom VPC:**
    * You create and configure.
    * **Private by default**.

### VPC Core Components
* **Subnets:**
    * A sub-section of a VPC's IP range.
    * **Tied to a single Availability Zone (AZ)**.
* **VPC Router:**
    * AWS-managed router that routes traffic *between* subnets.
* **Route Tables:**
    * Control where the VPC router sends traffic.
    * You associate a route table with a subnet.

### VPC Security
* **Network ACLs (NACLs):**
    * **Subnet** level firewall.
    * **Stateless:** Must create separate inbound *and* outbound rules.
    * Supports **Allow** and **Deny** rules.
* **Security Groups (SGs):**
    * **Resource** level (EC2, RDS) firewall.
    * **Stateful:** If traffic is allowed in, it's automatically allowed out.
    * Supports **Allow** rules only (implicit deny).

### VPC Gateways
* **Internet Gateway (IGW):**
    * Regional, highly available.
    * Allows **public subnets** to access the internet.
    * Performs 1:1 Static **NAT** (maps private IP to public IP).
* **NAT Gateway:**
    * **Network Address Translation**.
    * Allows instances in **private subnets** to access the internet (e.g., for software updates).
    * **Prevents** the internet from initiating connections *in*.

### VPC & Hybrid Connectivity
* **VPC Peering:**
    * Links two VPCs (same or different accounts/regions) to communicate using private IPs.
* **VPC Endpoints:**
    * Connects your VPC to AWS public services (like S3, DynamoDB) *privately*, without an IGW or NAT Gateway.
    * **Gateway Endpoint:** For S3 & DynamoDB.
    * **Interface Endpoint (AWS PrivateLink):** For most other services; uses an ENI.
* **AWS VPN:**
    * A **virtual, encrypted** connection over the **public internet**.
* **AWS Direct Connect:**
    * A **dedicated, physical** fiber connection (not over the internet).

### DNS & Routing
* **Amazon Route 53:**
    * **Globally resilient** managed **DNS** service.
    * Use for: Domain registration, hosting zones (translating names to IPs).
    * Provides routing policies (failover, weighted, latency).
* **Edge Services:**
    * **CloudFront:** Caches content.
    * **Global Accelerator:** Improves TCP/UDP performance (non-cached).

---
## **3.6 Identify AWS storage resources**
---

### Cloud Storage Types
* **Object Storage:** Stores data as objects (e.g., **Amazon S3**).
* **File Storage:** Stores data in a file system hierarchy (e.g., **Amazon EFS**, **Amazon FSx**).
* **Block Storage:** Stores data as blocks (e.g., **Amazon EBS**).

### Object Storage: Amazon S3
* **What:** Global, public, object storage service.
* **Buckets:** Containers for objects; must have a **globally unique name**.
* **Objects:** Files (0 bytes - 5 TB).
* **Key Feature: S3 Versioning:**
    * Keeps multiple versions of an object.
    * Protects against accidental overwrites or deletes.
* **Storage Classes (Example):**
    * **S3 Glacier Deep Archive:** Lowest cost, long-term archive, retrieval within 12 hours.

### File Storage: EFS vs. FSx
* **Amazon EFS (Elastic File System):**
    * Keyword: **Linux**.
    * Managed, shared file system for **Linux** EC2 instances.
* **Amazon FSx for Windows File Server:**
    * Keyword: **Windows**.
    * Managed, shared file system for **Windows** (supports SMB, NTFS).
* **Amazon FSx for Lustre:**
    * Keywords: **Linux + Cluster**.
    * For **High-Performance Computing (HPC)**, ML, and video processing.

### Block Storage: EBS vs. Instance Store
* **Instance Store:**
    * **Ephemeral** (temporary) storage, physically attached to the host.
    * Fast, but **data is lost** if the EC2 instance stops or fails.
* **EBS (Elastic Block Store):**
    * **Persistent** network-attached storage (like a virtual hard drive).
    * Resilient; data is separate from the EC2 host.
    * Can be a **boot volume**.

### EBS Volume Types
* **General Purpose SSD (gp2/gp3):**
    * Recommended for most workloads.
    * **Can** be a boot volume.
* **Provisioned IOPS SSD (io1/io2):**
    * Critical apps, large databases (sustained IOPS).
* **Throughput Optimized HDD (st1):**
    * Streaming, big data.
    * **Cannot** be a boot volume.
* **Cold HDD (sc1):**
    * Infrequently accessed, lowest cost.
    * **Cannot** be a boot volume.
* **EBS Snapshots:** Point-in-time backups of EBS volumes.

### Hybrid Storage: AWS Storage Gateway
* **What:** Connects on-premises storage to AWS.
* **File Gateway:** Stores files as S3 objects; provides a local cache.
* **Volume Gateway (iSCSI):**
    * **Gateway Stored:** Full data on-premises, backups (snapshots) to S3.
    * **Gateway Cached:** Primary data in S3, hot data cached on-premises.
* **Virtual Tape Library (VTL) Gateway:** Replaces physical tapes (backup to S3/Glacier).

### Backup
* **Amazon S3:** Low-cost, durable storage for backups (use **Lifecycle Management**).
* **AWS Backup:** Centralized, automated service to manage backups across AWS.


---
## **3.7 Identify AWS storage resources**
---
