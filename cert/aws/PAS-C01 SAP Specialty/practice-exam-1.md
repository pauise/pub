# Practice Exam 1

Click on the **Answer** button for the correct answer and its explanation.

If this practice exam has been helpful to you please share it with others and react to this below.

---

## Question 1
A global enterprise is running SAP ERP Central Component (SAP ECC) workloads on Oracle in an on-premises environment. The enterprise plans to migrate to SAP S/4HANA on AWS.
The enterprise recently acquired two other companies. One of the acquired companies is running SAP ECC on Oracle as its ERP system. The other acquired company is running an ERP system that is not from SAP. The enterprise wants to consolidate the three ERP systems into one ERP system on SAP S/4HANA on AWS. Not all the data from the acquired companies needs to be migrated to the final ERP system. The enterprise needs to complete this migration with a solution that minimizes cost and maximizes operational efficiency.
Which solution will meet these requirements?
 - A. Perform a lift-and-shift migration of all the systems to AWS. Migrate the ERP system that is not from SAP to SAP ECC. Convert all three systems to SAP S/4HANA by using SAP Software Update Manager (SUM) Database Migration Option (DMO). Consolidate all three SAP S/4HANA systems into a final SAP S/4HANA system. Decommission the other systems.
 - B. Perform a lift-and-shift migration of all the systems to AWS. Migrate the enterprise's initial system to SAP HANA, and then perform a conversion to SAP S/4HANA. Consolidate the two systems from the acquired companies with this SAP S/4HANA system by using the Selective Data Transition approach with SAP Data Management and Landscape Transformation (DMLT).
 - C. Use SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move to re-architect the enterprise’s initial system to SAP S/4HANA and to change the platform to AWS. Consolidate the two systems from the acquired companies with this SAP S/4HANA system by using the Selective Data Transition approach with SAP Data Management and Landscape Transformation (DMLT).
 - D. Use SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move to re-architect all the systems to SAP S/4HANA and to change the platform to AWS. Consolidate all three SAP S/4HANA systems into a final SAP S/4HANA system. Decommission the other systems.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C
 
> This option minimizes cost and maximizes operational efficiency by using the DMO with System Move to migrate the initial system to SAP S/4HANA on AWS. The Selective Data Transition approach with DMLT allows for the consolidation of the two acquired companies' systems with the new SAP S/4HANA system, enabling the migration of only necessary data and reducing overall complexity.
A and D are wrong as one of the system is non-sap.
B gives the expected end result but C is more cost effective and efficient approach.
</details> 

## Question 2
A global retail company is running its SAP landscape on AWS. Recently, the company made changes to its SAP Web Dispatcher architecture. The company added an additional SAP Web Dispatcher for high availability with an Application Load Balancer (ALB) to balance the load between the two SAP Web Dispatchers.
When users try to access SAP through the ALB, the system is reachable. However, the SAP backend system is showing an error message. An investigation reveals that the issue is related to SAP session handling and distribution of requests. The company confirmed that the system was working as expected with one SAP Web Dispatcher. The company replicated the configuration of that SAP Web Dispatcher to the new SAP Web Dispatcher.
How can the company resolve the error?
 - A. Maintain persistence by using session cookies. Enable session stickiness (session affinity) on the SAP Web Dispatchers by setting the wdisp/HTTP/esid_support parameter to True.
 - B. Maintain persistence by using session cookies. Enable session stickiness (session affinity) on the ALB.
 - C. Turn on host-based routing on the ALB to route traffic between the SAP Web Dispatchers.
 - D. Turn on URL-based routing on the ALB to route traffic to the application based on URL.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B
 
> Must be B, the setting on webdispatcher affects how requests are distributed among the application servers - if the issue wasn't existing before, it must be connected to the multiple dispatchers setup. We must to make sure that once the user is connected to given dispatcher, it will remain so. B is the best answer then.
</details> 

## Question 3
A company hosts its SAP NetWeaver workload on SAP HANA in the AWS Cloud. The SAP NetWeaver application is protected by a cluster solution that uses Red Hat Enterprise Linux. High Availability Add-On. The cluster solution uses an overlay IP address to ensure that the high availability cluster is still accessible during failover scenarios.
An SAP solutions architect needs to facilitate the network connection to this overlay IP address from multiple locations. These locations include more than 25 VPCs, other AWS Regions, and the on-premises environment. The company already has set up an AWS Direct Connect connection between the on-premises environment and AWS.
What should the SAP solutions architect do to meet these requirements in the MOST scalable manner?
 - A. Use VPC peering between the VPCs to route traffic between them.
 - B. Use AWS Transit Gateway to connect the VPCs and on-premises networks together.
 - C. Use a Network Load Balancer to route connections to various targets within VPCs.
 - D. Deploy a Direct Connect gateway to connect the Direct Connect connection over a private VIF to one or more VPCs in any accounts.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B
 
> AWS Transit Gateway is a network transit hub that can interconnect thousands of VPCs and on-premises networks through a central gateway. This simplifies the network architecture and eliminates the need for complex peering relationships. AWS Transit Gateway also supports inter-Region peering, which enables the connection of transit gateways across different AWS Regions using the AWS global network. This way, the SAP NetWeaver workload on SAP HANA can be accessed from multiple locations with high performance and security.
</details> 

