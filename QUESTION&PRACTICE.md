## **Bonus Question & Some Keyword to Remember**
### **Domain 1**
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

### **Domain 2**
- **Network ACLs** 
    + Used to allow or deny specific traffic to a VPC at the subnet level. Network ACLs operate at the subnet level and meet the requirements to add a layer of security that acts as a firewall.
    + A company wants to add a virtual firewall to an Amazon VPC -> wants all instances inside a specific subnet to be automatically covered under this firewall.
    + A cloud practitioner wants to explicitly deny network traffic to a subnet inside of an Amazon VPC.


- **GuardDuty** 
    + Provides continuous **monitoring and threat detection** services. 
    + GuardDuty uses **threat intelligence feeds and machine learning** to identify unauthorized and malicious activity within your AWS environment. You can use GuardDuty to **identify compromised** instances and accounts.
- **Amazon Macie**
    + Provides **data security** by **using machine learning** to **discover, monitor, and provide automated protection of sensitive data** that is stored in **Amazon S3**.

- **The customer's responsibility** 
    + The customer's responsibility for AWS Lambda -> Encrypption of the application data at rest
    + Configure IAM user for least-privilege access
    + Determine which services hace access to an Amazon DynamoDB table
    + The customer responsible for updating and patching -> Amazon WorkSpaces virtual Windows desktop
- **AWS CloudTrail** 
    + Helps to **provide governance, compliance,** and **operational risk auditing** of your AWS account. 
    + Actions taken by a user, role, or an AWS service are recorded as events in CloudTrail. 
    + Events include actions taken in the AWS Management Console, AWS Command Line Interface (AWS CLI), and AWS SDKs and APIs.
    + **Service provides risk auditing by continuously monitoring and logging API requests** to resources in an account -> user actions in the AWS Management Console and AWS SDKs 

- **AWS responsible**
    + AWS responsible for in the AWS shared responsibility model for **security and compliance** -> Updating Amazon EC2 hardware

- **AWS Artifact** 
    + A web service that allows you to download AWS security and compliance documents such as ISO certifications and SOC reports.
    + During a compliance review, one of the auditors **requires a copy of the AWS SOC 2 report.**

- **AWS CloudTrail** 
    + Can use CloudTrail to log actions taken in a production account, such as actions taken in the AWS Management Console, AWS CLI, and AWS SDKs.
    + A company has a new requirement to log actions taken in a production account.

- **AWS IAM Identity Center** 
    + Provides you with the ability to** manage sign-in securit**y for your workforce users. 
    + IAM Identity Center can be used for **SSO integration** to access the AWS Management Console.
    + Service should someone use to turn on single sign-on (SSO) to the AWS Management Console

- **AWS Organizations** 
    + Offers an API to create and manage AWS accounts. 
    + Organizations can control permissions that are available to accounts and can consolidate billing.
    + **Provides a quick and automated** way to **create and manage** AWS accounts

- **AWS Trusted Advisor** 
    + Draws upon best practices learned from serving hundreds of thousands of AWS customers. These best practices include security checks.
- **Data encryption**
    + Many AWS services support data encryption, including Amazon Elastic Block Store (Amazon EBS) and Amazon S3. Encryption adds another layer of security to your data.






---
## **Flashcard**
### **Domain 1**
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

### **Domain 2**
> You are hosting a MySQL database on Amazon RDS. Are you responsible for patching the database engine on an Amazon RDS database instance or is AWS responsible for this security patching? 

**AWS is responsible for patching on Amazon RDS.**

> You have a database running on Amazon EC2? Who would be responsible for patching of the Amazon EC2 instance? 

**You are responsible for the patching of your Amazon EC2 instance.**

> Where can you find information about compliance on AWS? 

**AWS compliance programs such as AWS Artifact, the Security Center, and the AWS Knowledge Center.**

> What AWS service helps to identify an IAM user who deleted an Amazon EC2 instance in your production environment? 

**AWS CloudTrail is a service for governance, compliance, operational auditing, and risk auditing of your AWS account that continuously monitors, and retains account activity related to actions across your AWS infrastructure.**

> What are some actions you can perform as the account root user of your AWS account? 

**As the account root user, you can change your account settings, restore IAM user permissions, activate access to the AWS Billing and Cost Management console, register as a seller, configure an S3 bucket to enable multi-factor authentication, close your AWS account, and more.**

> What identity in AWS has associated usernames and passwords? 

**IAM users.**

> What AWS service would you choose if you need to create rules to filter web traffic based on conditions such as IP addresses, HTTP headers, or custom URLs? 

**AWS WAF helps to control traffic with rules that you define that block common attack patterns such as SQL injections or cross-site scripting.** 

> Can you conduct security assessments and penetration testing without prior approval against your AWS resources? 

**Yes, but only for certain services.**