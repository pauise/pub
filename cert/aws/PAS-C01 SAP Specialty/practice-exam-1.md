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



<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> 
</details>

 
> bla.
</details> nn. lalala.
- A. lala
- B. lala
- C. lala
- D. lala
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> bla.
</details> nn. lalala.
- A. lala
- B. lala
- C. lala
- D. lala
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> bla.
</details> nn. lalala.
- A. lala
- B. lala
- C. lala
- D. lala
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> bla.
</details> 





nn. lalala.
- A. lala
- B. lala
- C. lala
- D. lala
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ?
 
> bla.
</details> 






1. A company is starting a new project to implement an SAP landscape with multiple accounts that belong to multiple teams in the us-east-2 Region. These teams include procurement finance sales and human resources An SAP solutions
architect has started designing this new landscape and the AWS account structures The company wants to use automation as much as possible The company also wants to secure the environment implement federated access to accounts
centralize logging and establish cross-account security audits in addition the company's management team needs to receive a top-level summary of policies that are applied to the AWS accounts.
What should the SAP solutions architect do to meet these requirements?
    - A. Use AWS CloudFormation StackSets to apply SCPs to multiple accounts in multiple Regions. Use an Amazon CloudWatch dashboard to check the applied policies in the accounts
    - B. Use an AWS Elastic Beanstalk blue green deployment to create 1AM policies and apply them to multiple accounts together Use an Amazon CloudWatch dashboard to check the applied policies in the accounts
    - C. Implement guardrails by using AWS CodeDeploy and AWS CodePipeline to deploy SCPs into each account Use the CodePipeline deployment dashboard to check the applied policies in the accounts
    - D. Apply SCPs through AWS Control Tower Use the AWS Control Tower integrated dashboard to check the applied policies in the accounts
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
2. A company is running its SAP workloads on premises and needs to migrate the workloads to AWS All the workloads are running on SUSE Linux Enterprise Server and Oracle Database. The company's landscape consists of SAP ERP
Central Component {SAP ECC). SAP Business Warehouse (SAP BW), and SAP NetWeaver systems. The company has a dedicated AWS Direct Connect connection between its on-premises environment and AWS The company needs to
migrate the systems to AWS with the least possible downtime Which migration solution will meet these requirements?
    - A. Use SAP Software Provisioning Manager to perform an export of the systems Copy the export to Amazon S3 Use SAP Software Provisioning Manager to perform an import of the systems to SUSE Linux Enterprise Server and Oracle
Database on AWS
    - B. Use SAP Software Provisioning Manager to perform parallel export import of the systems to migrate the systems to SUSE Linux Enterprise Server and Oracle Database on AWS
    - C. Use SAP Software Provisioning Manager to perform parallel export/import of the systems to migrate the systems to Oracle Enterprise Linux and Oracle Database on AWS
    - D. Use SAP Software Provisioning Manager to perform an export of the systems Copy the export to Amazon S3 Use SAP Software Provisioning Manager to perform an import of the systems to Oracle Enterprise Linux and Oracle Database
on AWS.
<details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C
</details> 

3. A company wants 10 run SAP HANA on AWS m the eu-centrai-1 Region. The company must make the SAP HANA system highly available by using SAP HANA system replication in addition the company must create a disaster recovery
(DR) solution that uses SAP HANA system replication in the eu-west-1 Region As prerequisites the company has confirmed that inter-AZ latency is less than 1 ms and that Inter-Region latency is greater than 1 ms.
Which solutions will meet these requirements? (Select TWO.)
    - A. Install the tier 1 primary system and the tier 2 secondary system in eu-central-1 Configure the tier 1 system m Availability Zone 1 Configure the tier 2 system m Availability Zone 2 Configure SAP HANA system replication between tier 1
and tier 2 by using ASYNC replication mode install the OR tier 3 secondary system m eu-west-1 by using SYNC replication mode.
    - B. Install the tier 1 primary system and the tier 2 secondary system in eu-central-1 Configure the tier 1 system in Availability Zone 1 Configure the tier 2 system m Availability Zone 2 Configure SAP HANA system replication between tier 1
and tier 2 by using SYNC replication mode Install the OR her 3 secondary system n eu-west-1 by using ASYNC replication mode.
    - C. Install the tier 1 primary system and the tier 2 secondary system in eu-central-1 Configure the tier 1 system in Availability Zone 1 Configure the tier 2 system in Availability Zone 2 Configure SAP HANA system replication between tier 1
and tier 2 by using SYNC replication mode Install the OR tier 3 secondary system n eu-west-1 Store daily backups from tier 1 m an Amazon S3 bucket m eu-central-1 Use S3 Cross-Region Replication to copy the daily backups to eu-westi
where they can be restored if needed
    - D. install the tier 1 primary system in eu-central-1 install the tier 2 secondary system and the DR tier 3 secondary system m eu-west-1 Configure the tier 2 system in Availability Zone 1 Configure the tier 3 system in Availability Zone 2
Configure SAP HANA system replication between all tiers by using ASYNC replication mode
    - E. Install the tier 1 primary system and the tier 2 secondary system in eu-central-1 Configure the tier 1 system m Availability Zone 1 Configure the tier 2 system m Availability Zone 2 Configure SAP HANA system replication between tier 1
and tier 2 by using SYNCMEM replication mode Install the DR tier 3 secondary system in eu-west-1 by using ASYNC replication mode
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: BE

</details> 
4. A company is running an SAP ERP Central Component (SAP ECC) system on an SAP HANA database that is 10 TB m size The company rs receiving notifications about long-running database backups every day The company uses AWS
Backint Agent for SAP HANA (AWS Backint agent) on an Amazon EC2 instance to back up the database An SAP NetWeaver administrator needs to troubleshoot the problem and propose a solution Which solution will help resolve this
problem'?
    - A. Ensure mat AWS Backint agent is configured to send the backups to an Amazon S3 bucket over the internet Ensure that the EC2 instance is configured to access the internet through a NAT gateway
    - B. Check the UploadChanneiSize parameter for AWS Backint agent increase this value in the awsbackint- agent-config yaml configuration file based on the EC2 instance type and storage configurations
    - C. Check the MaximumConcurrentFilesForRestore parameter tor AWS Backint agent Increase the parameter from 5 to 10 by using the aws-backint-agent-config yaml configuration file
    - D. Ensure that the backups are compressed if necessary configure AWS Backint agent to compress the backups and send them to an Amazon S3 bucket
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details> 
5. A company wants to migrate its SAP workloads to AWS from another cloud provider. The company's landscape consists of SAP S 4HANA SAP BWMHANA SAP Solution Manager and SAP Web Dispatcher SAP Solution Manager 15 running
on SAP NANA The company wants 10 change the operating system from SUSE Linux Enterprise Server to Red Hat Enterprise Linux as a pan of this migration. The company needs a solution that results in the least possible downtime for the
SAP SMHANA and SAP BW 4HANA systems.
Which migration solution will meet these requirements?
    - A. Use SAP Software Provisioning Manager to perform a system export/import for SAP S/4HANA SAP BW.4HANA SAP Solution Manager and SAP Web Dispatcher
    - B. Use backup and restore tor SAP S'4HAN    - A. SAP BW4HANA and SAP Solution Manager Reinstall SAP Web Dispatcher on AWS with the necessary configuration
    - C. Use backup and restore for SAP S’4 HAN A and SAP BW 4HANA Use SAP Software Provisioning Manager to perform a system export import for SAP Solution Manager Reinstall SAP Web Dispatcher on AWS with the necessary
configuration.
    - D. Use SAP HANA system replication to replicate the data between the source system and the target AWS system for SAP S 4HANA and SAP BW 4HANA Use SAP Software Provisioning Manager to perform a system export import for SAP
Solution Manager Reinstall SAP Web Dispatcher on AWS with the necessary configuration
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
6. A company is running an SAP on Oracle system on IBM Power architecture in an on-premises data center. The company wants to migrate the SAP system to AWS. The Oracle database is 15 TB n size The company has set up a 100 Gbps
AWS Direct Connect connection to AWS from the on-premises data center.
Which solution should the company use to migrate the SAP system MOST quickly?
    - A. Before the migration window build a new installation of the SAP system on AWS by using SAP Software Provisioning Manager. During the migration window export a copy of the SAP system and database by using the heterogeneous