## Question 4
A company is implementing SAP HANA on AWS. According to the company’s security policy, SAP backups must be encrypted. Only authorized team members can have the ability to decrypt the SAP backups.
What is the MOST operationally efficient solution that meets these requirements?

 - A. Configure AWS Backint Agent for SAP HANA to create SAP backups in an Amazon S3 bucket. After a backup is created, encrypt the backup by using client-side encryption. Share the encryption key with authorized team members only.
 - B. Configure AWS Backint Agent for SAP HANA to use AWS Key Management Service (AWS KMS) for SAP backups. Create a key policy to grant decryption permission to authorized team members only.
 - C. Configure AWS Storage Gateway to transfer SAP backups from a file system to an Amazon S3 bucket. Use an S3 bucket policy to grant decryption permission to authorized team members only.
 - D. Configure AWS Backint Agent for SAP HANA to use AWS Key Management Service (AWS KMS) for SAP backups. Grant object ACL decryption permission to authorized team members only.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B
 
> AWS Backint Agent for SAP HANA to use AWS Key Management Service (AWS KMS) for SAP backups. AWS Backint Agent for SAP HANA is a tool that integrates SAP HANA with Amazon S3 and enables you to create and manage SAP HANA backups in Amazon S3 https://docs.aws.amazon.com/sap/latest/sap-hana/aws-backint-agent-Amazon-S3.html. AWS KMS is a service that allows you to create and manage encryption keys and use them to encrypt and decrypt data in AWS services and in your applications https://docs.aws.amazon.com/aws-backup/latest/devguide/encryption.html. By using AWS Backint Agent for SAP HANA with AWS KMS, you can encrypt your SAP backups with a customer master key (CMK) that you control and specify in the AWS Backup vault that stores your backups https://docs.aws.amazon.com/sap/latest/sap-hana/aws-backint-agent-Amazon-S3.html. You can also create a key policy to grant decryption permission to authorized team members only, which will ensure that only they can access and restore the encrypted backups https://docs.aws.amazon.com/aws-backup/latest/devguide/encryption.html.
</details> 
 

## Question 5
A data analysis company has two SAP landscapes that consist of sandbox, development, QA, pre-production, and production servers. One landscape is on Windows, and the other landscape is on Red Hat Enterprise Linux. The servers reside in a room in a building that other tenants share.
An SAP solutions architect proposes to migrate the SAP applications to AWS. The SAP solutions architect wants to move the production backups to AWS and wants to make the backups highly available to restore in case of unavailability of an on-premises server.
Which solution will meet these requirements MOST cost-effectively?

 - A. Take a backup of the production servers. Implement an AWS Storage Gateway Volume Gateway. Create file shares by using the Storage Gateway Volume Gateway. Copy the backup files to the file shares through NFS and SMB.
 - B. Take a backup of the production servers. Send those backups to tape drives. Implement an AWS Storage Gateway Tape Gateway. Send the backups to Amazon S3 Standard-Infrequent Access (S3 Standard-IA) through the S3 console. Move the backups immediately to S3 Glacier Deep Archive.
 - C. Implement a third-party tool to take images of the SAP application servers and database server. Take regular snapshots at 1-hour intervals. Send the snapshots to Amazon S3 Glacier directly through the S3 Glacier console. Store the same images in different S3 buckets in different AWS Regions.
 - D. Take a backup of the production servers. Implement an Amazon S3 File Gateway. Create file shares by using the S3 File Gateway. Copy the backup files to the file shares through NFS and SMB. Map backup files directly to Amazon S3. Configure an S3 Lifecycle policy to send the backup files to S3 Glacier based on the company’s data retention policy.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D
 
> This solution will allow the company to store their backups in Amazon S3, which is highly available and durable, and automate the movement of data to S3 Glacier based on the company's data retention policy, providing cost-effective data storage. See https://aws.amazon.com/blogs/storage/integrate-an-sap-ase-database-to-amazon-s3-using-aws-storage-gateway/ and https://aws.amazon.com/blogs/awsforsap/passive-disaster-recovery-for-sap-applications-using-aws-backup-and-aws-backint-agent/

</details>

## Question 6
A company’s SAP basis team is responsible for database backups in Amazon S3. The company frequently needs to restore the last 3 months of backups into the pre-production SAP system to perform tests and analyze performance. Previously, an employee accidentally deleted backup files from the S3 bucket. The SAP basis team wants to prevent accidental deletion of backup files in the future.
Which solution will meet these requirements?

 - A. Create a new resource-based policy that prevents deletion of the S3 bucket.
 - B. Enable versioning and multi-factor authentication (MFA) on the S3 bucket.
 - C. Create signed cookies for the backup files in the S3 bucket. Provide the signed cookies to authorized users only.
 - D. Apply an S3 Lifecycle policy to move the backup files immediately to S3 Glacier.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