system copy process and R3load Copy the output of the SAP system files to AWS through the Direct Connect connection import the SAP system to the new SAP installation on AWS Switch over to the SAP system on AWS
    - B. Before the migration window build a new installation of the SAP system on AWS by using SAP Software Provisioning Manager Back up the Oracle database by using native Oracle tools Copy the backup of the Oracle database to AWS
through the Direct Connect connection Import the Oracle database to me SAP system on AWS Configure Oracle Data Guard to begin replication on-premises database log changes from the SAP system to the new AWS system During the
migration window use Oracle to replicate any remaining changes to the Oracle database hosted on AWS Switch over to the SAP system on AWS
    - C. Before the migration window build a new installation of the SAP system on AWS by using SAP Software Provisioning Manager Create a staging Oracle database on premises to perform Cross Platform Transportable Tablespace (XTTS)
conversion on the Oracle database Take a backup of the convened staging database Copy the converted backup to AWS through the Direct Connect connection import the Oracle database backup to the SAP system on AWS Take
regularly scheduled incremental backups and XTTS conversions of the staging database Transfer these backups and conversions to the AWS target database During the migration window, perform a final incremental Oracle backup
Convert the final Oracle backup by using XTTS Replay the logs in the target Oracle database hosted on AWS Switch over to the SAP system on AWS
    - D. Before the migration window launch an appropriately sized Amazon EC2 instance on AWS to receive the migrated SAP database Create an AWS Server Migration Service (AWS SMS) job to take regular snapshots of the on-premises
Oracle hosts Use AWS SMS to copy the snapshot as an AMI to AWS through the Direct Connect connection Create a new SAP on Oracle system by using the migrated AMI During the migration window take a final incremental SMS
snapshot and copy the snapshot to AWS Restart the SAP system by using the new up-to-date AMI Switch over to the SAP system on AWS
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
7. A company is designing a disaster recovery (DR) strategy for an SAP HANA database that runs on an Amazon EC2 instance in a single Availability Zone The company can tolerate a long RTO and an RPO greater than zero if it means that
the company can save money on its DR process.
The company has configured an Amazon CloudWatch alarm to automatically recover the EC2 instance if the instance experiences an unexpected issue. The company has set up AWS Backint Agent for SAP HANA to save the backups into
Amazon S3.
What is the MOST cost-effective DR option for the company's SAP HANA database?
    - A. Set up AWS CloudFormation to automatically launch a new EC2 instance for the SAP HANA database in a second Availability Zone from backups that are stored in Amazon S3 When the SAP HANA database is operational perform a
database restore by using the standard SAP HANA restore process.
    - B. Launch a secondary EC2 instance for the SAP HANA database on a less powerful EC2 instance type in a second Availability Zone Configure SAP HANA system replication with the preload option turned off
    - C. Launch a secondary EC2 instance tor the SAP HANA database on an equivalent EC2 instance type in a second Availability Zone Configure SAP HANA system replication with the preload option turned on
    - D. Set up AWS CloudFormation to automatically launch a new EC2 instance for the SAP HANA database in a second Availability Zone from backups that are stored in Amazon Elastic Block Store (Amazon EBS) When the SAP HANA
database is operational perform a database restore by using the standard SAP HANA restore process
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
8. A company is using a multi-account strategy for SAP HANA and SAP BW 4HANA instances across development QA and production systems m the same AWS Region Each system is hosted m its own VPC The company needs to establish
cross-VPC communication between the SAP systems.
The company might add more SAP systems m the future. The company must create connectivity across the SAP systems and hundreds of AWS accounts. The solution must maximize scalability and reliability.
Which solution will meet these requirements?
    - A. Create an AWS Transit Gateway in a central networking account Attach the transit gateway to the AWS accounts Set up routing and a network ACL to establish communication
    - B. Set up VPC peering between the accounts Configure routing in each VPC to use the VPC peering links
    - C. Create a transit VPC that uses the hub-and-spoke model set up routing to use the transit VPC for communication between the SAP systems
    - D. Create a VPC link for each SAP system Use the VPC links to connect the SAP systems
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
9. A company is planning to deploy a new SAP NetWeaverABAP system on AWS with an Oracle database that runs on an Amazon EC2 instance. The EC2 instance uses a Linux-based operating system. The company needs a database
storage solution that provides flexibility to adjust the IOPS regardless of the allocated storage size.
Which solution will meet these requirements MOST cost-effectively?
    - A. General Purpose SSD (gp3) Amazon Elastic Block Store (Amazon EBS) volumes
    - B. Amazon Elastic File System (Amazon EFS) Standard-Infrequent Access (Standard-IA) storage class
    - C. Amazon FSx for Windows File Server
    - D. Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volumes
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 




12. A company is planning to move its on-premises SAP HANA database to AWS. The company needs to migrate this environment to AWS as quickly as possible An SAP solutions architect will use AWS Launch Wizard for SAP to deploy this
SAP HANA workload.
Which combination of steps should the SAP solutions architect follow to start the deployment of this workload on AWS? (Select THREE.)
    - A. Download the SAP HANA software
    - B. Download the AWS CloudFormation template for the SAP HANA deployment
    - C. Download and extract the SAP HANA software upload the SAP HANA software to an FTP server that Launch Wizard can access
    - D. Upload the unextracted SAP HANA software to an Amazon S3 destination bucket Follow the S3 file path syntax for the software in accordance with Launch Wizard recommendations
    - E. Bring the operating system AMI by using the Bring. Your Own Image (BYOI) model or purchase the subscription for the operating system AMI from AWS Marketplace
    - F. Create the SAP file system by using Amazon Elastic Block Store (Amazon EBS) before the deployment
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ACF

</details> 
13. A company wants 10 implement SAP HANAonAWS with the Multi-AZ deployment option by using AWS Launch Wizard for SAP The solution will use SUSE Linux Enterprise High Availability Extension for the high availability deployment An
SAP solutions architect must ensure that all the prerequisites are met The SAP solutions architect also must ensure that the user inputs to start the guided deployment of Launch Wizard are valid.
Which combination of steps should the SAP solutions architect take to meet these requirements?
(Select TWO)
    - A. Before starting the Launch Wizard deployment create the underlying Amazon Elastic Block Store
(Amazon EBS) volume types to use for SAP HANA data and log volumes based on the performance requirements
    - B. Use a value for the PaceMakerTag parameter that is not used by any other Amazon EC2 instances in the AWS Region where the system is being deployed
    - C. Ensure that the virtual hostname for the SAP HANA database that is used for the SUSE Linux Enterprise High Availability Extension configuration is not used in any other deployed accounts
    - D. Ensure that the Virtual Address parameter is outside the VPC CIDR and is not being used in the route table that is associated with the subnets where primary and secondary SAP HANA instances will be deployed
    - E. Before starting the Launch Wizard deployment set up the SUSE Linux Enterprise High Availability Extension network configuration and security group
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: BE

</details> 
14. A company that has SAP workloads on premises plans to migrate an SAP environment to AWS. The company is new to AWS and has no poor setup. The company has the following requirements
- The application server and database server must be placed in isolated network configurations
• SAP systems must be accessible to the on-premises end users over the internet
• The cost of communications between the application server and the database server must be minimized Which combination of steps should an SAP solutions architect take to meet these requirements?
(Select TWO.)
    - A. Configure a Network Load Balancer for incoming connections from end users
    - B. Set up an AWS Site-to-Site VPN connection between the company's on-premises network and AWS
    - C. Separate the application server and the database server by using different VPCs
    - D. Separate the application server and the database server by using different subnets and network security groups within the same VPC
    - E. Set up an AWS Direct Connect connection with a private VIF between the company's on-premises network and AWS
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: CD

</details> 
15. A company is running its SAP workload on AWS The company's security team has implemented the following requirements
• All Amazon EC2 instances for SAP must be SAP certified instance types
- Encryption must be enabled for all Amazon S3 buckets and Amazon Elastic Block Store (Amazon EBS) volumes
• AWS CloudTrail must be activated
• SAP system parameters must be compliant with business rules
• Detailed monitoring must be enabled for all instances
The company wants to develop an automated process to review the systems for compliance with the security team's requirements. The process also must provide notification about any deviation from these standards Which solution will meet
these requirements''
    - A. Use AWS AppConfig to model configuration data in an AWS Systems Manager Automation runbook Schedule this Systems Manager Automation runbook to monitor for compliance with all the requirements integrate AWS AppConfig with
Amazon CloudWatch for notification purposes
    - B. Use AWS Config managed rules to monitor for compliance with all the requirements Use Amazon EventBridge (Amazon CloudWatch Events) and Amazon Simple Notification Service (Amazon SNS) for email notification when a resource
is flagged as noncompliant
    - C. Use AWS Trusted Advisor to monitor for compliance with all the requirements Use Trusted Advisor preferences for email notification when a resource is flagged as noncompliant
    - D. Use AWS Config managed rules to monitor for compliance with the requirements except for the SAP system parameters Create AWS Config custom rules to validate the SAP system parameters Use Amazon EventBridge (Amazon
CloudWatch Events) and Amazon Simple Notification Sen/ice (Amazon SNS) for email notification when a resource is flagged as noncompliant
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
16. A company is hosting its SAP workloads on AWS An SAP solutions architect is designing high availability architecture for the company's production SAP S4HANA and SAP BW-4HANA workloads These workloads have the following
requirements.
• Redundant SAP application servers that consist of a primary application server (PAS) and an additional application server (AAS)
• ASCS and ERS instances that use a failover cluster
• Database high availability with a primary DB Instance and a secondary OB instance How should the SAP solutions architect design the architecture to meet these requirements?
    - A. Deploy ASCS and ERS cluster nodes in different subnets within the same Availability Zone Deploy the PAS instance and AAS instance in different subnets within the same Availability Zone Deploy the primary DB instance and secondary
DB instance m different subnets within the same Availability Zone Deploy all the components in the same VPC
    - B. Deploy ASCS and ERS duster nodes m different subnets within the same Availability Zone Deploy the PAS instance and AAS instance in different subnets within the same Availably Zone Deploy the primary DB instance and secondary
DB instance m different subnets within the same Availability Zone Deploy the ASCS instance PAS instance and primary DB instance in one VPC Deploy the ERS instance AAS instance and secondary DB instance in a different VPC
    - C. Deploy ASCS and ERS cluster nodes in different subnets across two Availability Zones Deploy the PAS instance and AAS instance m different subnets across two Availability Zones Deploy the primary DB instance and secondary DB
instance in different subnets across two Availability Zones Deploy all the components m the same VPC
    - D. Deploy ASCS and ERS cluster nodes in different subnets across two Availability Zones Deploy the PAS instance and AAS instance m different subnets across two
    - E. Availability Zones Deploy the primary DB instance and secondary DB instance in different subnets across two Availability Zones Deploy the ASCS instance PAS instance and primary DB instance in one VPC Deploy the ERS instance AAS