> This option will allow the SAP basis team to enable versioning and multi-factor authentication (MFA) on the S3 bucket. Versioning is a feature that allows you to preserve, retrieve, and restore every version of every object stored in an S3 buckethttps://aws.amazon.com/getting-started/hands-on/protect-data-on-amazon-s3/. MFA is a security feature that requires users to provide two forms of authentication when performing certain actions on an S3 buckethttps://stackoverflow.com/questions/72634045/aws-s3-how-to-protect-against-accidental-deletion. By enabling versioning and MFA on the S3 bucket, the SAP basis team can protect their backup files from being overwritten or deleted by mistake or by unauthorized users. They can also recover any deleted versions of their backup files from the S3 bucket.
</details>

## Question 7
A company wants to run SAP HANA on AWS in the eu-central-1 Region. The company must make the SAP HANA system highly available by using SAP HANA system replication. In addition, the company must create a disaster recovery (DR) solution that uses SAP HANA system replication in the eu-west-1 Region. As prerequisites, the company has confirmed that Inter-AZ latency is less than 1 ms and that Inter-Region latency is greater than 1 ms.
Which solutions will meet these requirements? **(Choose two.)**

 - A. Install the tier 1 primary system and the tier 2 secondary system in eu-central-1. Configure the tier 1 system in Availability Zone 1. Configure the tier 2 system in Availability Zone 2. Configure SAP HANA system replication between tier 1 and tier 2 by using ASYNC replication mode. Install the DR tier 3 secondary system in eu-west-1 by using SYNC replication mode.
 - B. Install the tier 1 primary system and the tier 2 secondary system in eu-central-1. Configure the tier 1 system in Availability Zone 1. Configure the tier 2 system in Availability Zone 2. Configure SAP HANA system replication between tier 1 and tier 2 by using SYNC replication mode. Install the DR tier 3 secondary system in eu-west-1 by using ASYNC replication mode.
 - C. Install the tier 1 primary system and the tier 2 secondary system in eu-central-1. Configure the tier 1 system in Availability Zone 1. Configure the tier 2 system in Availability Zone 2. Configure SAP HANA system replication between tier 1 and tier 2 by using SYNC replication mode. Install the DR tier 3 secondary system in eu-west-1. Store daily backups from tier 1 in an Amazon S3 bucket in eu-central-1. Use S3 Cross-Region Replication to copy the daily backups to eu-west-1, where they can be restored if needed.
 - D. Install the tier 1 primary system in eu-central-1. Install the tier 2 secondary system and the DR tier 3 secondary system in eu-west-1. Configure the tier 2 system in Availability Zone 1. Configure the tier 3 system in Availability Zone 2. Configure SAP HANA system replication between all tiers by using ASYNC replication mode.
 - E. Install the tier 1 primary system and the tier 2 secondary system in eu-central-1. Configure the tier 1 system in Availability Zone 1. Configure the tier 2 system in Availability Zone 2. Configure SAP HANA system replication between tier 1 and tier 2 by using SYNCMEM replication mode. Install the DR tier 3 secondary system in eu-west-1 by using ASYNC replication mode.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: BE
 
> The problem statement says that HANA system replication is used for both high availability and DR. Therefore, for High Availability, it would be SYNC replication mode or SYNCMEM replication mode, and for DR, it would be ASYNC replication mode. So, the answer is B and E.
Option C does not use HANA system replication in DR.
</details> 

## Question 8
A company is running an SAP ERP Central Component (SAP ECC) system on an SAP HANA database that is 10 TB in size. The company is receiving notifications about long-running database backups every day. The company uses AWS Backint Agent for SAP HANA (AWS Backint agent) on an Amazon EC2 instance to back up the database. An SAP NetWeaver administrator needs to troubleshoot the problem and propose a solution.
Which solution will help resolve this problem?

 - A. Ensure that AWS Backint agent is configured to send the backups to an Amazon S3 bucket over the internet. Ensure that the EC2 instance is configured to access the internet through a NAT gateway.
 - B. Check the UploadChannelSize parameter for AWS Backint agent. Increase this value in the aws-backint-agent-config.yaml configuration file based on the EC2 instance type and storage configurations.
 - C. Check the MaximumConcurrentFilesForRestore parameter for AWS Backint agent. Increase the parameter from 5 to 10 by using the aws-backint-agent-config.yaml configuration file.
 - D. Ensure that the backups are compressed. If necessary, configure AWS Backint agent to compress the backups and send them to an Amazon S3 bucket.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B
 