instance and secondary DB instance in a different VPC
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details>
17. A company has deployed SAP HANA m the AWS Cloud. The company needs its SAP HAN A database to be highly available An SAP solutions architect has deployed the SAP HANA database in separate Availability Zones in a single AWS
Region SUSE Linux Enterprise High Availability Extension is configured with an overlay IP address. The overlay IP resource agent has the following IAM policy:
During a test of failover the SAP solutions architect finds that the overlay IP address does not change to the secondary Availability Zone Which change should the SAP solutions architect make in the policy statement for Sid oip1 to dx this
error1?
    - A. Change the Action element to ec2 CreateRoute
    - B. Change the Action element to ec2 ReplaceRoute
    - C. Change the Action element to ec2 ReplaceRouteTableAssociation
    - D. Change the Action element to ec2 ReplaceTransrtGatewayRoute
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details> 
18. A company wants to improve the RPO and RTO for its SAP disaster recovery (DR) solution by running the DR solution on AWS The company is running SAP ERP Central Component (SAP ECO on SAP HANA The company has set an RPO
of 15 minutes and an RTO of 4 hours.
The production SAP HANA database is running on a physical appliance that has x86 architecture. The appliance has 1 TB of memory and the SAP HANA global allocation limit is set to 768 G    - B. The SAP application servers are running as
VMs on VMware and they store data on an NFS file system The company does not want to change any existing SAP HANA parameters that are related to data and log backup for its on-premises systems.
What should an SAP solutions architect do to meet the DR objectives MOST cost-effectively?
    - A. For the SAP HANA database change the log backup frequency to 5 minutes Move the data and log backups to Amazon S3 by using the AWS CLI or AWS DataSync Launch the SAP HANA database For the SAP application servers,
export the VMs as AMis by using the VM import/Export feature from AWS For NFS file shares/sapmnt and usr-sap/trans/ establish realtime synchronization from DataSync to Amazon Elastic File System (Amazon EFS)
    - B. For the SAP HANA database change the log backup frequency to 5 minutes Move the data and log backups to Amazon S3 by using AWS Storage Gateway File Gateway For the SAP application servers export the VMs as AMIs by using
the VM Import'Export feature from AWS For NFS file shares/sapmnt and 'usr saplrans establish realtime synchronization from AWS DataSync to Amazon Elastic Foe System (Amazon EFS)
    - C. For the SAP HANA database SAP application servers and NFS Me shares use CloudEndure Disaster Recovery to replicate the data continuously from on premises to AWS Use CloudEndure Disaster Recovery to launch target instances in
the event of a disaster
    - D. For the SAP HANA database use a smaller SAP certified Amazon EC2 instance Use SAP HANA system replication with ASYNC replication mode to replicate the data continuously from on premises to AWS For the SAP application
servers use CloudEndure Disaster Recovery for continuous data replication For NFS file shares sapmnt and .'uv-sap'trans. establish real-time synchronization from AWS DataSync to Amazon Elastic File System (Amazon EFS)
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details>
19. A company is planning to migrate its on-premises SAP applications to AWS. The applications are based on Windows operating systems A file share stores the transport directories and third party application data on the network attached
storage of the company's on-premises data center. The company's plan is to lift and shift the SAP applications and the file share to AWS. The company must follow AWS best practices for the migration Which AWS service should the
company use to host the transport directories and third-party application data on AWS?
    - A. Amazon Elastic Block Store (Amazon EBS)
    - B. AWS Storage Gateway
    - C. Amazon Elastic File System (Amazon EFS)
    - D. Amazon FSx for Windows File Server
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 
20. A company hosts an SAP HANA database on an Amazon EC2 instance in the us-easi-1 Region. The company needs to implement a disaster recovery (DR) site in the us-west-1 Region. The company needs a cost-optimized solution that
offers a guaranteed capacity reservation an RPO of less than 30 minutes and an RTO of less than 30 minutes.
When solution will meet these requirements?
    - A. Deploy a single EC2 instance to support the secondary database in us-west with additional storage Use this secondary database instance to support QA and production Configure the primary SAP HANA database in us-east-1 to constantly
replicate the data to the secondary SAP HANA database in us-west-t by using SAP HANA system replication with preload off During DR shut down the QA SAP HANA instance and restart the production services at the secondary site
    - B. Deploy a secondary staging server on an EC2 instance in us-west-1 Use CloudEndure Disaster Recovery to replicate changes at the database level from us-east-1 to the secondary staging server on an ongoing basis During DR, initiate
cutover increase the size of the secondary EC2 instance to match the primary EC2 instance and start the secondary EC2 instance
    - C. Set up the primary SAP HANA database in us-east-1 to constantly replicate the data to a secondary SAP HANA database in us-west-1 by using SAP HANA system replication with preload on Keep the secondary SAP HANA instance as a
hot standby that rs ready to take over in case of failure
    - D. Create an SAP HANA database AMI by using Amazon Elastic Block Store (Amazon EBS) snapshots Replicate the database and log backup files from a primary Amazon S3 bucket in us-east-1 to a secondary S3 bucket m us-west-1
During DR launch the EC2 instance in us-west-1 based on AMIs that are replicated Update host information Download database and log backups from the secondary S3 bucket Perform a point-in-time recovery
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
21. An SAP solutions architect is leading the SAP basis team for a company. The company's SAP landscape includes SAP HANA database instances for the following systems sandbox development quality assurance test {QAT} system
performance test (SPT) and production. The sandbox development and OAT systems are running on Amazon EC2 On-Demand Instances. The SPT and production systems are running on EC2 Reserved Instances All the EC2 instances are
using Provisioned IOPS SSO (K)2) Amazon Elastic Block Store (Amazon EBS) volumes.
The entire development learn is in the same time zone and works from 8 AM to 6 PM. The sandbox system is for research and testing that are not critical. The SPT and production systems are business critical The company runs load-testing
jobs and stress-testing jobs on the QAT systems overnight to reduce testing duration. The company wants to optimize infrastructure cost for the existing AWS resources.
How can the SAP solutions architect meet these requirements with the LEAST amount of administrative effort?
    - A. Use a Spot Fleet instead of the Reserved Instances and On-Demand Instances
    - B. Use Amazon EventBridge (Amazon CloudWatch Events) and Amazon CloudWatch alarms to stop the development and sandbox EC2 instances from 7 PM every night to 7 AM the next day
    - C. Make the SAP basis team available 24 hours a day 7 days a week to use the AWS CLi to stop and start the development and sandbox EC2 instances manually
    - D. Change the EBS volume type to Throughput Optimized HDD (sti) for the /hana/data and nana, log file systems for the production and non-production SAP HANA databases
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
22. A company is hosting an SAP HANA database on AWS. The company is automating operational tasks including backup and system refreshes. The company wants to use SAP HANA Studio to perform data backup of an SAP HANA tenant
database to a backint interface. The SAP HANA database is running in multi-tenant database container (MDO mode. The company receives the following error message during an attempt to perform the backup.
What should an SAP solutions architect do to resolve this issue?
    - A. Set the execute permission for AWS Backint agent binary aws-backint-agent and for the launcher script aws-backint-agent-launcher sh in the installation directory
    - B. Verify the installation steps Create symbolic links (symlinks)
    - C. Ensure that the cataiog_backup_using_backint SAP HANA parameter is set to true Ensure that the data_backup_parameter_file and log_backup_parameter_file parameters have the correct path location in the global ini file
    - D. Add the SAP HANA system to SAP HANA Studio Select multiple container mode and then try to initiate the backup again
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
23. A company is planning to migrate its on-premises SAP ERP Central Component (SAP ECC) system on SAP HANA to AWS Each month the system experiences two peaks in usage. The first peak is on the 21st day of the month when the
company runs payroll. The second peak is on the last day of the month when the company processes and exports credit data Both peak workloads are of high importance and cannot be rescheduled The current SAP ECC system has six
application servers an of a similar size. During normal operation outside of peak usage four application servers would suffice Which purchasing option will meet the company's requirements MOST cost-effectively on AWS?
    - A. Four Reserved Instances and two Spot Instances
    - B. Six On-Demand Instances
    - C. Six Reserved Instances
    - D. Four Reserved Instances and two On-Demand Instances
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 
24. A company hosts its SAP NetWeaver workload on SAP HANA m the AWS Cloud The SAP NetWeaver application is protected by a cluster solution that uses Red Hat Enterprise Linux High Availability Add- On The duster solution uses an
overlay IP address to ensure that the high availability cluster is still accessible during failover scenarios.
An SAP solutions architect needs to facilitate the network connection to this overlay IP address from multiple locations These locations include more than 25 VPCs other AWS Regions and the onpremises environment The company already
has set up an AWS Direct Connect connection between the on-premises environment and AWS.
What should the SAP solutions architect do to meet these requirements in the MOST scalable manner?
    - A. Use VPC peering between the VPCs to route traffic between them
    - B. Use AWS Transit Gateway to connect the VPCs and on-premises networks together
    - C. Use a Network Load Balancer to route connections to various targets within VPCs
    - D. Deploy a Direct Connect gateway to connect the Direct Connect connection over a private VIF to one or more VPCs in any accounts
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
25. A company is implementing SAP HANA on AWS According 10 the company's security policy SAP backups must be encrypted Only authorized team members can have the ability to decrypt the SAP backups What is the MOST operationally
efficient solution that meets these requirements?
    - A. Configure AWS Backint Agent for SAP HANA to create SAP backups in an Amazon S3 bucket After a backup is created encrypt the backup by using client-side encryption Share the encryption key with authorized team members only
    - B. Configure AWS Backint Agent for SAP HANA to use AWS Key Management Service (AWS KMS) for SAP backups Create a key policy to grant decryption permission to authorized team members only
    - C. Configure AWS Storage Gateway to transfer SAP backups from a file system to an Amazon S3 bucket Use an S3 bucket policy to grant decryption permission to authorized team members only
    - D. Configure AWS Backint Agent for SAP HANA to use AWS Key Management Service (AWS KMS) for SAP backups Grant object ACL decryption permission to authorized team members only
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 
26. A data analysis company has two SAP landscapes that consist of sandbox development QA, preproduction and production servers. One landscape is on Windows and the other landscape is on Red Hat Enterprise Linux. The servers reside in
a room m a building that other tenants share.
An SAP solutions architect proposes to migrate the SAP applications to AWS The SAP solutions architect wants to move the production backups to AWS and wants to make the backups highly available to restore >n case of unavailability of
an on-premises server.
Which solution will meet these requirements MOST cost-effectively?
    - A. Take a backup of the production servers Implement an AWS Storage Gateway Volume Gateway Create file shares by using the Storage Gateway Volume Gateway Copy the backup files to the file shares through NFS and 9MB.
    - B. Take a backup of the production servers Send those backups to tape drives implement an AWS Storage Gateway Tape Gateway Send the backups to Amazon S3 Standard-Infrequent Access (S3 Standard-IA) through the S3 console
Move the backups immediately to S3 Glacier Deep Archive
    - C. Implement a third-party tool to take images of the SAP application servers and database server Take regular snapshots at 1-hour intervals send the snapshots to Amazon S3 Glacier directly through the S3 Glacier console Store the same
images in different S3 buckets in different AWS Regions
    - D. Take a backup of the production servers Implement an Amazon S3 File Gateway Create file shares by using the S3 File Gateway Copy the backup files lo the file shares through NFS and SMB Map backup files directly to Amazon S3
Configure an S3 Lifecycle policy to send the backup files to S3 Glacier based on the company's data retention policy
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 
27. A company's SAP basis team is responsible for database backups in Amazon S3. The company frequently needs to restore the last 3 months of backups into the pre-production SAP system to perform tests and analyze performance.
Previously an employee accidentally deleted backup files from the S3 bucket. The SAP basis team wants to prevent accidental deletion of backup files in the future.
Which solution will meet these requirements?
    - A. Create a new resource-based policy that prevents deletion of the S3 bucket
    - B. Enable versioning and multi-factor authentication (MFA) on the S3 bucket
    - C. Create signed cookies for the backup files in the S3 bucket Provide the signed cookies to authorized users only
    - D. Apply an S3 Lifecycle policy to move the backup fries immediately to S3 Glacier
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
28. An SAP solutions architect is designing an SAP HANA scale-out architecture for SAP Business Warehouse (SAP BW) on SAP HANA on AWS. The SAP solutions architect identifies the design as a three-node scale out deployment of x1e
32xlarge Amazon EC2 instances The SAP solutions architect must ensure that the SAP HANA scale-out nodes can achieve the lowlatency and high-throughput network performance that are necessary for node-to-node communication Which
combination of steps should the SAP solutions architect take to meet these requirements?
(Select TWO.)
    - A. Create a cluster placement group Launch the instances into the cluster placement group
    - B. Create a spread placement group Launch the instances into the spread placement group
    - C. Create a partition placement group Launch the instances into the partition placement group
    - D. Based on the operating system version verify that enhanced networking is enabled on all the nodes
    - E. Switch to a different instance family that provides network throughput that is greater than 25 Gbps
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: CE

</details> 
29. A company needs to migrate its critical SAP workloads from an on-premises data center to AWS The company has a few source production databases that are 10 TB or more in size The company wants to minimize the downtime for this
migration As part of the proof of concept the company used a low-speed high-latency connection between its data center and AWS During the actual migration the company wants to maintain a consistent connection that delivers high
bandwidth and low latency. The company also wants to add a layer of connectivity resiliency. The backup connectivity does not need to be as fast as the primary connectivity An SAP solutions architect needs to determine the optimal network
configuration for data transfer.
The solution must transfer the data with minimum latency
Which configuration will meet these requirements?
    - A. Set up one AWS Direct Connect connection for connectivity between the on-premises data center and AWS Add an AWS Site-to-Site VPN connection as a backup to the Direct Connect connection
    - B. Set up an AWS Direct Connect gateway with multiple Direct Connect connections that use a link aggregation group (LAG) between the on-premises data center and AWS
    - C. Set up Amazon Elastic fie System (Amazon EPS) file system storage between the on-premises data center and AWS Configure a cron job to copy the data into this EFS mount Access the data in the EFS file system from the target
environment
    - D. Set up two redundant AWS Site-to-Site VPN connections for connectivity between the on-premises data center and AWS
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
30. A company wants 10 migrate its SAP ERP landscape to AWS The company will use a highly available distributed deployment for the new architecture Clients will access SAP systems from a local data center through an AWS Site-to-Site
VPN connection that is already in place An SAP solutions architect needs to design the network access to the SAP production environment Which configuration approaches will meet these requirements? (Select TWO.)
    - A. For the ASCS instance configure an overlay IP address that is within the production VPC ClDR range Create an AWS Transit Gateway Attach me VPN to the transit gateway Use the transit gateway to route the communications between
the local data center and the production VPC Create a static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance
    - B. For the ASCS instance configure an overlay IP address that is outside the production VPC ClDR range Create an AWS Transit Gateway Attach the VPN to the transit gateway Use the transit gateway to route the communications between
the local data center and the production VPC Create a static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance
    - C. For the ASCS instance configure an overlay IP address that is within the production VPC ClDR range Create a target group that points to the overlay IP address Create a Network Load Balancer and register the target group Create a static
route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance
    - D. For the ASCS instance configure an overlay IP address that is outside the production VPC ClDR range Create a target group that points to the overlay IP address Create a Network Load Balancer, and register the target group Create a
static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance
    - E. For the ASCS instance configure an overlay IP address that is outside the production VPC ClDR range Create a target group that points to the overlay IP address Create an Application Load Balancer and register the target group Create a
static route on the production VPC to route traffic that is directed to the overlay IP address to the ASCS instance.
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: AB

</details> 
31. A company is running an SAP HANA database on AWS The company is running AWS Backint Agent for SAP HANA(AWS Backint agent) on an Amazon EC2 instance AWS Back agent is configured to back up to an Amazon S3 bucket The
backups are failing with an AccessDeniod error m the AWS Backint agent log file.
What should an SAP basis administrator do to resolve this error?
    - A. Assign execute permissions at the operating system level for the AWS Backint agent binary and for AWS Backint agent
    - B. Assign an 1AM role to an EC2 instance Attach a policy to the IAM role to grant access to the target S3 bucket
    - C. Assign the correct Region ID for the S3BucketAwsRegion parameter in AWS Backint agent for the SAP HANA configuration file
    - D. Assign the value for the Enable Tagging parameter in AWS Backint agent for the SAP HANA configuration file
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
32. A company is using SAP NetWeaver with Java on AWS The company has updated its generation of Amazon EC2 instances to the most recent generation of EC2 instances When the company tries to start SAP the startup fails The tog
indicates that the SAP license expired Of is not valid.
What is the reason for this issue?
    - A. The instance ID changed as part of the EC2 generation change
    - B. The instance's hypervisor changed from Xen to Nitro
    - C. The SAP Java Virtual Machine (SAP JVM) is not compatible with the new instance type
    - D. An EC2 generation change is not supported for SAP Java-based systems
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details> 
33. A company's basis administrator is planning to deploy SAP on AWS m Linux. The basis administrator must set up the proper storage to store SAP HANAdata and log volumes. Which storage options should the basis administrator choose to
meet these requirements? (Select TWO.)
    - A. Amazon Elastic Block Store (Amazon EBS) Throughput Optimized HDD (st1)
    - B. Amazon Elastic Block Store (Amazon EBS) Provisioned IOPS SSD (io1, k>2)
    - C. Amazon S3
    - D. Amazon Elastic File System (Amazon EFS>
    - E. Amazon Elastic Block Store (Amazon EBS) General Purpose SSD (gp2 gp3)
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: CD

</details> 
34. A company has deployed a highly available SAP NetWeaver system on SAP HANA into a VPC The system is distributed across multiple Availability Zones within a single AWS Region SAP NetWeaver is running on SUSE Linux Enterprise
Server for SAP SUSE Linux Enterprise High Availability Extension is configured to protect SAP ASCS and ERS instances and uses the overlay IP address concept The SAP shared dies sapmnt and . usrsap. trans are hosted on an Amazon
Elastic File System (Amazon EFS) tile system The company needs a solution that uses already-existing private connectivity to the VP    - C. The SAP NetWeaver system must be accessible through the SAP GUI client tool.
Which solutions will meet these requirements? (Select TWO)
    - A. Deploy an Application Load Balancer Configure the overlay IP address as a target
    - B. Deploy a Network Load Balancer Configure the overlay IP address as a target
    - C. Use an Amazon Route 53 private zone Create an A record that has the overlay IP address as a target
    - D. Use AWS Transit Gateway Configure the overlay IP address as a static route in the transit gateway route table Specify the VPC as a target
    - E. Use a NAT gateway Configure the overlay IP address as a target
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: BC

</details> 
35. A company is planning to move all its SAP applications to Amazon EC2 instances in a VPC Recently the company signed a multiyear contract with a payroll software-as-a-service (SaaS) provider integration with the payroll SaaS solution is
available only through public web APIs.
Corporate security guidelines state that all outbound traffic must be validated against an allow list.
The payroll SaaS provider provides only fully qualified domain name (FQDN) addresses and no IP addresses or IP address ranges Currently, an on-premises firewall appliance filters FQDNs. The company needs to connect an SAP Process
Orchestration (SAP PO) system to the payroll SaaS provider.
What must the company do on AWS to meet these requirements?
    - A. Add an outbound rule to the security group of the SAP PO system to allow the FODN of the payroll SaaS provider and deny all other outbound traffic
    - B. Add an outbound rule to the network ACL of the subnet that contains the SAP PO system to allow the FQDN of the payroll SaaS provider and deny all other outbound traffic
    - C. Add an AWS WAF web ACL to the VPC Add an outbound rule to allow the SAP PO system to connect to the FQDN of the payroll SaaS provider
    - D. Add an AWS Network Firewall firewall to the VPC Add an outbound rule to allow the SAP PO system to connect to the FQDN of the payroll SaaS provider
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
36. A company is planning to migrate its on-premises SAP application to AWS. The application runs on VMware vSphere The SAP ERP Central Component (SAP ECC) server runs on an IBM Db2 database that is 2 TB m size The company
wants to migrate the database to SAP HANA Which migration strategy will meet these requirements'?
    - A. Use AWS Application Migration Service (CloudEndure Migration)
    - B. Use SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move
    - C. Use AWS Server Migration Service (AWS SMS)
    - D. Use AWS Database Migration Service (AWS DMS)
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
37. A company hosts multiple SAP applications on Amazon EC2 instances in a VPC While monitoring the environment the company notices that multiple port scans are attempting to connect to SAP portals inside the VP    - C. These port scans are
originating from the same IP address block. The company must deny access to the VPC from all the offending IP addresses for the next 24 hours.
Which solution win meet this requirement?
    - A. Modify network ACLs that are associated with all public subnets in the VPC to deny access from the IP address block
    - B. Add a rule in the security group of the EC2 instances to deny access from the IP address block
    - C. Create a policy in AWS identity and Access Management (1AM) to deny access from the IP address block
    - D. Configure the firewall m the operating system of the EC2 instances to deny access from the IP address block
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 
38. A company has deployed SAP workloads on AWS The AWS Data Provider for SAP is installed on the Amazon EC2 instance where the SAP application is running An SAP solutions architect has attached an IAM role to the EC2 instance with
the following policy.
The AWS Data Provider for SAP is not returning any metrics to the SAP application. Which change should the SAP solutions architect make to the 1AM permissions to resolve this issued.
    - A. Add the cloudwatch ListMetrics action to the policy statement with Sid AWSDataProvider1.
    - B. Add the cloudwatch GetMetricStatrstics action to the policy statement with Sid AWSDataProvider1
    - C. Add the cloudwatch GetMetricStream action (o the policy statement with Sid AWSDataProvider
    - D. Add the cloudwatch DescribeAlarmsForMetric action to the policy statement with Sid AWSDataProvider
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
39. A company wants to deploy an SAP HANA database on AWS by using AWS Launch Wizard for SAP An SAP solutions architect needs to run a custom post-deployment script on the Amazon EC2 instance that Launch Wizard provisions.
Which actions can the SAP solutions architect take to provide the post-deployment script m the Launch Wizard console? (Select TWO.)
    - A. Provide the FTP URL of the script
    - B. Provide the HTTPS URL of the script on a web server
    - C. Provide the Amazon S3 URL of the script
    - D. Write the script inline
    - E. Upload the script
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: DE

</details> 
40. A company has an SAP environment that runs on AWS. The company wants to enhance security by restricting Amazon EC2 Instance Metadata Service (IMDS) to IMDSv2 only. The company's current configuration option supports both
iMDSvi and iM0Sv2. The security enhancement must not create an SAP outage.
What should the company do before it applies the security enhancement on EC2 instances that are running the SAP environment?
    - A. Ensure that the SAP kernel versions are 7 45 or later
    - B. Ensure that the EC2 instances are Nitro based
    - C. Ensure that the AWS Data Provider for SAP is installed on each EC2 instance
    - D. Stop the EC2 instances
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
41. A company is running an SAP HANA database on AWS. The company wants to manage historical infrequently accessed warm data for a native SAP HANA use case An SAP solutions architect needs to recommend a solution that can
provide online data storage m extended store available for queries and updates. The solution must be an integrated component of the SAP HANA database and must allow the storage of up to five limes more data in the warm tier than in the
not tier Which solution will meet these requirements?
    - A. Use Amazon Data lifecycle Manager (Amazon DLM) with SAP Data Hub to move data in and out of the SAP HANA database to Amazon S3
    - B. Use an SAP HANA extension node
    - C. Use SAP HANA dynamic tiering as an optional add-on to the SAP HANA database
    - D. Use Amazon Data Lifecycle Manager (Amazon DLM) with SAP HANA spark controller so that SAP HANA can access the data through the Spark SQL SDA adapter
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
42. A company plans to migrate its SAP NetWeaver deployment to AWS. The deployment runs on a Microsoft SQL Server database. The company plans to change the source database from SQL Server to SAP HANA as part of this process.
Which migration tools or methods should an SAP solutions architect use to meet these requirements'' (Select TWO. )
    - A. SAP HANA classical migration
    - B. SAP HANA system replication
    - C. SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move
    - D. SAP HANA backup and restore
    - E. SAP homogeneous system copy
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: CD

</details> 
43. A company has an SAP Business One system that runs on SUSE Linux Enterprise Server 12 SP3. The company wants to migrate the system to AWS An SAP solutions architect selects a homogeneous migration strategy that uses AWS
Application Migration Service (CloudEndure Migration) After the server migration process is finished the SAP solutions architect launches an Amazon EC2 test instance from the R5 instance family. After a few minutes the EC2 console
reports that the test instance has failed an instance status check Network connections to the instance are refused How can the SAP solutions architect solve this problem?
    - A. Reboot the instance to initiate instance migration to another host
    - B. Request an instance limit increase for the AWS Region where the test instance is being launched
    - C. Create a ticket for AWS Support that documents the test server instance ID Wait for AWS to update the host of the R5 instance
    - D. Install the missing drivers on the source system Wait for the completion of migration synchronization Launch the test instance again
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
44. An SAP basis architect is configuring high availability for a critical SAP system on AWS. The SAP basis architect is using an overlay IP address to route traffic to the subnets across multiple Availability Zones within an AWS Region for the
system's SAP HANA database.
What should the SAP basis architect do to route the traffic to the Amazon EC2 instance of the active SAP HANA database?
    - A. Edit the route in the route table of the VPC that includes the EC2 instance that runs SAP HANA Specify the overlay IP address as the destination Specify the private IP address of the EC2 instance as the target
    - B. Edit the inbound and outbound rules in the security group of the EC2 instance that runs SAP HANA Allow traffic for SAP HANA specific ports from the overlay IP address
    - C. Edit the network ACL of the subnet that includes the EC2 instance that runs SAP HANA Allow traffic for SAP HANA specific ports from the overlay IP address
    - D. Edit the route in the route table of the VPC that includes the EC2 instance that runs SAP HANA Specify the overlay IP address as the destination Specify the elastic network interface of the EC2 instance as the target
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
45. A company is running SAP ERP Central Component (SAP ECC) with a Microsoft SQL Server database on AWS A solutions architect must attach an additional 1 TB Amazon Elastic Block Store (Amazon EBS) volume. The company needs
to write the SQL Server database backups to this EBS volume before moving the database backups to Amazon S3 for long-term storage.
Which EBS volume type will meet these requirements MOST cost-effectively?
    - A. Throughput Optimized HDD (st1)
    - B. Provisioned IOPS SSD (io3)
    - C. General Purpose SSD (gp3)
    - D. Cold HDD (sc1)
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details> 
46. An SAP technology consultant needs to scale up a primary application server (PAS) instance The PAS currently runs on a c5a.xlarge Amazon EC2 instance The SAP technology consultant needs to change the instance type to c5a 2xlarge
How can the SAP technology consultant meet this requirement?
    - A. Stop the complete SAP system Stop the EC2 instance Use the AWS Management Console or the AWS CLI to change the instance type Start the EC2 instance Start the complete SAP system
    - B. While SAP is running use the AWS Management Console or the AWS CLI to change the instance type without stopping the EC2 instance
    - C. Stop the complete SAP system Terminate the EC2 instance Use the AWS Management Console or the AWS CLI to change the instance type Start the EC2 instance Start the complete SAP system
D.
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details> 
47. A company has moved an of its SAP workloads to AWS During peak business hours end users are reporting performance issues because work processes are going into PRIV mode on an SAP S/4HANA system An SAP support engineer
indicates that SAP cannot provide support for this issue because some specific performance metrics are not available.
Which combination of actions must the company perform to comply with SAP support requirements? (Select THREE.)
    - A. Buy an SAP license from AWS Ensure that the SAP license is installed
    - B. Select only an AWS Migration Acceleration Program (MAP) certified managed service provider (MSP)
    - C. Enable detailed monitoring for Amazon CloudWatch on each Amazon EC2 instance where SAP workloads are running
    - D. Install configure and run the AWS Data Provider for SAP on each Amazon EC2 instance where SAP workloads are running
    - E. integrate AWS Systems Manager with SAP Solution Manager to provide alerts about SAP parameter configuration drift
    - F. Enable SAP enhanced monitoring through a SAPOSCOL enhanced function
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: ABC

</details> 
48. A company needs to implement high availability for its SAP S 4HANA system on AWS The company will use a SUSE Linux Enterprise Server clustering solution in private subnets across two Availability Zones An SAP solutions architect
must ensure that the solution can route traffic to the active SAP instance m this clustered configuration.
What should the SAP solutions architect do to meet these requirements?
    - A. Implement the SAP cluster solution by using a secondary private IP address Reassign the secondary private IP address from one network interface to another network interface in the event of any failure that affects the primary instance.
    - B. Implement the SAP cluster solution by using an Elastic IP address Mask the failure of an instance or software by rapidly remapping the address to another instance in the account
    - C. Implement the SAP duster solution by using a public IP address Use this public IP address for communication between the instances and the internet
    - D. implement the SAP duster solution by using an overlay IP address that is outside the CIDR block of the VPC Use overlay IP address routing to dynamically update the route table to point to the active node and provide external access by
using a Network Load Balancer or AWS Transit Gateway.
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
49. A company is migrating its SAP workloads to AWS The company's IT team installs a highly available SAP S.4HANA system that uses the SAP HANA system replication cluster package on SUSE Linux Enterprise Server The IT team deploys
the system by using cluster nodes m different Availability Zones within the same AWS Region.
After the initial launch of the SAP application the application is accessible However after failover the IT team cannot access the application even though the system is up and running on the secondary node After investigation an SAP
solutions architect discovers that the virtual IP address has not been used correctly Which combination of steps should the SAP solutions architect take to resolve this problem? (Select TWO.)
    - A. Use an overlay IP address as a secondary IP address with the primary node of the cluster
    - B. Choose an overlay IP address within the VPC CiDR block that corresponds with the secondary node of the cluster
    - C. Use an overlay IP address as a virtual IP address
    - D. Choose an overlay IP address within the VPC CIDR block that corresponds with the primary node of the cluster
    - E. Choose an overlay IP address outside the VPC CiDR block that hosts the application and the database
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: AD

</details> 
50. A company wants to migrate its on-premises servers to AWS. These servers include SAP ERP Central Component (SAP ECC) on Oracle Database. The company is running SAP ECC application servers and Oracle Database servers on
AIX. The company must migrate the SAP workloads to AWS with minimal changes.
Which solution will meet these requirements?
    - A. Perform a heterogeneous migration for SAP on AWS Specify the SAP ECC application servers to run on SUSE Linux Enterprise Server Specify Oracle Database to run on Oracle Enterprise Linux on a Dedicated Host
    - B. Perform a homogeneous migration for SAP on AWS Specify the SAP ECC application servers and Oracle Database to run on AIX
    - C. Perform a heterogeneous migration for SAP on AWS Specify the SAP ECC application servers and Oracle Database to run on Oracle Enterprise Linux.
    - D. Perform a heterogeneous migration for SAP on AWS Specify the SAP ECC application servers and Oracle Database to run on Windows.
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
51. A company has deployed its SAP applications into multiple Availability Zones in the same AWS Region To accommodate storage of media files database table export and import and files dropped by third-party tools the company has
mounted Amazon Elastic File System (Amazon EFS) file systems between the SAP instances The company needs to retrieve the files quickly for installations updates and system refreshes Over time the EFS file systems have grown
exponentially to multiple terabytes An SAP solutions architect must optimize storage cost for the tiles that are stored in Amazon EFS.
Which solution will meet this requirement with the LEAST administrative overhead?
    - A. Scan the files manually to identify unnecessary files Delete the unnecessary files
    - B. Move the files to Amazon S3 Glacier Deep Archive
    - C. Apply a lifecycle policy on the files in Amazon EFS to move the files to EFS Standard-Infrequent Access (Standard-IA)
    - D. Move the files to Amazon S3 Glacier Apply an S3 Glacier vault lock policy to the files
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 
52. An SAP specialist is budding an SAP environment The SAP environment contains Amazon EC2 instances that fun in a private subnet in a VP    - C. The VPC includes a NAT gateway.
The SAP specialist is selling up IBM Db2 high availability disaster recovery for the SAP duster. After configuration of overlay IP address routing traffic is not routing to the database EC2 instances.
What should the SAP specialist do to resolve this issue?
    - A. Open a security group tor SAP ports »o allow traffic on port 443
    - B. Create route table entries to allow traffic from the database EC2 instances to the NAT gateway
    - C. Turn off the source destination check for the database EC2 instances
    - D. Create an IAM role that has permission to access network traffic Associate the role with the database EC2 instances
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details> 
53. A company uses an SAP application that runs batch jobs that ate performance sensitive. The batch jobs can be restarted safely The SAP application has sot application servers. The SAP application functions reliability as long as the SAP
application availability remains greater than 60%. The company wants to migrate the SAP application to AWS. The company is using a duster with two Availability Zones How should the company distribute the SAP application servers to
maintain system reliability?
    - A. Distribute the SAP application servers equally across three partition placement groups
    - B. Distribute the SAP application servers equally across three Availability Zones
    - C. Distribute the SAP application servers equally across two Availability Zones
    - D. Create an Amazon EC2 Auto Scaling group across two Availability Zones Set a minimum capacity value of 4.
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details> 
54. A company wants to migrate its SAP landscape from on premises to AWS
What are the MINIMUM requirements that the company must meet to ensure full support of SAP on AWS? (Select THREE.)
    - A. Enable detailed monitoring for Amazon CloudWatch on each instance in the landscape
    - B. Deploy the infrastructure by using SAP Cloud Appliance Library
    - C. Install configure and run the AWS Data Provider for SAP on each instance m the landscape
    - D. Protect all production instances by using Amazon EC2 automatic recovery
    - E. Deploy the infrastructure for the SAP landscape by using AWS Launch Wizard for SAP
    - F. Deploy the SAP landscape on an AWS account that has either an AWS Business Support plan or an AWS Enterprise Support plan
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: BCF

</details> 
55. A company wants to migrate its SAP S/4HANA software from on premises to AWS in a few weeks An SAP solutions architect plans to use AWS Launch Wizard for SAP to automate me SAP deployment on AWS Which combination of steps
must the SAP solutions architect take to use Launch Wizard to meet these requirements? (Select TWO.)
    - A. Download the SAP software files from the SAP Support Portal Upload the SAP software files to Amazon S3 Provide the S3 bucket path as an input to Launch Wizard
    - B. Provide the SAP S-user ID and password as inputs to Launch Wizard to download the software automatically.
    - C. Format the S3 Tile path syntax according to the Launch Wizard deployment recommendation
    - D. Use an AWS CloudFormation template for the automated deployment of the SAP landscape
    - E. Provision Amazon EC2 instances Tag the instances to install SAP S'4HANA on them
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: AD

</details> 
56. A company runs its SAP ERP 6 0 EHP 8 system on SAP HANAon AWS The system is deployed on an r4 I6xlarge Amazon EC2 instance with default tenancy. The company needs to migrate the SAP HANA database to an x2gd/.6xiarge
High Memory instance After an operations engineer changes the instance type and starts the instance the AWS Management Console shows a failed instance status check What is the cause of this problem?
    - A. The operations engineer missed the network configuration step during the post-migration activities
    - B. The operations engineer missed the Amazon CloudWatch configuration step during the postmigration activities.
    - C. The operations engineer did not install Elastic Network Adapter (ENA) drivers before changing the instance type
    - D. The operations engineer did not create a new AMI from the original instance and did not launch a new instance with dedicated tenancy from the AMI
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
57. A company is running SAP on anyDB at a remote location that has slow and inconsistent internet connectivity. The company wants to migrate its system to AWS and wants to convert its database to SAP HANA during this process Because
of the inconsistent internet connection the company has not established connectivity between the remote location and the company's VPC in the AWS Cloud.
How should the company perform this migration?
    - A. Migrate by using SAP HANA system replication over the internet connection Specify a public IP address on the target system
    - B. Migrate by using SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move Use an AWS Snowball Edge Storage Optimized device to transfer me SAP export files to AWS
    - C. Migrate by using SAP HANA system replication with initialization through backup and restore Use an AWS Snowball Edge Storage Optimized device to transfer the SAP export files to AWS
    - D. Migrate by using SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move Use Amazon Elastic File System (Amazon EPS) to transfer the SAP export files to AWS
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
58. A financial services company is implementing SAP core banking on AWS. The company must not allow any system information to traverse the public internet. The company needs to implement secure monitoring of its SAP ERP Central
Component (SAP ECO system to check for performance issues and faults in its application. The solution must maximize security and must be supported by SAP and AWS.
How should be company integrate AWS metrics with its SAP system to meet these requirements?
    - A. Set up SAP Solution Manager to call Amazon CoudWatch and Amazon EC2 endpoints with RESTbased calls to populate SAPOSCOL details Use SAP transaction ST06N to monitor CPU and memory utilization on each EC2 instance
    - B. Install the AWS Data Provider for SAP on the Amazon EC2 instances that host SAP Allow access to the Amazon CloudWatch and EC2 endpoints through a NAT gateway Create an IAM policy that allows the ec2 Describeinstances action
the cloudwatch.GetMetricStatistics action and the ec2 DescribeVolumes action for all EC2 resources.
    - C. Install the AWS Data Provider for SAP on the Amazon EC2 instances that host SAP Create VPC endpoints for Amazon CloudWatch and Amazon EC2 Allow access through these endpoints Create an IAM policy that allows the ec2
Describe instances action the cloudwatch GetMemcStatistics action and the ec2 DescribeVolumes action tor all EC2 resources.
    - D. install the AWS data Provider for SAP on the Amazon EC2 instances that host SAP Create VPC endpoints for Amazon CloudWatch and Amazon EC2 Allow access through these endpoints Create an IAM policy that allows al actions for
all EC2 resources.
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: A

</details> 
59. Business users are reporting timeouts during periods of peak query activity on an enterprise SAP HANAdata mart An SAP system administrator has discovered that at peak volume the CPU utilization increases rapidly to 100% for extended
periods on the x1.32xlarge Amazon EC2 instance where the database is installed However the SAP HANA database is occupying only 1 120 GiB of the available 1 952 GiB on the instance 10 wart times are not increasing Extensive query
tuning and system tuning have not resolved this performance problem Which solutions should the SAP system administrator use to improve the performance? (Select TWO.)
    - A. Reduce the global_allocation_limit parameter to i 120 GiB
    - B. Migrate the SAP HANA database to an EC2 High Memory instance with a larger number of available vCPUs
    - C. Move to a scale-out architecture for SAP HANA with at least three x1 16xlarge instances
    - D. Modify the Amazon Elastic Block Store (Amazon EBS) volume type from General Purpose to Provisioned lOPS for ail SAP HANA data volumes
    - E. Change to a supported compute optimized instance type for SAP HANA
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: DE

</details> 
60. A company is moving to the AWS Cloud gradually. The company has multiple SAP landscapes on VMware The company already has sandbox development and QA systems on AWS The company's production system is still running on
premises. The company has 2 months to cut over the entre landscape to the AWS Cloud The company has adopted a hybrid architecture for the next 2 months and needs to synchronize its shared file systems between the landscapes These
shared file systems include trans directory mounts, /software directory mounts, and third-party integration mounts in the on-premises landscape the company has NFS mounts between the servers On the AWS infrastructure side the company
is using Amazon Elastic File System (Amazon EFS) to share the common files An SAP solutions architect needs to design a solution to schedule transfer of these shared files bidirectional^ four times each day. The data transfer must be
encrypted Which solution will meet these requirements?
    - A. Write an rsync script Schedule the script through cron for four times each day in the on-premises VMware servers to transfer the data from on premises to AWS
    - B. Install an AWS DataSync agent on the on-premises VMware platform Use the DataSync endpoint to synchronize between the on-premises NFS server and Amazon EFS on AWS
    - C. Order an AWS Snowcone device Use the Snowcone device to transfer data between the onpremises servers and AWS
    - D. Set up a separate AWS Direct Connect connection for synchronization between the on-premises servers and AWS
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B

</details> 
61. A company is planning to move to AWS. The company wants to set up sandbox and test environments on AWS to perform proofs of concept (POCs) Development and production environments will remain on premises until the POCs are
completed.
At the company's on-premises location SAProuter is installed on the same server as SAP Solution Manager. The company uses SAP Solution Manager to monitor the entire landscape The company uses SAP router to connect to SAP
Support The on-premises SAP Solution Manager instance must monitor the performance and server metrics of the newly created POC systems on AWS. The existing SAP router must be able to report any issues to SAP What should an
SAP solutions architect do to set up this hybrid infrastructure MOST cost-effectively''
    - A. Install a new SAP Solution Manager instance and a new SAP router instance m the AWS environment Connect the POC systems to these new instances Use these new instances m parallel with the on-premises SAP Solution Manager
instance and the on-premises SAP router instance
    - B. Install a new SAP Solution Manager instance and a new SAP router instance in the AWS environment install the Amazon CloudWatch agent on all on-premises instances Push the monitoring data to the new SAP Solution Manager
instance Connect ail on-premises systems and POC systems on AWS to the new SAP Solution Manager instance and the new SAP router instance Remove the onpremises SAP Solution Manager instance and the on-premises SAP router
instance Use the new instances on AWS
    - C. Use AWS Site-to-Site VPN to connect the on-premises network to the AWS environment Connect the POC systems on AWS to the on-premises SAP Solution Manager instance and the on-premises SAP router instance
    - D. Add the POC systems on AWS to the existing SAP Transport Management System that is configured m the on-premises SAP systems
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 
62. An SAP solutions architect is using AWS Systems Manager Distributor to install the AWS Data Provider for SAP on production SAP application servers and SAP HANA database servers The SAP application servers and the SAP HANA
database servers are running on Red Hat Enterprise Linux.
The SAP solutions architect chooses instances manually m Systems Manager Distributor and schedules installation. The installation fails with an access and authorization error related to Amazon CloudWatch and Amazon EC2 instances.
There is no error related to AWS connectivity.
What should the SAP solutions architect do to resolve the error?
    - A. Install the CloudWatch agent on the servers before installing the AWS Data Provider tor SAP
    - B. Download the AWS Data Provider for SAP installation package from AWS Marketplace Use an operating system super user to install the agent manually or through a script
    - C. Create an IAM role Attach the appropriate policy to the role Attach the role to the appropriate EC2 instances
    - D. Wait until Systems Manager Agent is fully installed and ready to use on the EC2 instances Use Systems Manager Patch Manager to perform the installation
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: C

</details> 
63. A company is running its SAP applications on Oracle Database Oracle Database is hosted on physical servers that are running SUSE Linux Enterprise Server Because of compliance requirements the company cannot install any additional
software on its on premises database servers. The company needs to migrate the SAP landscape to AWS and must continue to use Oracle Database.
Which migration solution should the company use to meet these requirements?
    - A. AWS Server Migration Service (AWS SMS)
    - B. AWS Application Migration Service (CloudEndure Migration)
    - C. SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move
    - D. Oracle Database replication with Oracle Data Guard
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
64. A company is planning to migrate its SAP workloads to AWS. The company will use two VPCs One VPC will be for production systems and one VPC will be for non-production systems. The company will host the non-production systems and
the primary node of all the production systems in the same Availability Zone.
What is the MOST cost-effective way to establish a connection between me production systems and the non-production systems?
    - A. Create an AWS Transit Gateway Attach the VPCs to the transit gateway Add the appropriate routes m the subnet route tables
    - B. Establish a VPC peering connection between the two VPCs Add the appropriate routes in the subnet route tables
    - C. Create an internet gateway in each VPC Use an AWS Site-to-Site VPN connection between the two VPCs Add the appropriate routes in the subnet route tables
    - D. Set up an AWS Direct Connect connection between the two VPCs Add the appropriate routes in the subnet route tables
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: D

</details> 
65. An SAP engineer has deployed an SAP S/4HANA system on an Amazon EC2 instance mat runs Linux.
The SAP license key has been installed After a white the newly installed SAP instance presents an error that indicates that the SAP license key is not valid because the SAP system's hardware key changed. There have been no changes to
the EC2 instance or its configuration.
Which solution will permanently resolve this issue?
    - A. Perform SAP kernel patching
    - B. Apply a new SAP license that uses a new hardware key Install the new key
    - C. Set the SUC_HW_VERSlON Linux environment variable
    - D. Reboot the EC2 instance
    <details markdown=1><summary markdown='span'>Answer</summary>Correct Answer: B
</details>
Please feel free to comment below if any information is inaccurate or if any answers need correction.

[<img align="center" src="../images/list.png" height="30" width="30"/> Exam List](../practice-exam/exams.md)