> The performance of backup and restore depends on many factors, such as the type of EC2 instance used, the EBS volumes, and the number of SAP HANA channels. If your database size is less than 128 GB, SAP HANA defaults to a single channel, or your SAP HANA parameter parallel_data_backup_backint_channels is set to 1.
> Check the UploadChannelSize parameter
The UploadChannelSize parameter is used to determine how many files can be uploaded in parallel to the S3 bucket during backups. [https://docs.aws.amazon.com/sap/latest/sap-hana/aws-backint-agent-installing-configuring.html]
> (The connection between AWS Backint agent and S3 fails due to high throughput [https://docs.aws.amazon.com/sap/latest/sap-hana/aws-backint-agent-troubleshooting.html])

</details> 

## Question 9
A company wants to migrate its SAP workloads to AWS from another cloud provider. The company’s landscape consists of SAP S/4HANA, SAP BW/4HANA, SAP Solution Manager, and SAP Web Dispatcher. SAP Solution Manager is running on SAP HANA.
The company wants to change the operating system from SUSE Linux Enterprise Server to Red Hat Enterprise Linux as a part of this migration. The company needs a solution that results in the least possible downtime for the SAP S/4HANA and SAP BW/4HANA systems.
Which migration solution will meet these requirements?

 - A. Use SAP Software Provisioning Manager to perform a system export/import for SAP S/4HANA, SAP BW/4HANA, SAP Solution Manager, and SAP Web Dispatcher.
 - B. Use backup and restore for SAP S/4HANA, SAP BW/4HANA, and SAP Solution Manager. Reinstall SAP Web Dispatcher on AWS with the necessary configuration.
 - C. Use backup and restore for SAP S/4HANA and SAP BW/4HANA. Use SAP Software Provisioning Manager to perform a system export/import for SAP Solution Manager. Reinstall SAP Web Dispatcher on AWS with the necessary configuration.
 - D. Use SAP HANA system replication to replicate the data between the source system and the target AWS system for SAP S/4HANA and SAP BW/4HANA. Use SAP Software Provisioning Manager to perform a system export/import for SAP Solution Manager. Reinstall SAP Web Dispatcher on AWS with the necessary configuration.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

> The following REDHAT site describes the conversion of SAP HANA from SUSE to REDHAT.
SAP HANA system replication is used.
https://www.redhat.com/en/resources/migrating-sap-workloads-linux-detail
> SolMan DB does not matter, question is about "least possible DT for S/4 and BW/4", therefore D shoud be correct. See also https://docs.aws.amazon.com/sap/latest/sap-hana/migrating-hana-hana-to-aws.html and  https://docs.aws.amazon.com/migrationhub-orchestrator/latest/userguide/migrate-sap.html

</details> 

## Question 10
A company is running an SAP on Oracle system on IBM Power architecture in an on-premises data center. The company wants to migrate the SAP system to AWS. The Oracle database is 15 TB in size. The company has set up a 100 Gbps AWS Direct Connect connection to AWS from the on-premises data center.
Which solution should the company use to migrate the SAP system MOST quickly?

 - A. Before the migration window, build a new installation of the SAP system on AWS by using SAP Software Provisioning Manager. During the migration window, export a copy of the SAP system and database by using the heterogeneous system copy process and R3load. Copy the output of the SAP system files to AWS through the Direct Connect connection. Import the SAP system to the new SAP installation on AWS. Switch over to the SAP system on AWS.
 - B. Before the migration window, build a new installation of the SAP system on AWS by using SAP Software Provisioning Manager. Back up the Oracle database by using native Oracle tools. Copy the backup of the Oracle database to AWS through the Direct Connect connection. Import the Oracle database to the SAP system on AWS. Configure Oracle Data Guard to begin replicating on-premises database log changes from the SAP system to the new AWS system. During the migration window, use Oracle to replicate any remaining changes to the Oracle database hosted on AWS. Switch over to the SAP system on AWS.
 - C. Before the migration window, build a new installation of the SAP system on AWS by using SAP Software Provisioning Manager. Create a staging Oracle database on premises to perform Cross Platform Transportable Tablespace (XTTS) conversion on the Oracle database. Take a backup of the converted staging database. Copy the converted backup to AWS through the Direct Connect connection. Import the Oracle database backup to the SAP system on AWS. Take regularly scheduled incremental backups and XTTS conversions of the staging database. Transfer these backups and conversions to the AWS target database. During the migration window, perform a final incremental Oracle backup. Convert the final Oracle backup by using XTTS. Replay the logs in the target Oracle database hosted on AWS. Switch over to the SAP system on AWS.
 - D. Before the migration window, launch an appropriately sized Amazon EC2 instance on AWS to receive the migrated SAP database. Create an AWS Server Migration Service (AWS SMS) job to take regular snapshots of the on-premises Oracle hosts. Use AWS SMS to copy the snapshot as an AMI to AWS through the Direct Connect connection. Create a new SAP on Oracle system by using the migrated AMI. During the migration window, take a final incremental SMS snapshot and copy the snapshot to AWS. Restart the SAP system by using the new up-to-date AMI. Switch over to the SAP system on AWS.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

> See https://aws.amazon.com/blogs/awsforsap/reducing-downtime-with-oracle-xtts-method-for-cross-platform-sap-migrations/.
</details> 

## Question 11

An SAP solutions architect is designing an SAP HANA scale-out architecture for SAP Business Warehouse (SAP BW) on SAP HANA on AWS. The SAP solutions architect identifies the design as a three-node scale-out deployment of xte.32xiarge Amazon EC2 instances.
The SAP solutions architect must ensure that the SAP HANA scale-out nodes can achieve the low-latency and high-throughput network performance that are necessary for node-to-node communication.
Which combination of steps should the SAP solutions architect take to meet these requirements? **(Choose two.)**

 - A. Create a cluster placement group. Launch the instances into the cluster placement group.
 - B. Create a spread placement group. Launch the instances into the spread placement group.
 - C. Create a partition placement group. Launch the instances into the partition placement group.
 - D. Based on the operating system version, verify that enhanced networking is enabled on all the nodes.
 - E. Switch to a different instance family that provides network throughput that is greater than 25 Gbps.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: AD
 
> Spread and Partition placement groups ensure distinct underlying hardware, but Cluster is the one that guarantees same Availability Zone and achieve lowest latency network performance. Additionally, enhanced networking operating system setting should be always enabled on SAP servers. See https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html.
</details> 

## Question 12

A company needs to migrate its critical SAP workloads from an on-premises data center to AWS. The company has a few source production databases that are 10 TB or more in size. The company wants to minimize the downtime for this migration.
As part of the proof of concept, the company used a low-speed, high-latency connection between its data center and AWS. During the actual migration, the company wants to maintain a consistent connection that delivers high bandwidth and low latency. The company also wants to add a layer of connectivity resiliency. The backup connectivity does not need to be as fast as the primary connectivity.
An SAP solutions architect needs to determine the optimal network configuration for data transfer. The solution must transfer the data with minimum latency.
Which configuration will meet these requirements?

 - A. Set up one AWS Direct Connect connection for connectivity between the on-premises data center and AWS. Add an AWS Site-to-Site VPN connection as a backup to the Direct Connect connection.
 - B. Set up an AWS Direct Connect gateway with multiple Direct Connect connections that use a link aggregation group (LAG) between the on-premises data center and AWS.
 - C. Set up Amazon Elastic File System (Amazon EFS) file system storage between the on-premises data center and AWS. Configure a cron job to copy the data into this EFS mount. Access the data in the EFS file system from the target environment.
 - D. Set up two redundant AWS Site-to-Site VPN connections for connectivity between the on-premises data center and AWS.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A
 
> One Direct Connect, one VPN.
</details>

## Question 13

A company wants to migrate its SAP ERP landscape to AWS. The company will use a highly available distributed deployment for the new architecture. Clients will access SAP systems from a local data center through an AWS Site-to-Site VPN connection that is already in place. An SAP solutions architect needs to design the network access to the SAP production environment.
Which configuration approaches will meet these requirements? **(Choose two.)**

 - A. For the ASCS instance, configure an overlay IP address that is within the production VPC CIDR range. Create an AWS Transit Gateway. Attach the VPN to the transit gateway. Use the transit gateway to route the communications between the local data center and the production VPC. Create a static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance.
 - B. For the ASCS instance, configure an overlay IP address that is outside the production VPC CIDR range. Create an AWS Transit Gateway. Attach the VPN to the transit gateway. Use the transit gateway to route the communications between the local data center and the production VPC. Create a static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance.
 - C. For the ASCS instance, configure an overlay IP address that is within the production VPC CIDR range. Create a target group that points to the overlay IP address. Create a Network Load Balancer, and register the target group. Create a static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance.
 - D. For the ASCS instance, configure an overlay IP address that is outside the production VPC CIDR range. Create a target group that points to the overlay IP address. Create a Network Load Balancer, and register the target group. Create a static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance.
 - E. For the ASCS instance, configure an overlay IP address that is outside the production VPC CIDR range. Create a target group that points to the overlay IP address. Create an Application Load Balancer, and register the target group. Create a static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: BD
 
> Overlay IP should be outside Prod VPC CIDR, thus A and C are eliminated.
HA of ASCS uses Network load balancer and not application load balancer, so E is eliminated. Application load balancer cannot be attached with Overlay IP

> SAP on AWS High Availability with Overlay IP Address Routing：
AWS Transit Gateway serves as central hub to facilitate network connection to an overlay IP address.
Elastic Load Balancing where a Network Load Balancer enables network access to an overlay IP addres
https://docs.aws.amazon.com/sap/latest/sap-hana/sap-ha-overlay-ip.html
</details>

## Question 14

A company is running an SAP HANA database on AWS. The company is running AWS Backint Agent for SAP HANA (AWS Backint agent) on an Amazon EC2 instance. AWS Backint agent is configured to back up to an Amazon S3 bucket. The backups are failing with an AccessDenied error in the AWS Backint agent log file.
What should an SAP basis administrator do to resolve this error?

 - A. Assign execute permissions at the operating system level for the AWS Backint agent binary and for AWS Backint agent.
 - B. Assign an IAM role to an EC2 instance. Attach a policy to the IAM role to grant access to the target S3 bucket.
 - C. Assign the correct Region ID for the S3BucketAwsRegion parameter in AWS Backint agent for the SAP HANA configuration file.
 - D. Assign the value for the EnableTagging parameter in AWS Backint agent for the SAP HANA configuration file.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

> [AccessDenied appears in agent logs](https://docs.aws.amazon.com/sap/latest/sap-hana/aws-backint-agent-troubleshooting.html)
</details>

## Question 15

A company is starting a new project to implement an SAP landscape with multiple accounts that belong to multiple teams in the us-east-2 Region. These teams include procurement, finance, sales, and human resources. An SAP solutions architect has started designing this new landscape and the AWS account structures.
The company wants to use automation as much as possible. The company also wants to secure the environment, implement federated access to accounts, centralize logging, and establish cross-account security audits. In addition, the company’s management team needs to receive a top-level summary of policies that are applied to the AWS accounts.
What should the SAP solutions architect do to meet these requirements?

 - A. Use AWS CloudFormation StackSets to apply SCPs to multiple accounts in multiple Regions. Use an Amazon CloudWatch dashboard to check the applied policies in the accounts.
 - B. Use an AWS Elastic Beanstalk blue/green deployment to create IAM policies and apply them to multiple accounts together. Use an Amazon CloudWatch dashboard to check the applied policies in the accounts.
 - C. Implement guardrails by using AWS CodeDeploy and AWS CodePipeline to deploy SCPs into each account. Use the CodePipeline deployment dashboard to check the applied policies in the accounts.
 - D. Apply SCPs through AWS Control Tower. Use the AWS Control Tower integrated dashboard to check the applied policies in the accounts.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D
 
> AWS Control Tower is a service that automates the set-up of a multi-account AWS environment and provides guardrails to help enforce compliance and security best practices. By using AWS Control Tower, the company can apply SCPs to multiple accounts, monitor policies across multiple accounts, and receive a top-level summary of policies that are applied to the AWS accounts. Additionally, the integrated dashboard of AWS Control Tower can be used to check the applied policies in the accounts. See https://aws.amazon.com/blogs/mt/managing-the-multi-account-environment-using-aws-organizations-and-aws-control-tower/

</details>

## Question 16

A company is running its SAP workloads on premises and needs to migrate the workloads to AWS. All the workloads are running on SUSE Linux Enterprise Server and Oracle Database. The company’s landscape consists of SAP ERP Central Component (SAP ECC), SAP Business Warehouse (SAP BW), and SAP NetWeaver systems. The company has a dedicated AWS Direct Connect connection between its on-premises environment and AWS. The company needs to migrate the systems to AWS with the least possible downtime.
Which migration solution will meet these requirements?

 - A. Use SAP Software Provisioning Manager to perform an export of the systems. Copy the export to Amazon S3. Use SAP Software Provisioning Manager to perform an import of the systems to SUSE Linux Enterprise Server and Oracle Database on AWS.
 - B. Use SAP Software Provisioning Manager to perform parallel export/import of the systems to migrate the systems to SUSE Linux Enterprise Server and Oracle Database on AWS.
 - C. Use SAP Software Provisioning Manager to perform parallel export/import of the systems to migrate the systems to Oracle Enterprise Linux and Oracle Database on AWS.
 - D. Use SAP Software Provisioning Manager to perform an export of the systems. Copy the export to Amazon S3. Use SAP Software Provisioning Manager to perform an import of the systems to Oracle Enterprise Linux and Oracle Database on AWS.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C
 
> SUSE does not support Oracle on AWS. So A and B are eliminated. Of C and D, parallel exp/imp will take less time so less outage. See https://launchpad.support.sap.com/#/notes/1656250

</details>

## Question 17

A company is designing a disaster recovery (DR) strategy for an SAP HANA database that runs on an Amazon EC2 instance in a single Availability Zone. The company can tolerate a long RTO and an RPO greater than zero if it means that the company can save money on its DR process.
The company has configured an Amazon CloudWatch alarm to automatically recover the EC2 instance if the instance experiences an unexpected issue. The company has set up AWS Backint Agent for SAP HANA to save the backups into Amazon S3.
What is the MOST cost-effective DR option for the company's SAP HANA database?

 - A. Set up AWS CloudFormation to automatically launch a new EC2 instance for the SAP HANA database in a second Availability Zone from backups that are stored in Amazon S3. When the SAP HANA database is operational, perform a database restore by using the standard SAP HANA restore process.
 - B. Launch a secondary EC2 instance for the SAP HANA database on a less powerful EC2 instance type in a second Availability Zone. Configure SAP HANA system replication with the preload option turned off.
 - C. Launch a secondary EC2 instance for the SAP HANA database on an equivalent EC2 instance type in a second Availability Zone. Configure SAP HANA system replication with the preload option turned on.
 - D. Set up AWS CloudFormation to automatically launch a new EC2 instance for the SAP HANA database in a second Availability Zone from backups that are stored in Amazon Elastic Block Store (Amazon EBS). When the SAP HANA database is operational, perform a database restore by using the standard SAP HANA restore process.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A
 
> This option leverages the existing backups stored in Amazon S3 and does not require running additional, potentially costly, EC2 instances until needed. The new instance is only launched in the event of a disaster, and data is then restored from the S3 backup. This is a cost-effective method, as you only pay for the S3 storage of your backup and the EC2 resources when you need them.

> See https://docs.aws.amazon.com/sap/latest/sap-hana/hana-ops-ha-dr.html#backint-hana-hadr

</details>

## Question 18

A company is using a multi-account strategy for SAP HANA and SAP BW/4HANA instances across development, QA, and production systems in the same AWS Region. Each system is hosted in its own VPC. The company needs to establish cross-VPC communication between the SAP systems.
The company might add more SAP systems in the future. The company must create connectivity across the SAP systems and hundreds of AWS accounts. The solution must maximize scalability and reliability.
Which solution will meet these requirements?

 - A. Create an AWS Transit Gateway in a central networking account. Attach the transit gateway to the AWS accounts. Set up routing and a network ACL to establish communication.
 - B. Set up VPC peering between the accounts. Configure routing in each VPC to use the VPC peering links.
 - C. Create a transit VPC that uses the hub-and-spoke model. Set up routing to use the transit VPC for communication between the SAP systems.
 - D. Create a VPC link for each SAP system. Use the VPC links to connect the SAP systems.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A
 
> AWS Transit Gateway is a service that enables you to connect your Amazon Virtual Private Clouds (VPCs) and on-premises networks to a single gateway. It is a great solution for scenarios like this where you need to connect multiple VPCs across several AWS accounts. It simplifies network architecture, reduces operational overhead, and is highly scalable. With Transit Gateway, you can set up routing and network ACLs to establish and control communication between the connected VPCs.
</details>


## Question 19

A company is planning to deploy a new SAP NetWeaver ABAP system on AWS with an Oracle database that runs on an Amazon EC2 instance. The EC2 instance uses a Linux-based operating system. The company needs a database storage solution that provides flexibility to adjust the IOPS regardless of the allocated storage size.
Which solution will meet these requirements MOST cost-effectively?

 - A. General Purpose SSD (gp3) Amazon Elastic Block Store (Amazon EBS) volumes
 - B. Amazon Elastic File System (Amazon EFS) Standard-Iinfrequent Access (Standard-IA) storage class
 - C. Amazon FSx for Windows File Server
 - D. Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volumes
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D
 
> Amazon EBS gp3 volumes are the next generation of general purpose SSD volumes for Amazon EC2. gp3 volumes provide the ability to independently configure volume capacity and performance, enabling you to optimize costs for a wide range of workloads. By other hand, we recommend the io2 or io2 Block Express configuration for mission-critical SAP HANA production workloads because provide the highest performance for mission-critical applications. But if the cost effective, gp3 is the one.
See https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/requesting-ebs-volume-modifications.html and https://aws.amazon.com/blogs/storage/optimizing-sap-hanas-persistence-layer-with-amazon-ebs-gp3-volumes/
</details> 


## Question 20

A company is using SAP NetWeaver with Java on AWS. The company has updated its generation of Amazon EC2 instances to the most recent generation of EC2 instances. When the company tries to start SAP, the startup fails. The log indicates that the SAP license expired or is not valid.
What is the reason for this issue?

 - A. The instance ID changed as part of the EC2 generation change.
 - B. The instance’s hypervisor changed from Xen to Nitro.
 - C. The SAP Java Virtual Machine (SAP JVM) is not compatible with the new instance type.
 - D. An EC2 generation change is not supported for SAP Java-based systems.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B
 
> When you change the generation of the Amazon EC2 instance, the underlying hypervisor can change from Xen to Nitro. The SAP license is bound to the hypervisor's hardware key, so if the hypervisor changes, the hardware key changes, which can make the SAP license invalid. This is likely the reason why the startup is failing after the update to a newer generation of EC2 instances.

> https://launchpad.support.sap.com/#/notes/2591601

> https://docs.aws.amazon.com/sap/latest/general/overview-sap-on-aws.html


</details> 


## Question 21

A company’s basis administrator is planning to deploy SAP on AWS in Linux. The basis administrator must set up the proper storage to store SAP HANA data and log volumes.
Which storage options should the basis administrator choose to meet these requirements? **(Choose two.)**

 - A. Amazon Elastic Block Store (Amazon EBS) Throughput Optimized HDD (st1)
 - B. Amazon Elastic Block Store (Amazon EBS) Provisioned OPS SSD (io1, io2)
 - C. Amazon S3
 - D. Amazon Elastic File System (Amazon EFS)
 - E. Amazon Elastic Block Store (Amazon EBS) General Purpose SSD (gp2, gp3)

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: BE
 
> S3 is only suitable for backups and EFS for shared filesystems like /sapmnt or /usr/sap/trans in a distributed or HA landscape. Correct answers are B and E. See https://docs.aws.amazon.com/sap/latest/sap-hana/hana-ops-storage-config.html


</details> 


## Question 22

A company has deployed a highly available SAP NetWeaver system on SAP HANA into a VPC. The system is distributed across multiple Availability Zones within a single AWS Region. SAP NetWeaver is running on SUSE Linux Enterprise Server for SAP. SUSE Linux Enterprise High Availability Extension is configured to protect SAP ASCS and ERS instances and uses the overlay IP address concept. The SAP shared files /sapmnt and /usr/sap/trans are hosted on an Amazon Elastic File System (Amazon EFS) file system.
The company needs a solution that uses already-existing private connectivity to the VPC. The SAP NetWeaver system must be accessible through the SAP GUI client tool.
Which solutions will meet these requirements? **(Choose two.)**

 - A. Deploy an Application Load Balancer. Configure the overlay IP address as a target.
 - B. Deploy a Network Load Balancer. Configure the overlay IP address as a target.
 - C. Use an Amazon Route 53 private zone. Create an A record that has the overlay IP address as a target.
 - D. Use AWS Transit Gateway. Configure the overlay IP address as a static route in the transit gateway route table. Specify the VPC as a target.
 - E. Use a NAT gateway. Configure the overlay IP address as a target

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: BC
 
> AWS Transit Gateway is generally used for connecting multiple VPCs and on-premises networks. Adding a static route for the overlay IP does not specifically facilitate SAP GUI client access and would be more applicable for routing concerns between multiple networks. See https://docs.aws.amazon.com/sap/latest/sap-hana/sap-oip-sap-on-aws-high-availability-setup.html

</details> 


## Question 23

A company is planning to move all its SAP applications to Amazon EC2 instances in a VPC. Recently, the company signed a multiyear contract with a payroll software-as-a-service (SaaS) provider. Integration with the payroll SaaS solution is available only through public web APIs.
Corporate security guidelines state that all outbound traffic must be validated against an allow list. The payroll SaaS provider provides only fully qualified domain name (FQDN) addresses and no IP addresses or IP address ranges. Currently, an on-premises firewall appliance filters FQDNs. The company needs to connect an SAP Process Orchestration (SAP PO) system to the payroll SaaS provider.
What must the company do on AWS to meet these requirements?

 - A. Add an outbound rule to the security group of the SAP PO system to allow the FQDN of the payroll SaaS provider and deny all other outbound traffic.
 - B. Add an outbound rule to the network ACL of the subnet that contains the SAP PO system to allow the FQDN of the payroll SaaS provider and deny all other outbound traffic.
 - C. Add an AWS WAF web ACL to the VPAdd an outbound rule to allow the SAP PO system to connect to the FQDN of the payroll SaaS provider.
 - D. Add an AWS Network Firewall firewall to the VPC. Add an outbound rule to allow the SAP PO system to connect to the FQDN of the payroll SaaS provider.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D
 
> AWS Network Firewall is a managed service that makes it easy to deploy essential network protections for all of your Amazon Virtual Private Clouds (VPCs). The service can be configured to filter traffic based on fully qualified domain names (FQDN), which meets the requirement of the scenario. See https://docs.aws.amazon.com/network-firewall/latest/developerguide/stateful-rule-groups-domain-names.html

</details> 


## Question 24

A company is planning to migrate its on-premises SAP application to AWS. The application runs on VMware vSphere. The SAP ERP Central Component (SAP ECC) server runs on an IBM Db2 database that is 2 TB in size. The company wants to migrate the database to SAP HANA.
Which migration strategy will meet these requirements?

 - A. Use AWS Application Migration Service (CloudEndure Migration).
 - B. Use SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move.
 - C. Use AWS Server Migration Service (AWS SMS).
 - D. Use AWS Database Migration Service (AWS DMS).

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B
 
> The Database Migration Option (DMO) within the SAP Software Update Manager (SUM) is the recommended tool to convert your existing SAP ERP database to SAP HANA. This is because DMO is able to update the existing SAP system and migrate the database to SAP HANA in one step, hence reducing the total downtime required for the migration.

Option A: AWS Application Migration Service (CloudEndure Migration) doesn't support database transformation (such as converting IBM DB2 to SAP HANA).

Option C: AWS Server Migration Service (AWS SMS) is used for migrating on-premise servers to AWS, but it does not handle database conversions from IBM Db2 to SAP HANA.

Option D: AWS Database Migration Service (AWS DMS) helps you migrate databases to AWS easily and securely, but as of my knowledge cutoff in September 2021, it doesn't support SAP HANA as a target for migration.
</details> 


## Question 25

A company hosts multiple SAP applications on Amazon EC2 instances in a VPC. While monitoring the environment, the company notices that multiple port scans are attempting to connect to SAP portals inside the VPC. These port scans are originating from the same IP address block. The company must deny access to the VPC from all the offending IP addresses for the next 24 hours.
Which solution will meet this requirement?

 - A. Modify network ACLs that are associated with all public subnets in the VPC to deny access from the IP address block.
 - B. Add a rule in the security group of the EC2 instances to deny access from the IP address block.
 - C. Create a policy in AWS Identity and Access Management (IAM) to deny access from the IP address block.
 - D. Configure the firewall in the operating system of the EC2 instances to deny access from the IP address block.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A
 
> First consider that "from the same IP address block" refers to that the scans are always from IPs of the same block, not from the same block than the portal IP. Then, Network Access Control Lists (ACLs) in Amazon VPC provide a layer of security for your VPC that act as a firewall for controlling traffic in and out of one or more subnets. You can add rules to your Network ACL to deny the traffic from specific IP address block.
</details> 


## Question 26
A company has deployed SAP workloads on AWS. The AWS Data Provider for SAP is installed on the Amazon EC2 instance where the SAP application is running. An SAP solutions architect has attached an IAM role to the EC2 instance with the following policy:
![image](https://github.com/pauise/pub/assets/155977504/46e79045-d91a-456b-87e4-164ab0969c6f)
The AWS Data Provider for SAP is not returning any metrics to the SAP application.
Which change should the SAP solutions architect make to the IAM permissions to resolve this issue?

 - A. Add the cloudwatch:ListMetrics action to the policy statement with Sid AWSDataProvider1.
 - B. Add the cloudwatch:GetMetricStatistics action to the policy statement with Sid AWSDataProvider1.
 - C. Add the cloudwatch:GetMetricStream action to the policy statement with Sid AWSDataProvider1.
 - D. Add the cloudwatch:DescribeAlarmsForMetric action to the policy statement with Sid AWSDataProvider1.

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B
 
> See https://docs.aws.amazon.com/sap/latest/general/data-provider-troubleshooting.html

</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 


## Question 

<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details> 

