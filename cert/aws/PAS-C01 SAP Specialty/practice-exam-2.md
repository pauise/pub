# Practice Exam 2

Click on the **Answer** button for the correct answer and its explanation.

If this practice exam has been helpful to you please share it with others and react to this below.

---

## Question 1

A US-based Banking and Insurance company is running their SAP workloads on-premise. They have been maintaining their SAP backup data for the last 15 years for regulatory compliance requirements in their on-premise datacenter. The company sometimes needs to access this backup data once or twice a year during March or December month-end. The company is looking for a low-cost durable solution to store these backups on the AWS cloud. Which of the following solutions can help meet the company‘s requirements with minimum cost?
 - A. Use Amazon S3 Standard-Infrequent Access to store the SAP backups
 - B. Use Amazon S3 Glacier Instant Retrieval to store the SAP backups
 - C. Use Amazon S3 Glacier Deep Archive to store the SAP backups
 - D. Use Amazon S3 Standard to store the SAP backups

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> Glacier Deep Archive is specifically ideal for 1 or 2 retrievals per year with 12 hours from request. As stated, the company knows when these backups are needed in advance and it's only 2 times a year. All other options are more expensive.
</details>


## Question 2

A company is running their SAP workloads on-premise. They are planning to migrate their SAP BW Netweaver 7.5 landscape to AWS cloud, which is running on an Oracle database on AIX. The customer does not plan to change the underlying database for the SAP BW environment. What are the steps and best practices the company needs to perform in order to migrate the SAP BW landscape to AWS? **(Select THREE)**
 - A. Migrate the SAP BW non-production systems first to ensure that migration is successful and there are no issues with running BW workloads on AWS
 - B. Migrate all SAP BW systems together to ensure that downtime required is less and the migration project timeline can be shortened
 - C. Perform a DB migration using Software Provisioning Manager (SWPM) to change the database to HANA as Oracle is not supported on AWS for SAP
 - D. Perform an OS migration using Software Provisioning Manager (SWPM) to change the operating system to Oracle Linux as AIX is not supported on AWS for SAP
 - E. Perform an OS migration using Software Provisioning Manager (SWPM) to change the operating system to SUSE Linux Enterprise Server (SLES) as AIX is not supported on AWS for SAP
 - F. Ensure to generate a migration key from the SAP Support Portal for the migration using Software Provisioning Manager (SWPM)

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: ADF

> "Non-prod first" is the typical change management golden rule; so A is valid and B not. By other hand, Oracle DB is supported on OEL only, so the solution is then export/import to OEL keeping Oracle DB as per requirement and then no necessity to move to HANA (C and E discarded and D valid) and finally you will need a migration key (F valid).
    
</details>


## Question 3

A customer is running their SAP workloads in a Hybrid cloud model. The non-production systems are hosted on the AWS cloud and production systems are running on customers‘ on-premise datacenter. There is a Direct Connect connectivity between the on-premises datacenter and AWS cloud. The customer is planning to create a new HANA sandbox system (SBX) on the AWS cloud from the data of the production system (PRD) based on HANA 2.0 SPS 4, using the backup-restore method. Which of the following combination of steps should the customer perform to achieve the requirement? **(Select TWO)**
 - A. Launch the EC2 instance hosting the SBX system in the public subnet of VPC. Install a HANA database with a version same or higher than the version of the PRD database on this EC2 instance
 - B. Launch the EC2 instance hosting the SBX system in the private subnet of VPC. Install a HANA database with a version same or higher than the version of the PRD database on this EC2 instance
 - C. Launch the EC2 instance hosting the SBX system in the private subnet of VPC. Install a HANA database of any version on this EC2 instance
 - D. Create a backup of the tenant database of the PRD system and transfer this backup to an S3 bucket that is accessible by the SBX EC2 instance. Restore the backup to the newly created SBX database
 - E. Create a backup of the SYSTEMDB and tenant database of the PRD system and transfer this backup to an S3 bucket that is accessible by the SBX EC2 instance. Restore the backup to the newly created SBX database


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: BD

> SAP workloads always in private subnet, so A discarded. The HANA version of the restore target must be always greater or equal to the backup source one, so B valid and C discarded. And to perform any system copy with HANA you ONLY need the tenant db, so D valid and E discarded.
</details>


## Question 4

A European manufacturing company wants to migrate one of their production SAP HANA databases from on-premise environment to AWS cloud. The company‘s on-premise datacenter is connected via an AWS Direct Connect connection to AWS Cloud. Due to the tight project deadlines, the company‘s SAP solution architect would like to set up the target HANA database in a single EC2 instance in the shortest amount of time possible. Which of the following solutions can meet the requirement? **(Select TWO)**
 - A. Use AWS CloudFormation script to provision the HANA database on the AWS cloud
 - B. Use AWS Quick Start to provision the HANA database on the AWS cloud
 - C. Use SAP Cloud Appliance Library (CAL) to provision the HANA database on AWS cloud
 - D. Use AWS Launch Wizard to provision the HANA database on the AWS cloud
 - E. Use Amazon S3 Transfer Acceleration to provision the HANA database on the AWS cloud


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: AD

> Launch Wizard for SAP software deployment is always the fastest, so D is valid for the initial deployment. But in this list appears the option to use the SAP CAL. SAP CAL launched recently a template of S/4HANA for Production usage only based on Azure https://community.sap.com/topics/cloud-appliance-library/production-ready-systems. So at this moment, we should consider that SAP CAL on AWS can not be used for production at all, then C discarded. By other side, AWS Quick Start is not used anymore for SAP deployments even if it's still valid for other products, then B discarded. Option A could have sense in the case of a great amount of HANA but the requirement is move just one in a very simple configuration, so CloudFormation script does not make sense here. Finally, once the deployment is completed, we need to move the data, and this is the option D regarding S3 Transfer Acceleration. 
</details>


## Question 5

A customer who is running their SAP workloads on-premise wants to deploy the SAP HANA database on the AWS cloud. The customer wants to first try a Proof of Concept (POC) architecture and use HANA Quick Start Reference Deployment in a Single-AZ, single-node deployment scenario. The customer wants to monitor the Quick Start deployment progress. Where can the customer check relevant deployment logs?
 - A. The customer can find the deployment logs in the /root/install/ folder of the SAP HANA instance. The name of the log file is install.log
 - B. The customer can find the deployment logs in the /root/install/ folder of the SAP HANA instance. The name of the log file is deploy.log
 - C. The customer can find the deployment logs in the /root/deployment/ folder of the SAP HANA instance. The name of the log file is install.log
 - D. The customer can find the deployment logs in the /root/deployment/ folder of the SAP HANA instance. The name of the log file is deploy.log


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> This is completely obsolete and this question does not apply https://docs.aws.amazon.com/quickstart/latest/sap-hana/welcome.html. 
</details>


## Question 6

A US-based OTT platform company is running their SAP workloads on-premise. To reduce the overhead administration of infrastructure, the company has decided to move the non-production SAP workloads to AWS. This includes the sandbox, development, and quality environment. The company on-premises is connected to AWS via a site-to-site VPN connection. The company has decided to keep running SAProuter and SAP Solution Manager systems in their on-premise environment. Which of the following statements is true regarding this architecture? **(Select TWO)**
- A. Set up support connectivity for the SAP systems on AWS a change in saprouttab files
- B. Do not set up support connectivity for the SAP systems on AWS a change in saprouttab files
- C. A new connection to SAP Support Backbone is required from the Solution Manager system
- D. A new connection to SAP Support Backbone is not required from the Solution Manager system


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: AD

> saprouttab is necessary to adapt with the new CIDR address space of SAP systems on AWS, while the Backbone connectivity remains unaltered since the saprouter host has been kept in on-premise.
</details>


## Question 7

A US-based banking customer is running their SAP workloads on AWS. They have set up a high availability and disaster recovery solution for their production SAP system in AWS. The highly available systems are running in the us-east-1 region in two availability zones AZ-1 & AZ-2. The disaster recovery systems are placed in the us-west-1 region. The customer is looking for a solution against logical data loss that could happen due to malicious activity or human error. Which of the following solutions is recommended by AWS to meet the customer‘s requirement?
 - A. To protect against logical data loss, it is recommended that regular copies of the data are backed up to an Amazon S3 bucket. This bucket should be replicated to another Amazon S3 bucket owned by a separate AWS account in either us-east-1 or us-west-1 using Same-Region Replication (SRR) or Cross-Region Replication (CRR) respectively
 - B. To protect against logical data loss, it is recommended that regular copies of the data are backed up to an Amazon S3 bucket. This bucket is replicated using Cross-Region replication (CRR) to another Amazon S3 bucket in us-west-1
 - C. To protect against logical data loss, it is recommended that regular copies of the data are backed up to an Amazon S3 bucket. This bucket is replicated using Same-Region replication (SRR) to another Amazon S3 bucket in us-east-1
 - D. To protect against logical data loss, it is recommended that regular copies of the data are backed up to an Amazon S3 bucket. This bucket should have Lifecycle rules enabled so that data can be periodically moved to AWS Glacier


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> Considering the statement of "malicious activity" the only option that guarantees that one single person can not destroy all the information is to have all the relevant backups replicated in different S3 buckets of different accounts and never provide access to both to the same person. Different regions is accessory but justified in this case because is the DR design.
</details>


## Question 8

A US-based Financial company is running their SAP S/4 HANA system in the us-east-1 region on AWS. They are running the SAP system in high availability mode within two different availability zones. They plan to have a multi-region disaster recovery(DR) solution for their S/4 HANA system. The company is also looking for a database native solution for data replication. Which of the following is the most optimal solution for the company‘s DR requirements?
 - A. Set up the disaster recovery system in us-west-1. Use HANA System Replication in an asynchronous (async) mode for data replication
 - B. Set up the disaster recovery system in us-west-1. Use HANA System Replication in synchronous (sync) mode for data replication
 - C. Set up the disaster recovery system in us-west-1. Use S3 Cross Region Replication (CRR) for backup replication across regions
 - D. Set up the disaster recovery system in us-west-1. Use HANA System Replication in synchronous in-memory (syncmem) mode for data replication


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> For DR, always ASYNC, specially if the locations are separated by thousands of kms.
</details>


## Question 9

A company is planning to deploy their SAP BW/4HANA workloads on AWS. They are planning for a scale-out implementation of the HANA database with 4 nodes. The company is also planning to set up a HANA Auto host failover where three nodes will be acting as worker nodes and the fourth node will be a standby node. The company is looking for a low network latency solution that is required for internode communication in a scale-out deployment. Which of the following solutions will meet the company‘s requirements?
 - A. Deploy the HANA nodes in a cluster placement group across multiple availability zones
 - B. Deploy the HANA nodes in a spread placement group across a single availability zone
 - C. Deploy the HANA nodes in a cluster placement group across a single availability zone
 - D. Deploy the HANA nodes in a spread placement group across multiple availability zones


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> A cluster placement is required to guarantee the lowest latency, so B and D discarded and additionally a cluster pg is always in the same AZ, so A discarded. https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html
</details>


## Question 10

A company that is migrating their SAP workloads on AWS is looking for an option that can be used to resolve the IP address and hostname in the VPC. In their on-premise environment, they are using a highly available domain name system (DNS) server. The company is looking for a similar AWS-managed reliable option in the AWS cloud. Which of the following is the most optimal option that can help the customer meet their requirement?
 - A. Use Amazon Route53 as a DNS service. It provides inherent high availability as part of its design
 - B. Set up a DNS server in the EC2 instance. Ensure high availability of this EC2 instance
 - C. Maintain /etc/hosts files in each EC2 instance and ensure high availability for these instances
 - D. Use Amazon CloudFront as a DNS service. It provides inherent high availability as part of its design


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

</details>


## Question 11

A customer is running their SAP workloads on their on-premise environment. The customer wants to connect their on-premise datacenter to the AWS cloud. They are looking for a networking solution that provides encryption during data transfer and are not worried about the cost of setup. Which of the following AWS services meets the customer‘s requirement?
 - A. AWS Site-to-Site VPN
 - B. AWS Direct Connect
 - C. AWS Client VPN
 - D. AWS Customer Gateway

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> If the cost is not an issue A and B are valid options. C can not be used to connect networks, just a user. And D is the artifact to define the on-premise route.
</details>


## Question 12

A Singapore based Financial customer that has been running their SAP workloads on-premise in their datacenter for the last 30 years is considering migrating to AWS cloud. Their SAP team is worried about the security of SAP applications on the AWS cloud. Which of the following is true about the security in the AWS cloud? (Select TWO)
 - A. AWS is responsible for ‘Security of the cloud‘. It involves protecting the infrastructure that runs the services offered in the AWS Cloud
 - B. Customer is responsible for ‘Security in the cloud‘. It involves protecting the infrastructure that runs the services offered in the AWS Cloud
 - C. AWS is responsible for ‘Security of the cloud‘. It involves protecting the data owned by customers along with Identity and access management in the AWS cloud
 - D. Customer is responsible for ‘Security in the cloud‘. It involves protecting the data owned by customers along with Identity and access management in the AWS cloud

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: AD

> Shared Responsibility Model: AWS controls the infra, you control the data and config of AWS artifacts.
</details>


## Question 13

A company is running its SAP S/4 HANA production system on the AWS cloud. Both the SAP database, ABAP SAP Central Services (ASCS), and Primary Application Server (PAS) EC2 instances are in the same private subnet. After an OS hardening activity on a weekend, when the SAP engineers try to start the SAP application they get the error message – ‘Database is not available via R3trans – Database must be started first ‘ When they log in to the database EC2 instance they notice that the database is already running. Considering that the HANA database instance number is 00, What should the SAP engineers do to troubleshoot this issue ?
 - A. Restart the database and the database EC2 instance again. Try starting the SAP application once the database restart has finished
 - B. Ensure that the security group of the database EC2 instances allows communication from the application server. Check if the port range 30015 - 39915 is allowed from the private IP address of the application server
 - C. Ensure that the security group of the database EC2 instances allows communication from the application server. Check if the port range 3600 - 3699 is allowed from the private IP address of the application server
 - D. Ensure that the Network Access Control lists (NACLs) of the private subnet allow communication from the application server



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> Must be B because it was after an OS hardening activity and the symptom is that the DB is running but SAP is not reaching it. So HANA ports 30015-39915 involved and never the 3600-3699 that corresponds to message server.
</details>


## Question 14

A US-based retail company is running its SAP workloads on AWS. They are using multiple VPCs that are communicating with each other using the VPC peering method. After a recent merger and acquisition, the company expects its accounts and VPCs to grow as more SAP systems will be on-boarded on the AWS cloud. The company is looking for an AWS-managed solution that works on a hub and spoke model to ensure communication between all the VPCs across the company‘s accounts. Which of the following solutions can help meet the company‘s requirements?
 - A. Use an AWS Virtual Private Gateway to connect the company‘s VPCs. The Virtual Private Gateway can be shared through AWS Resource Access Manager (RAM) across the company‘s AWS accounts
 - B. Use an AWS Transit Gateway to connect the company‘s VPCs. The Transit Gateway can be shared through AWS Resource Access Manager (RAM) across the company‘s AWS accounts
 - C. Use an AWS Virtual Private Gateway to connect the company‘s VPCs. The Virtual Private Gateway can be shared through AWS Control Tower across the company‘s AWS accounts
 - D. Use an AWS Transit Gateway to connect the company‘s VPCs. The Transit Gateway can be shared through AWS Control Tower across the company‘s AWS accounts



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> Transit Gateway is the solution to interconnect multiple VPCs. RAM is used to share the access with other accounts. https://docs.aws.amazon.com/vpc/latest/tgw/transit-gateway-share.html
</details>


## Question 15

An EMEA region customer is planning to run their SAP workloads on AWS. The customer‘s SAProuter is currently running on-premise in their network‘s demilitarized Zone(DMZ). They are looking for a similar solution to set up SAProuter in the AWS cloud. Which of the following combinations of steps can help meet the customer‘s requirement? **(Select TWO)**
 - A. Launch the instance that the SAProuter software will be installed on into a public subnet of the VPC and assign it an Elastic IP address
 - B. Launch the instance that the SAProuter software will be installed on into a private subnet of the VPC and assign it an Elastic IP address
 - C. Create and configure a security group for the SAProuter instance, which allows the inbound and outbound access from SAP provide IP address along with TCP port 3299
 - D. Create and configure a security group for the SAProuter instance, which allows the inbound and outbound access from SAP provide IP address along with TCP port 3600
 - E. Create and configure a security group for the SAProuter instance, which allows inbound and outbound access from the internet along with TCP port 3600



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: AC

> The equivalent to a DMZ is a public subnet and the Elastic IP is a public IP. A security group is an artifact at EC2 instance level to allow or deny inbound/outbound connections and the typical usage is to allow the SAP Support public SAProuter IP to reach the SAProuter port 3299.
</details>


## Question 16

A company is running a 15 TB production HANA database on AWS. The company has requirements to perform daily complete backups. They have decided to use AWS Backint for the HANA backups. They will be storing the backups in S3. During the first run of the backup, the backup fails with error code 403 – Access denied. What could be the cause of this error?
 - A. S3 Transfer Acceleration is not enabled in the bucket where backups are stored
 - B. The IAM role on the HANA DB EC2 instance doesn‘t have sufficient permission
 - C. S3 Versioning needs to be enabled to ensure the consistency of backups
 - D. Public access needs to be provided to the S3 bucket where backups are stored



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> It's obviously a permissions error and the IAM role is necessary to perform the initial setup HANA Backint.
</details>


## Question 17

A Germany based automobile company is running a 20 TB size SAP S/4 HANA 2020 system on AWS. They have installed an SAP router along with a NAT gateway on the public subnet of VPC. They have also performed the connectivity to the SAP support backbone. Now the SAP team wants to create an OSS incident for few of the issues related to performance. What are the prerequisites recommended before opening an OSS message with SAP? **(Select Three)**
 - A. Ensure that connections are open to the S/4 HANA system from the SAP support portal
 - B. Ensure that AWS Data Provider is installed
 - C. Ensure that a support user in the secure area of the SAP support portal is maintained
 - D. Ensure that SAP Enhanced monitoring is deployed
 - E. Ensure that CloudWatch Detailed monitoring is turned on
 - F. Ensure that a support user is created in the SAP system in SU01



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: BDE

> As per https://me.sap.com/notes/1656250 just AWS Data Provider agent configured, Enhanced monitoring and CloudWatch Detailed monitoring enabled. The rest are also strongly recommended to open a case if you want SAP Support engineer connects to your system to reproduce the issue, but not mandatory for opening the case at all.
</details>


## Question 18

A company has recently set up a new SAP S/4 HANA 2021 environment on AWS in the us-east-1 region. After go-live, the SAP Basis administrator finds out that the performance data in transaction ST06N is missing. What should an SAP Basis administrator do to resolve this issue?
 - A. ST06N is not supported for SAP systems on AWS. Write a script that collects the performance data and monitors it daily
 - B. Install the AWS Data Provider for SAP on the SAP instance
 - C. Install the Amazon CloudWatch agent on the SAP instance
 - D. Create an SAP-OSS message and AWS support ticket



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> Does not exist any CloudWatch agent, it's a known issue and this is the reason why AWS Data Provider for SAP must be configured (on every SAP instance).
</details>


## Question 19

A US-based customer is planning to deploy 10 TB of SAP HANA database with high availability option in AWS cloud. The primary and secondary SAP HANA databases are running in separate private subnets in different Availability Zones within an AWS Region. The VPC CIDR range of this setup is 10.0.0.0/16. The customer is using SUSE Linux Enterprise High Availability Extension as the clustering solution. The Overlay IP assigned for the SAP HANA database cluster is 192.168.0.54. Which of the following solutions can the customer use for routing the Overlay IP address? **(Select TWO)**
 - A. The customer can use an AWS Transit Gateway that serves as a central hub to facilitate network connection to the Overlay IP address
 - B. The customer can use an AWS Virtual Private Gateway that serves as a central hub to facilitate network connection to the Overlay IP address
 - C. The customer can use an AWS Network Load Balancer that enables network access to the Overlay IP address
 - D. The customer can use an AWS Application Load Balancer that enables network access to the Overlay IP address
 - D. The customer can use the clustering capabilities of SUSE Linux Enterprise High Availability Extension to facilitate network connection to the Overlay IP address



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: AC

> See https://docs.aws.amazon.com/sap/latest/sap-hana/sap-oip-overlay-ip-routing-using-aws-transit-gateway.html and https://docs.aws.amazon.com/sap/latest/sap-hana/sap-oip-overlay-ip-routing-with-network-load-balancer.html
</details>


## Question 20

A SAP Solution architect in a Pharma company is designing a high availability solution for their SAP S/4 HANA production system on AWS cloud. They are planning to use a clustering solution for automatic switchover and failover scenarios. This highly available system will be deployed in two different Availability Zones in different subnets in a single AWS Region. Which of the following services of SAP S/4 HANA systems are considered Single Points of Failure (SPOFs) where the architect needs to configure high availability?
 - A. The Application Servers and database are considered Single Points of Failures (SPOFs) in standard SAP architecture where high availability is required
 - B. The ABAP SAP Central Service (ASCS) and database are considered Single Points of Failures (SPOFs) in standard SAP architecture where high availability is required
 - C. The ABAP SAP Central Service (ASCS) and Application Servers are considered Single Points of Failures (SPOFs) in standard SAP architecture where high availability is required
 - D. The database only is considered a Single Point of Failure (SPOF) in standard SAP architecture where high availability is required



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B
</details>


## Question 21

A European OTT platform company is planning to deploy 24TB of SAP HANA database as a highly available system on AWS cloud. The primary and secondary SAP HANA databases are running in separate private subnets in different Availability Zones within an AWS Region. The company is looking for a database native solution for high availability. Which of the following options will provide the lowest possible recovery time objective (RTO)?
 - A. Use SAP HANA system replication in synchronous mode with the preload option for data replication between primary and secondary. Use a smaller EC2 instance for the secondary database than the primary
 - B. Use SAP HANA system replication in a synchronous mode without the preload option for data replication between primary and secondary. Use a smaller EC2 instance for the secondary database than the primary
 - C. Use SAP HANA system replication in synchronous mode with the preload option for data replication between primary and secondary. Use the same sized EC2 instance for the secondary database as the primary
 - D. Use SAP HANA system replication in a synchronous mode without the preload option for data replication between primary and secondary. Use a same-sized EC2 instance for the secondary database as primary

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> Since cost-effective is not required, C is the option with lowest RTO.
</details>


## Question 22

A Singapore – based public sector company has deployed their SAP workloads on AWS in ap-southeast-1 region, which is the only available AWS region in the country. As per the company‘s policy, the data must reside within the country. They are looking for a solution that will ensure High Availability(HA) and Disaster Recovery (DR). Which of the following options meets the company‘s requirements?
 - A. Set up High Availability for SAP workloads in AZ-1 & AZ-2 of the ap-southeast-1 region. Set up DR for SAP workloads in AZ1 of the ap-south-1 region
 - B. Set up High Availability for SAP workloads in AZ-1 & AZ-2 of the ap-southeast-1 region. Set up DR for SAP workloads in AZ-3 of the ap-southeast-1 region
 - C. Set up High Availability for SAP workloads in AZ-1 of the ap-southeast-1 region. Set up DR for SAP workloads in AZ-2 of the ap-southeast-1 region
 - D. Set up High Availability for SAP workloads in AZ-1 & AZ-2 of the ap-southeast-1 region. Set up DR for SAP workloads in AZ-1 & AZ-2 of the ap-south-1 region

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> ap-south-1 does not exist.
</details>


## Question 23

A customer is running their SAP workloads on AWS. Their SAP landscape includes SAP S/4 HANA, SAP Adobe Document Services (ADS), and SAP Solution Manager system. The ADS and SAP solution manager are running on the Oracle database. They are looking for a solution that can fulfill their disaster recovery (DR) needs without the administrative overhead of using multiple solutions for data replication. Which of the following solutions meets the customer‘s requirements?
 - A. Use CloudEndure disaster recovery for data replication
 - B. Use HANA System Replication (HSR) for data replication
 - C. Use Oracle DataGuard for data replication
 - D. Use AWS DataSync for data replication

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A*
 
* CloudEndure DR are not supported anymore since 1st Dec 2023 except China. Use Elastic DR instead: https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/use-cloudendure-for-disaster-recovery-of-an-on-premises-database.html

> Option A because they do not want multiple solutions, so CloudEndure DR should be the valid. By other hand, CloudEndure (now Elastic DR) can be used for database DR while DataSync is intended for files. See https://aws.amazon.com/disaster-recovery/when-to-choose-aws-drs/?cloud-endure-blogs.sort-by=item.additionalFields.createdDate&cloud-endure-blogs.sort-order=desc
</details>


## Question 24

A customer is running their SAP workloads on-premise. The landscape consists of multiple SAP systems running on SAP Adaptive Server Enterprise (ASE) database on Linux operating systems. The customer is looking for a method to directly backup the database on the AWS cloud in an S3 bucket using the NFS protocol. Which of the following is a valid solution that meets the customer‘s requirement?
 - A. Create an Amazon S3 File Gateway using AWS Storage Gateway. Create an NFS file share and connect it to Amazon S3. Create a mount point on a database host and mount the NFS file share
 - B. Create an Amazon S3 Volume Gateway using AWS Storage Gateway. Create an NFS file share and connect it to Amazon S3. Create a mount point on a database host and mount the NFS file share
 - C. Create an Amazon S3 Tape Gateway using AWS Storage Gateway. Create an NFS file share and connect it to Amazon S3. Create a mount point on a database host and mount the NFS file share
 - D. Create an Amazon Transit Gateway. Create an NFS file share and connect it to Amazon S3. Create a mount point on a database host and mount the NFS file share


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> Storage Gateway is the S3 in the edge. Tape for tape, volume for iSCSI volumes, and file for NFS. So, B and C discarded, A valid. About D could be valid for one small backup but not for all backups of all SAP systems due to it would collapse the connection to AWS. See https://docs.aws.amazon.com/en_en/filegateway/latest/files3/what-is-file-s3.html and https://docs.aws.amazon.com/storagegateway/.
</details>


## Question 25

A US-based Pharma company is planning to deploy the SAP HANA database on the AWS cloud. The database size is around 10 TB. They will be deploying the database in a private subnet of a VPC. They are looking for an operating system to host the HANA database, which provides inherent high availability capabilities. Which of the following operating systems, available in AWS Marketplace meets the company‘s requirements?
 - A. SUSE Linux Enterprise Server (SLES) 15.1 for SAP
 - B. SUSE Linux Enterprise Server (SLES) 15.1
 - C. Red Hat Enterprise Linux (RHEL) 8.1
 - D. Microsoft Windows Server 2016

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> Currently both (SLES for SAP and RHEL **for SAP** / Red Hat Enterprise Linux **for SAP Solutions**) are certified for HANA HA on AWS. See https://docs.aws.amazon.com/sap/latest/sap-hana/sap-hana-on-aws-automated-deployment-of-sap-hana-on-aws-with-high-availability.html and https://me.sap.com/notes/2765525.
</details>


## Question 26

A customer is planning for a greenfield implementation of the SAP S/4 HANA system on the AWS cloud. They have performed the sizing of the HANA database using the SAP Quick Sizer report and have the required value for SAPS (SAP Application Performance Standard). The next step is to select an EC2 instance for the HANA database. Which of the following sources can the customer refer to choose an appropriate EC2 instance for the HANA database on the AWS cloud? **(select TWO)**
 - A. The customer can refer to the SAP Community Network (SCN) blog for selecting the EC2 instance
 - B. The customer can refer to the AWS blog for selecting the EC2 instance
 - C. The customer can refer to the ‘SAP Certified and Supported SAP HANA Hardware Directory‘ page for selecting the EC2 instance
 - D. The customer can refer to ‘SAP Note 1656099 - SAP Applications on AWS: Supported DB/OS and Amazon EC2 products‘ for selecting the EC2 instance
 - E. The customer can refer to the SAP Product Availability Matrix (PAM) for selecting the EC2 instance


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: CD

    > SCN neither AWS blog are trustable sources compared with PAM, OSS or the SAP Certified HANA page. But PAM does not contain this information but only software release info.
</details>


## Question 27

A customer is deploying SAP S/4 HANA landscape on AWS Cloud. The landscape consists of development (DEV), quality (QAS) and production (PRD) systems. The SAP applications are running on the Windows Server 2016 operating system. The DEV and QAS systems are located in a single AWS Account and the PRD system is in a different AWS Account. The customer is looking for a storage solution for the \usr\sap\trans directory which is scalable and highly available. Which of the following AWS storage services meet the customer requirement?
 - A. Amazon Elastic File System (Amazon EFS)
 - B. Amazon Elastic Block Store (Amazon EBS)
 - C. Amazon S3
 - D. Amazon FSx

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

    > Windows keyword => FSx
</details>


## Question 28

A US-based financial company is planning to deploy its SAP S/4 HANA workloads on the AWS cloud. The HANA database will be launched in an EC2 instance with SUSE Linux as an operating system. For /hana/data and /hana/log directory they will be using EBS volumes. The company‘s SAP solution architect wants to understand the encryption for EBS volumes. Which of the following statements are TRUE for encrypted EBS volume in the AWS cloud? **(Select THREE)**
 - A. Data at rest inside the volume is encrypted
 - B. All data moving between the volume and S3 storage is encrypted
 - C. All data moving between the volume and the instance is encrypted
 - D. All snapshots created from the encrypted volume are encrypted
 - E. All data moving between the volume and EFS storage is encrypted

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: ACD

    > Obviously data inside the volume is encrypted, also data in transit with instance where the volume is attached and all its snapshots. See https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html
</details>


## Question 29

A European automobile company has deployed their 5 TB of production HANA database on a single u-6tb1.metal server. On the upcoming Sunday, they plan to perform patching of their HANA database. The SAP Basis team has approval for the downtime of 6 hrs. The SAP Basis team is looking for a disk-based backup solution so that in case there are issues with patching, they can restore the database quickly. Which of the following storage solutions can help the Basis team meet their requirements with minimum cost?
 - A. Elastic Block Store (EBS) General Purpose SSD (gp2)
 - B. AWS Simple storage service (S3)
 - C. Elastic File System (EFS)
 - D. Elastic Block Store (EBS) Throughput Optimized HDD (st1)

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

    > S3 is the cheapest but can not be used for a "disk-based backup". EFS could be used for this but it's not the best option to "restore the database quickly". EBS General Purpose is the most expensive while EBS Throughput is cheap and ideal for backup/restore.
</details>


## Question 30

A global retail company is looking to migrate their SAP S/4 HANA landscape to AWS. The landscape includes Sandbox (SBX), Development (DEV), Quality Assurance (QAS) and Production (PRD) systems. The SBX, DEV and QAS systems need to be available for 8 hrs per day, only on weekdays. The PRD system is expected to run 24*7. It is also expected that the size of the PRD system may increase after 8 months of usage as the company‘s business grows. Which of the following would be the most cost-efficient purchase option for the EC2 instances running the SAP systems?
 - A. Use On-demand billing for SBX, DEV, QAS systems and dedicated hosts for the PRD system.
 - B. Use On-demand billing for SBX, DEV, QAS and Standard Reserved Instance for the PRD system.
 - C. Use On-demand billing for SBX, DEV, QAS and Convertible Reserved Instance for the PRD system.
 - D. Use On-demand billing for SBX, DEV, QAS and Compute Savings Plans for the PRD system.
 - E. Use Spot instances for SBX, DEV, QAS and Standard Reserved Instance for the PRD system.



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

    > Standard Reserve can not be scaled up 8-months after. Convertible is the most cost-efficient.
</details>


## Question 31

You are an SAP architect with a US-based Pharma company that is running their SAP workloads on AWS in the us-east-1 (N. Virginia) region. The company is planning to set up a disaster recovery (DR) solution in the us-west-2 (Oregon) region. The company‘s management has agreed that they can tolerate the RPO and RTO in hours but are looking for a low operational cost DR solution. Which of the following Disaster Recovery architecture do you propose for minimum operational cost?
 - A. Set up a Passive DR by backing up the data to S3. Use S3 cross-region replication (CRR) to replicate the backups to the us-west-2 (Oregon) region. Create and replicate the AMIs of application servers and databases to the us-west-2 (Oregon) region. Build the DR environment using AMIs and backups in case of a switchover.
 - B. Set up a Passive DR by backing up the data to S3. Use S3 cross-region replication (CRR) to replicate the backups to the us-west-2 (Oregon) region. Create and replicate the AMIs of application servers and databases to the us-west-2 (Oregon) region. Build the SAP systems on DR using AMIs and backups. Switchover to the DR region in case of a disaster.
 - C. Set up a Pilot light DR by ensuring that all the systems running on us-east-1 (N. Virginia) are also built in the us-west-2 (Oregon) region. Shut down the application servers and keep the database in standby mode in the DR region. Replicate the data using a native database high availability/ disaster recovery solution. Start the database and application servers in case of a switchover.
 - D. Set up a Pilot light DR by ensuring that all the systems running on us-east-1 (N. Virginia) are also built in the us-west-2 (Oregon) region. Ensure that the application servers and database are running in the DR region. Replicate the data using a native database high availability/ disaster recovery solution. Switchover to the DR region in case of a disaster.



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 32

A company is running their SAP S/4 HANA landscape on AWS. The company is building its disaster recovery (DR) solution in another region and is looking for a way to replicate the saptrans and sapglobal files to the DR region. Currently, these files are hosted on the Amazon Elastic File System(EFS) on the primary side. Which of the following Amazon services can help companies meet this requirement? (**Select TWO**)
 - A. AWS Backup
 - B. AWS Backint Agent
 - C. AWS DataSync
 - D. AWS Cross Region Replication
 - E. AWS Elastic File System (EFS) snapshots.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: AC

> Since the company is lookiing for **replicate** the file systems based on EFS, the options are DataSync and Backup according to https://docs.aws.amazon.com/sap/latest/general/arch-guide-architecture-guidelines-and-decisions.html: *AWS DataSync supports Amazon EFS to Amazon EFS transfer between Regions and different AWS Accounts, allowing the replication of key SAP file based data across Regions. AWS Backup can also be used to replicate backups of Amazon EFS file systems across Regions.*. Option B is directly discarded since the Backint Agent is only for SAP HANA Backup on AWS. Option D is discarded since the volume is an EFS, not an S3. Option E could also be an option for a DR but it's not prescribed for this scenario.
</details>


## Question 33

A customer is planning to migrate their 10 TB of production HANA enterprise edition database from on-premise to AWS cloud. They are looking for an option to license the HANA database on AWS. Which of the following statements is TRUE?
 - A. The customer can use an existing license by using AWS ‘Bring your own license (BYOL)‘ model.
 - B. The customer can purchase the license for the HANA database from AWS Marketplace.
 - C. The customer does not need a license for the HANA database since it is included in the on-demand EC2 instances pricing for SAP.
 - D. The customer can use the Trial and developer license from CAL (Cloud Appliance Library).

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> Option A is TRUE because the customer has its own HANA license on-premise and the most cost-effective is move that license to the new host in AWS. This model is BYOL. Option B is FALSE because the HANA database can not be purchased in AWS Marketplace, only the OS (SLES|RHEL[4SAP]). Option C is FALSE because the HANA license is not included at all with any on-demand neither reserved neither any payment model of EC2 (only the OS license is always included for on-demmand EC-2). Finally option D is FALSE because its DB size is 10TB which is greater than the 32 GB limit of HANA express (developer) edition and customer wants it for production while CAL is not for PROD and the Trial license is just for a short period (30-days usually). See https://aws.amazon.com/sap/solutions/saphana/.

</details>


## Question 34

A company wants to migrate an on-premises SAP BusinessObjects Business Intelligence Platform workload to AWS. The company needs to use the most cost-effective database solution that will support the workload on AWS. Which database solution will meet these requirements?
 - A. SAP HANA
 - B. Amazon RDS for MySQL
 - C. Amazon Redshift
 - D. IBM Db2

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> According to PAM and OSS 1656099, SAP BusinessObjects Business Intelligence, versions 4.2 or higher, 4.3 or higher are supported on Amazon Relational Database Service (RDS) for MySQL and for SQL Server. By other hand, Data Services is only supported in RDS for MSSQL. See SAP note https://me.sap.com/notes/1656099. See deployment guide https://docs.aws.amazon.com/sap/latest/sap-businessobjects/bobi-windows-deployment.html. MySQL is opensource, then the most cost-effective option is B. Options A and D requires license from SAP and IBM respectively and option C does not apply because Redshift is for OLAP while the underlying DB for BO is always OLTP even the usage is to process/present data from OLTP/OLAP sources.
</details>


## Question 35

A company is planning to migrate its existing SAP workloads to AWS. An SAP solutions architect needs to design a highly available solution for SAP ERP Central Component (SAP ECC) on an SAP HANA production system on AWS. The company already has existing non-SAP workloads that run on AWS with AWS Organizations. The company uses AWS Resource Access Manager (AWS RAM) to share VPCs across multiple existing accounts. The company has decided to use SUSE Linux Enterprise Server to host the SAP workloads. How should the SAP solutions architect deploy the SAP workloads to meet these requirements?
- A. Create separate production and non-production AWS accounts for SAP workloads. Use AWS RAM to share VPCs and subnets with the newly created accounts.
- B. Create separate production and non-production AWS accounts for SAP workloads. Set up dedicated VPCs and subnets for the newly created accounts.
- C. Deploy SAP solutions with SUSE Linux Enterprise High Availability Extension configured in a single existing AWS account for production and non-production workloads.
- D. Create a single separate AWS account for SAP workloads. Use AWS RAM to share VPCs and subnets with the newly created account.


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> Option D can be discarded because the HA is only required for PROD. Option D can be discarded because use separate accounts for prod and non-prod is a best practice.

> *Using multiple AWS accounts to help isolate and manage your business applications and data can help you optimize across most of the AWS Well-Architected Framework pillars, including operational excellence, security, reliability, and cost optimization.* https://docs.aws.amazon.com/whitepapers/latest/organizing-your-aws-environment/organizing-your-aws-environment.html

> AWS RAM usage is not part of the best practice because it breaks the security isolation between the VPCs, so option A can be discarded.

> Finally, option B is most consistent from a security point of view and Well-Architected, but it's true that the transport directory will have to be replicated/interconnected in some way but in an scenario like this two options:

> - Replication: Have one for non-prod and one for prod and transfer the TRs via RFC from STMS via VPC peering or with Transit Gateway.

> - Shared FS: Use an EFS for /usr/sap/trans and mount it from the other VPC. See https://docs.aws.amazon.com/en_en/efs/latest/ug/efs-different-vpc.html.
</details>


## Question 36

A company runs an SAP S/4HANA system that includes critical business processes. An SAP solutions architect must design a highly available SAP application. The SAP application must have availability of 99.9% or more. The SAP database also must have availability of 99.9% or more. Which solution will meet these requirements?

- A. Install SAP ASCS instances and ERS instances on separate Amazon EC2 instances with an SAP certified cluster monitoring solution in different Availability Zones within an AWS Region. Configure an active-standby database setup with cluster monitoring. Deploy at least two SAP application servers that extend across multiple Availability Zones within the Region.
- B. Install SAP ASCS instances and ERS instances on one Amazon EC2 instance. Create Amazon Elastic Block Store (Amazon EBS) snapshots each hour. Configure an active-standby database setup. Deploy at least two SAP application servers in one Availability Zone.
- C. Install SAP ASCS instances, primary application server (PAS) instances, and a database instance on separate Amazon EC2 instances. Schedule Amazon Elastic Block Store (Amazon EBS) snapshots for every 10 minutes. Schedule database log backups for every 10 minutes.
- D. Install SAP ASCS instances, ERS instances, and a database instance on one Amazon EC2 instance. Install SAP application servers in the same subnet as the database instance. Use AWS Elastic Disaster Recovery (CloudEndure Disaster Recovery) to continuously replicate the SAP S/4HANA system to the standby AWS Region.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> 99.9% can only be reached with HA in different AZ but always in same Region. Option B, C and D are discarded since these options are not HA but based on one single EC2 instance. So, option A is the only that accomplishes or at least approach the 99.9% requirement.
</details>


## Question 37

A company is running a 5 TB SAP Business Warehouse (SAP BW) 7.5 system on SAP HANA 2.0 SPS 04. The SAP BW system and the SAP HANA database are hosted in an on-premises data center in a SUSE Linux Enterprise Server environment. The company wants to migrate the system to AWS without changing the type of the underlying operating system. The company has established a 1 Gbps IPsec VPN tunnel for networking between the AWS Cloud and the data center. The company needs a migration solution that minimizes downtime and cost. Which solution will meet these requirements?

 - A. Use the SAP HANA native backup and restore. Transfer the backup files to AWS by using an AWS Snowball Edge Storage Optimized device. Restore the files from the destination Amazon S3 bucket.
 - B. Use the SAP HANA classical migration method by using SAP Software Provisioning Manager (R3load based) with parallel export/import. Use the IPsec VPN tunnel for the network connectivity.
 - C. Use a third-party migration tool that is licensed and certified for SAP migration. Use the IPsec VPN tunnel for the network connectivity.
 - D. Use SAP HANA system replication. Use the IPsec VPN tunnel for the network connectivity.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

> HANA replication is the option with less downtime. Does not matter if DB is 5TBs, 50TBs or 5GB

</details>


## Question 38

A company uses AWS Backint Agent for SAP HANA (AWS Backint agent) to store SAP HANA backups. The backups are stored in an Amazon S3 Standard bucket that is replicated to a secondary AWS Region. An SAP engineer must reduce the cost of the backups without degrading the current RPO and RTO during recovery in the secondary Region. Currently, database backups are scheduled to run every 12 hours. What should the SAP engineer do to meet these requirements?

 - A. Configure a retention policy in SAP HANA Cockpit.
 - B. Configure AWS Backint agent to save backups in S3 Glacier Deep Archive instead of in S3 Standard.
 - C. Remove S3 Cross-Region Replication (CRR).
 - D. Reduce the frequency of SAP HANA backups.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> Reducing the retention policy from SAP HANA Cockpit reduces the total size used of CRR S3 bucket used by Backint. Option B is discarded due to S3 Glacier Deep Archive has a 12-h of access time and it would affect the current RTO. Option C is cheaper but it clearly would degrade the current resilience impacting on RPO. Option D would be cheaper in terms of cross-region data transfer but it degrades clearly the current RPO since the backup frequency is reduced.
</details>


## Question 39

A company wants to deploy SAP S/4HANA 2020 in a new environment. The company wants a high availability setup for production. The company wants a single-system deployment for its development system and its quality system. An SAP solutions architect must design a solution on AWS to accelerate the deployment. Which solution will require the LEAST amount of time to complete the deployment?

 - A. Create Amazon EC2 launch templates. Launch EC2 instances by using the templates. Use SAP Software Provisioning Manager to install SAP S/4HANA 2020 for the development system and the quality system. Manually deploy a high availability cluster for the production SAP S/4HANA 2020 instance.
 - B. Create Amazon EC2 launch templates. Launch EC2 instances by using the templates. Use SAP Software Provisioning Manager to install SAP S/4HANA 2020 for the development system and the quality system. Use AWS Launch Wizard for SAP to deploy a high availability cluster for the production SAP S/4HANA 2020 instance.
 - C. Use AWS Launch Wizard for SAP to deploy SAP S/4HANA 2020 on listed Amazon EC2 instance types in single-instance deployment mode for the development system and the quality system. For production, use Launch Wizard for SAP to deploy SAP S/4HANA 2020 on listed EC2 instance types in high availability deployment mode.
 - D. Create an AWS CloudFormation template to automate the deployment of SAP S/4HANA 2020 and related compute and storage resources for all environments.


<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> Keywords "LEAST amount of time", "Launch Wizard".
</details>


## Question 40

A company in the United States is planning to deploy a new SAP HANA instance on AWS. The company needs a highly available solution for the SAP HANA instance with an RPO of zero. An SAP solutions architect is using SAP HANA system replication between a primary node and a secondary node for this setup. How should the SAP solutions architect place the nodes to meet these requirements?

 - A. Place the primary node in one AWS Region. Place the secondary node in a different Region. Set up SAP HANA system replication between the primary node and the secondary node in SYNC mode.
 - B. Place the primary node in one AWS Region. Place the secondary node in a different Availability Zone within the same Region. Set up SAP HANA system replication between the primary node and the secondary node in SYNC mode.
 - C. Place the primary node and the secondary node in the same Availability Zone. Create and use a spread placement group. Set up SAP HANA system replication between the primary node and the secondary node in ASYNC mode.
 - D. Place the primary node and the secondary node in the same Availability Zone. Create and use a cluster placement group. Set up SAP HANA system replication between the primary node and the secondary node in SYNC mode.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> RPO zero on SAP HANA can only be reached by SYNC mode of SAP HANA system replication, so option C discarded. SYNC mode can only run between EC2 instances on same region, so option A discarded. RPO zero can only be reached using EC2 instances of different AZs, so now option D discarded. So, it's B.
</details>


## Question 41

A company‘s SAP solutions architect needs to implement a disaster recovery (DR) plan for a production SAP S/4HANA solution. The solution includes a single 512 GB database instance, one primary application server (PAS) instance, and two additional application server (AAS) instances. The company runs its production systems in one Availability Zone in the us-east-2 Region. The company runs its non-production systems in a separate Availability Zone in us-east-2. The production instances are the same size as the non-production instances. In a disaster scenario, the company must meet an RPO of 15 minutes and must meet an RTO of 2 hours. The DR target site must be in a separate AWS Region. Which solution will meet these requirements at the LOWEST cost?

 - A. In a separate Region, create a full-size copy of the production SAP S/4HANA environment, including the PAS and AAS instances. Set up asynchronous SAP HANA system replication with data preload to the standby SAP HANA database in the separate Region. In the event of a production failure, point the end users to the SAP S/4HANA system in the separate Region.
 - B. In a separate Region, create a standby database instance that uses a smaller instance type than the current SAP HANA DB uses. Set up asynchronous SAP HANA system replication without data preload to the standby SAP HANA DB in the separate Region. Back up the most recent AMI and Amazon EBS snapshots of all instances to the separate Region. In the event of a production failure, resize the SAP HANA database instance so that it is the same size as the source database instance, restore the PAS and AAS instances from snapshots, and point the end users to the SAP S/4HANA system in the separate Region.
 - C. In us-east-2, set up synchronous SAP HANA system replication without data preload from the existing production SAP HANA database in one Availability Zone to the existing non-production SAP HANA database in a separate Availability Zone. Back up the most recent AMI and Amazon Elastic Block Store (Amazon EBS) snapshots of all instances to us-east-2. In the event of a production failure, stop the non-production system, reload from the production storage, restore the PAS and AAS instances from snapshots, and point the end users to the SAP S/4HANA system in the new Availability Zone.
 - D. Copy all SAP HANA backup files, all SAP HANA database logs, and all instance AMIs and Amazon Elastic Block Store (Amazon EBS) snapshots to Amazon S3 as they are created. Set up S3 Cross-Region Replication to an S3 bucket in a separate Region. In the event of a production failure, copy the replicated files to EBS volumes, restore the SAP HANA database, restore the PAS and AAS instances from snapshots, and point the end users to the SAP S/4HANA system in the separate Region.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> Option A discarded since "data preload" is exactly the worst in terms of cost. Option D is discarded since this does not accomplishes the RTO of 15 minutes. Option C is cheaper than B and in certain mode accomplishes the requirements even the "synchronous" replication mode since it is without data preload.
</details>


## Question 42

A company is onboarding 10 new users in its Singapore office for its SAP S/4HANA 2020 system with the SAP Fiori front-end server (FES) embedded. The users in Singapore are experiencing poor performance across all functionality. The performance for United States-based users is as expected. The SAP S/4HANA system is deployed in the us-east-1 Region. An SAP basis administrator discovers that network latency seems to be the primary issue. The users are connecting through the internet. How should the SAP basis administrator improve the Singapore users‘ front-end experience for all SAP S/4HANA functionality?

 - A. Set up a separate SAP Fiori FES in the ap-southeast-1 (Singapore) Region. Configure the Singapore users‘ browsers to connect to this instance. Use AWS Transit Gateway to direct traffic to the SAP S/4HANA solution in us-east-1.
 - B. Establish an AWS Site-to-Site VPN connection from the Singapore office to us-east-1. Route the Singapore users‘ connections over the VPN.
 - C. Instruct the Singapore users to adopt SAP GUI for Windows instead of SAP Fiori. Deploy SAP GUI in an Amazon AppStream 2.0 image in a VPC in the ap-southeast-1 (Singapore) Region. Set up an inter-Region VPC peering connection to us-east-1. Instruct the Singapore users to access SAP GUI in AppStream 2.0 from their browsers.
 - D. Create an internet-facing Application Load Balancer (ALB) in us-east-1. Connect the ALB to the SAP S/4HANA system. Create an Amazon CloudFront distribution, and point the origin domain name to the ALB. Create an AWS Global Accelerator accelerator that has an endpoint that points to the ALB. Use Amazon Route 53 to set up the appropriate alias. Instruct the Singapore users to use this alias for connectivity through their browsers.



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

> First of all we have to consider that between Singapore and US East there are thousands of kms. Even if the connection is over internet of over VPN the latencies will not differ. A Direct Connect is not listed, so option B is clearly discarded. Fiori applications perform lot of roundtrips to OData layer of NW Gateway in comparison with typical SAPGUI but Option C is discarded since recommend get back to the SAP GUI is not the appropiate. Option A will not improve the experience so much since even the roundtrips between Fiori and GW via HTTPS are usually more than between GW and Backend via RFC it will not offer such performance like implement any kind of netwoek accelerator solution. Finally option D speaks about Global Accelerator and CloudFront and these are the keys to improve the latency between separated locations over internet.
</details>


## Question 43

A company migrated its SAP S/4HANA workload to run on memory optimized Amazon EC2 instances with SUSE Linux Enterprise Server as the operating system. The company wants to modify the architecture to ensure that the SAP S/4HANA deployment is highly available. The company also wants to support the lowest possible RPO and RTO. Which solution will meet these requirements?

 - A. Create an Auto Scaling group that has a minimum capacity of one instance and a maximum capacity of one instance. Use Amazon Data Lifecycle Manager (Amazon DLM) to automate Amazon Elastic Block Store (Amazon EBS) volume snapshots.
 - B. Set up an Amazon CloudWatch alarm to recover the EC2 instances automatically. In case of failure, use Amazon Elastic Block Store (Amazon EBS) volume snapshots to recover the SAP S/4HANA system to the most recent state.
 - C. Implement a Cross-AZ SAP S/4HANA high availability system by using AWS Launch Wizard for SAP. Deploy EC2 instances for ASCS, ERS, and SAP HANA databases across two Availability Zones. Spread the deployment of application servers across the EC2 instances.
 - D. Perform a daily backup of the SAP S/4HANA system with automatic log backup to an Amazon S3 bucket. In case of failure, perform a point-in-time recovery of the system from the backup that is stored in the S3 bucket.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> Clearly the only option that meets the "highly available" and "lowest possible RPO and RTO" is the one that speaks about cross-AZ deployment of S/4HANA.
</details>


## Question 44

A company migrates an existing SAP Java system to an Amazon EC2 instance. After the migration, the SAP application server is shutting down because the SAP license has expired or is not valid. Which actions should an SAP solutions architect take to make the SAP application server operational again? (**Select TWO.**)

 - A. Reinstall the SAP application server.
 - B. Purchase a license from SAP.
 - C. Ensure that SAP is running on a supported EC2 instance type.
 - D. Apply for a new regular SAP license for the new hardware key that was generated for the EC2 instance.
 - E. Ensure that the Amazon CloudWatch agent is installed at the operating system level.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: CD

> 
</details>


## Question 45

An SAP solutions architect needs to secure an Amazon EC2 instance that hosts an SAP HANA database on AWS. The SAP solutions architect must encrypt the database at rest. In addition, the data in transit between the frontend users and the SAP application on AWS must always be encrypted from end to end. Which combination of steps should the SAP solutions architect take to meet these requirements? (**Select TWO.**)

 - A. Stop the EC2 instance. Enable encryption on the existing Amazon Elastic Block Store (Amazon EBS) volumes. Start the EC2 instance with encrypted EBS volumes for the SAP HANA database.
 - B. Stop the EC2 instance. Create a snapshot of the Amazon Elastic Block Store (Amazon EBS) volumes. Create an encrypted copy of the snapshots. Create new encrypted EBS volumes from the encrypted snapshots. Attach the new volumes to the EC2 instance. Start the EC2 instance.
 - C. Use AWS Client VPN to connect the frontend users to the SAP application on AWS.
 - D. Configure TLS encryption at the SAP application level for encryption of data in transit.
 - E. Use AWS Direct Connect and AWS Site-to-Site VPN for encryption of data in transit.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: BE

> https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html#encryption-parameters
</details>


## Question 46

A company is implementing SAP S/4HANA on AWS. The company‘s operating system is SUSE Linux Enterprise Server for SAP. The company is deploying its development instances and QA instances in one Availability Zone. The company is deploying its production instance in a different Availability Zone. The company wants to avoid a single point of failure when creating the SAP transport directory. Which storage solution should the company use to meet these requirements?

 - A. Amazon S3
 - B. Amazon Elastic Block Store (Amazon EBS) Multi-Attach volume
 - C. Amazon Elastic File System (Amazon EFS)
 - D. AWS Storage Gateway Volume Gateway

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

>  
</details>


## Question 47

A company plans to migrate its SAP workloads to AWS. The company needs to install an SAProuter that has a connection to the SAP support network. Which combination of steps should an SAP solutions architect take to meet this requirement? (**Select THREE.**)

 - A. Launch the instance that the SAProuter software is installed on into a public subnet of the VPC.
 - B. Launch the instance that the SAProuter software is installed on into a private subnet of the VPC.
 - C. Assign the SAProuter instance an Elastic Fabric Adapter (EFA) and a dynamic IP address.
 - D. Assign the SAProuter instance an elastic network interface and a static Elastic IP address.
 - E. Create a specific security group for the SAProuter instance with rules to allow the required access to the SAP support network.
 - F. Create a specific network ACL for the SAProuter instance with rules to allow the required access to the SAP support network.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: ADE

> SAProuter needs an EC2 deployed into a public subnet with an Elastic IP (fixed public IP) with a Security group to enable the SAP support network inbound/outbound connections.
</details>


## Question 48

A company runs SAP on AWS and has deployed a production SAP S/4HANA database on an Amazon EC2 instance. The company decides to use AWS Backint Agent for SAP HANA (AWS Backint agent) to back up the database directly to Amazon S3. A solutions architect installs and configures the first AWS Backint agent on Friday and schedules a backup on Sunday morning. On Monday, the solutions architect notices that the backup failed. The solutions architect observes the following error in the logs: “Error performing backup AccessDenied: Access Denied status code: 403“ Which of the following could be the cause of this error?

 - A. The S3 bucket that is used to store the backup is not publicly accessible.
 - B. S3 Versioning is not enabled, so the SAP HANA database cannot guarantee consistency in the backups.
 - C. The SAP HANA SYSTEM database user is deactivated.
 - D. The IAM role that was configured during the setup of the SAP HANA database EC2 instance does not have the required permissions

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

> 
</details>


## Question 49

A company recently migrated its SAP workloads to AWS. An SAP technology administrator needs to create an incident with SAP OSS Support. After 2 hours, the incident comes back with the status of “Pending Customer.“ SAP OSS Support cannot access the required performance and configuration data on the system. Which combination of steps should the SAP technology administrator take to resolve this issue? (**Select TWO.**)

 - A. Restart the SAProuter that is being used for the SAP support network.
 - B. Enable Amazon CloudWatch detailed monitoring.
 - C. Turn on AWS CloudTrail.
 - D. Run SAP transaction OSS1 and configure the AWS specific settings.
 - E. Install and activate the AWS Data Provider for SAP.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: BE

> 
</details>


## Question 50

An SAP engineer deploys an SAP S/4HANA system on AWS. After logging in to the system by using the SAP GUI, the SAP engineer receives an alert that transaction ST06N is missing. What should the SAP engineer do to resolve this error?

 - A. Reboot the SAP S/4HANA application server.
 - B. Configure the AWS CLI on the SAP instance. Develop a script by using the AWS CLI to get related data.
 - C. Install the Amazon CloudWatch agent on the SAP instance.
 - D. Install the AWS Data Provider for SAP on the SAP instance.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

    > 
</details>


## Question 51

A company is planning to move its production SAP S/4HANA workload to AWS. The company needs high availability for the workload. An SAP consultant needs to use private network settings for all communications between the on-premises environment and the VPC that contains the Amazon EC2 instances that host the SAP S/4HANA workload. The SAP consultant is planning to use Red Hat Enterprise Linux for SAP to configure the systems for high availability. The SAP consultant must ensure that the end users can access the SAP S/4HANA system by using SAP GUI from the on-premises network. Which solutions will meet these requirements? (**Select TWO**)

 - A. Overlay IP address with AWS Transit Gateway
 - B. Overlay IP address with an Application Load Balancer
 - C. Overlay IP address with a Network Load Balancer
 - D. Elastic IP address with AWS Transit Gateway
 - E. Elastic IP address with a Network Load Balancer

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: AC

> D and E discarded since HA implies overlay IP (elastic IP means fixed public IP). B discarded because SAPGUI is not compliant with ALB.
</details>


## Question 52

A company has an on-premises SAP NetWeaver ABAP 7.4 system that runs on an AIX operating system with IBM Db2 as the database platform. The company plans to migrate the system to AWS with no change to the SAP version or the Db2 version. On AWS, the SAP workload will use SUSE Linux Enterprise Server as the operating system and will use Db2 as the database platform. How should the company export data from the current system to build the SAP system on AWS?

 - A. Use SAP Software Provisioning Manager 1.0.
 - B. Use AWS Database Migration Service (AWS DMS).
 - C. Use AWS Server Migration Service (AWS SMS).
 - D. Use AWS Application Migration Service (CloudEndure Migration).

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> It's an heterogeneous system copy, so SWPM must be used to perform the export/import due to the change of endianness from AIX to x64 on AWS.
</details>


## Question 53

A power utility company needs to migrate its SAP IS-U system to AWS. The company‘s on-premises SAP ERP Central Component (SAP ECC) 6 system runs on a Microsoft SQL Server database and is hosted on Windows Server 2019 physical servers. The company wants to migrate its SAP system by using the least effort and amount of time. The migration solution also requires the least possible number of system changes during the move. Which migration solution will meet these requirements?

 - A. Use AWS Application Migration Service (CloudEndure Migration) to replicate the SAP system to AWS. Continue replicating storage until migration cutover.
 - B. Perform a system export of the source database content from the on-premises SAP system by using R3load. Use SAP Software Provisioning Manager to install a new SAP system on AWS. Import the database content to the new SAP system on AWS. Replay the database logs from the on-premises SAP system during the migration cutover window to catch up business transactions.
 - C.  Perform a native SQL Server database backup for the on-premises SAP system. Use SAP Software Provisioning Manager to install a new SAP system on AWS. Restore the SQL Server database backup from the on-premises SAP system to the new system on AWS. Replay the database logs from the on-premises SAP system during the migration cutover window to catch up business transactions.
 - D. Perform a native SQL Server database backup for the on-premises SAP system. Use SAP Software Provisioning Manager to install a new SAP system on AWS. Restore the SQL Server database backup from the on-premises SAP system to the new system on AWS. Set up SQL Server Always On replication between the on-premises SAP system and the SAP system on AWS.

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> 
</details>


## Question 54

A Singapore based retail company wants to host their SAP S/4 HANA system with the production HANA database size of 18 TB on AWS. The company management wants to closely monitor the cost associated with running the production workloads on AWS. This will be the first time the company will be using AWS to run its workloads. How should an SAP solution architect deploy the SAP workload to meet these requirements?

 - A. Create separate production and non-production AWS accounts for SAP workloads. Set up dedicated VPCs and subnets for the newly created accounts
 - B. Create separate production and non-production AWS accounts for SAP workloads. Use AWS Resource Access Manager (RAM) to share the VPCs and subnets between the newly created accounts
 - C. Create a single account for SAP workloads. Set up dedicated VPCs and subnets for production and non-production SAP systems. Use tagging to mark the EC2 instances as production or non-production
 - D. Create a single account for SAP workloads. Set up a single VPC and dedicated subnets for production and non-production SAP systems. Use tagging to mark the EC2 instances as production or non-production

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> Options C and D discarded because separate non-prod vs prod in different accounts is a best practice. The idea to split them is to keep different administration, so RAM is no prescribed here for this.
</details>


## Question 55

A US based financial company is implementing SAP S/4 HANA on AWS. The database size is 12 TB, and they will implement the HANA database on SUSE Linux Enterprise Server (SLES) for SAP. The database instance needs to access S3 to store backups and access files. The requirement is that the data transfer should happen within the AWS network for security reasons. How can this be achieved?

 - A. Place the HANA database in a public subnet and access S3 using the Internet Gateway
 - B. Place the HANA database in a private subnet and access S3 using NAT Gateway
 - C. Place the HANA database in a private subnet and access S3 using the Internet Gateway
 - D. Place the HANA database in a private subnet and access S3 using Gateway Endpoints

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

> Gateway VPC endpoints provide reliable connectivity to Amazon S3 and DynamoDB without requiring an internet gateway or a NAT device for your VPC. Gateway endpoints do not use AWS PrivateLink, unlike other types of VPC endpoints. See https://docs.aws.amazon.com/vpc/latest/privatelink/gateway-endpoints.html.
</details>


## Question 56

You are an SAP solution architect with a company that is running their SAP S/4 HANA 1909 system on AWS. The SAP application is running on a single m6i.8xlarge EC2 instance. It has been observed in the last few months, that during the month-end payroll run, the workload on the system suddenly increases, and users report performance problems. After doing the root cause analysis it was found that the performance problem is because of the shortage of resources. What is the most cost-effective approach you would suggest to address this problem?

 - A. Scale up the SAP application server to m6i.16xlarge instance
 - B. Add the required resources by spinning up the spot instances during the duration of the payroll run
 - C. Scale out the SAP application server by adding another m6i.8xlarge instance
 - D. Add the required resources by spinning up the on-demand instances during the duration of the payroll run
 - E. Add the required resources by spinning up the reserved instances during the duration of the payroll run

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

> Spot instances can be stopped unexpectedly. On-Demmand could not be available when required but it's the most cost-effective compared with a reserved additional EC2 instance.
</details>


## Question 57

A London based Banking customer wants to deploy SAP S/4 HANA 2021 on the AWS environment. The customer wants to deploy the development and quality system as a single-system deployment, however, wants high availability for the production system. The production SAP application, as well as the database, must have an availability of 99.9% or more. Which solution design will meet these requirements for the production system?

 - A. Install SAP ASCS instance and ERS instance on one Amazon EC2 instance. Use an SAP-certified cluster monitoring solution in different Availability zones. Create Amazon Elastic Block Store (Amazon EBS) snapshots each hour. Configure an active-standby database setup. Deploy at least two SAP application servers in a single Availability Zone Install SAP ASCS
 - B. instance and ERS instance on separate Amazon EC2 instances. Use an SAP-certified cluster monitoring solution in different Availability zones. Configure an active-standby database setup with cluster monitoring. Deploy at least two application servers that extend across multiple availability zones within the region
 - C. Install SAP ASCS instances, primary application server (PAS), and a database instance on separate Amazon EC2 instances. Schedule Amazon Elastic Block Store (EBS) snapshots every 10 minutes. Schedule database log backups every 10 minutes
 - D. Install SAP ASCS instances, ERS instances, and a database instance on one Amazon EC2 instance. Install SAP application servers in the same subnet as the database instance. User AWS Elastic Disaster Recovery( CloudEndure Disaster Recovery) to continuously replicate the SAP S/4 HANA system to the standby AWS Region
 - E. Install SAP ASCS instance and ERS instance on separate Amazon EC2 instances. Use an SAP-certified cluster monitoring solution in different Availability zones. Configure an active-standby database setup with cluster monitoring. Deploy at least one application server in one Availability Zone

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: B

> 
</details>


## Question 58

A company that is planning to migrate to AWS are currently running their SAP workloads on-premise on ECC 6 on Oracle database. The entire SAP solution is running on SUSE Enterprise Linux Server (SLES). The company has no plans to migrate to S/4 HANA systems in near future. What are the changes in architecture a solution architect needs to support the existing SAP + Oracle workload on AWS? (**Select Two**)

 - A. Migrate the database to HANA as Oracle is not supported on AWS
 - B. Migrate the database to Amazon Aurora as Oracle is not supported on AWS
 - C. Migrate the database operating system to Redhat Enterprise Linux (RHEL)
 - D. Migrate the database operating system to Oracle Linux (OL)
 - E. No change is required in the operating system type
 - F. No change is required in the database type

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: DF

> 
</details>


## Question 59

A US-based oil and gas company is planning to migrate their existing SAP landscape from On-premise to AWS cloud. Their SAP landscape consists of both Linux and Windows-based SAP systems. The company is planning to use a high availability setup for the SAP application servers where multiple application servers will be deployed across two availability zones for a single highly available SAP system. What type of storage solution should the company choose for the transport directory in SAP? (**Select Two**)

 - A. Choose Elastic Block Store(EBS) volumes for both Linux and Windows-based SAP systems as they can span across multiple availability zones
 - B. Choose Amazon FSx for Window-based SAP systems as they can span across availability zones
 - C. Choose Elastic File System (EFS) for Linux-based SAP systems as they can span across multiple availability zones
 - D. Choose an S3 bucket for both Linux and Windows-based SAP systems as they can span across multiple availability zones

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> 
</details>


## Question 60

You are an SAP Technical architect with a US-based firm from N. Virginia, which is planning to start its SAP operations in Europe. Your company wants to use AWS for this new SAP Workload. The users and customers for this workload will be primarily from Germany. As per the law, you must comply with the GDPR requirements. Your company also have rigid multi-country disaster recovery requirement. Which of the following Disaster Recovery architecture do you propose for maximum resiliency?

 - A. Select the AWS Region in us-east-1 (N. Virginia) for the new SAP Workload. Use multiple availability zones to place the SAP Workload
 - B. Select the AWS Region in eu-central-1 (Frankfurt) for their new SAP Workload. Use us-east-1 (N. Virginia) as Disaster Recovery Region
 - C. Select the AWS Region in eu-central-1 (Frankfurt) for their new SAP Workload. Use eu-west-3 (Paris) as a Disaster Recovery Region
 - D. Select the AWS Region in us-east-1 (N. Virginia) for their new SAP Workload. Use eu-central-1 (Frankfurt) as Disaster Recovery Region

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> GDPR means that EU data can not leave EU
</details>


## Question 61

A US-based company from the media and entertainment sector has acquired a business in Europe. They plan to set up a new SAP S/4 HANA 2020 landscape in the AWS eu-central-1 (Frankfurt) region. They are looking for a high availability setup for the production environment and have very tight deadlines to build the environment. Which of the following solution will help the company to achieve this requirement ?

 - A. Create an AWS CloudFormation template to automate the deployment of the SAP S/4 HANA systems and related compute and storage resources for all the environments
 - B. Create and Launch EC2 instance by using launch templates. Use Software Provisioning Manager (SWPM) to install S/4 HANA 2020 non-production environment. Manually deploy a high availability cluster for the production S/4 HANA 2020 instance
 - C. Create and Launch EC2 instance by using launch templates. Use Software Provisioning Manager (SWPM) to install S/4 HANA 2020 non-production environment. Use AWS launch wizard for SAP to deploy a high availability cluster for the production SAP S/4HANA 2020 instance
 - D. Use AWS launch wizard for SAP to deploy S/4 HANA 2020 in single-instance deployment mode for non-production systems and in high availability deployment mode for production systems
 - E. Use SAP Cloud Appliance Library (CAL) to deploy S/4 HANA 2020 for both production and non-production environments. Manually deploy a high availability cluster for the production S/4 HANA 2020 instance

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: D

> 
</details>


## Question 62

You are an SAP solution architect in a manufacturing company. They are running their workloads on SAP ECC 6 EHP 4 system on DB2 on SUSE Linux. The company‘s hardware support with the current vendor will be ending within 2 years. They want to utilize this opportunity to migrate to AWS. They are also planning to upgrade their system to S/4 HANA 2020 FPS 2. As an SAP solution architect, which of the following migration paths should you recommend for migration with minimum downtime?

 - A. Upgrade SAP ECC 6 EHP 4 system to EHP 8. Perform an export with SUM DMO with system move. Build the target system on AWS. Run the import process of SUM DMO with system move
 - B. Upgrade SAP ECC 6 EHP 4 system to EHP 8. Perform a heterogeneous export with SWPM. Build the target system on AWS. Run the import process of SWPM on the target system
 - C. Upgrade SAP ECC 6 EHP 4 system to EHP 8. Upgrade the system from EHP 8 to S/4 HANA 2021 with SUM DMO
 - D. Upgrade SAP ECC 6 EHP 4 system to EHP 8. Perform a backup of the source database. Build the target system on AWS. Restore the database on the target system

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

> Keyword DMO with system move is usually the correct one. Options B, C and D discarded because at the end you only have an EHP8 on AWS or a different S/4HANA release. 
</details>


## Question 63

A customer is running SAP S/4 HANA 2021 on-premise. The customer‘s data center is connected to the AWS network with a Direct Connect connection. Which of the following approaches will help the customer to move their S/4 HANA system to AWS with the least amount of downtime?

 - A. SAP HANA backup and restore method
 - B. SAP HANA homogeneous system copy using SWPM
 - C. SAP HANA System Replication (HSR)
 - D. SAP HANA heterogeneous system copy using SWPM

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> 
</details>


## Question 64

A customer is planning to migrate their SAP Netweaver BW 7.4 system running on Oracle database on SUSE Linux, on-premise to AWS. Which of the following methods will take the shortest amount of time?

 - A. A migration of virtual machine using AWS Server Migration Service (SMS)
 - B. A heterogeneous SAP copy using Software Provisioning Manager (SWPM)
 - C. A SAP SUM database Migration option (DMO) with system move
 - D. A migration of BW application using AWS Application Migration Service (MGN)
 - E. A homogeneous SAP copy using Software Provisioning Manager (SWPM)

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: E

> Option A must be discarded because the current OS is different than Oracle Linux. Option B seems valid but it's not typically the "shortest". Option C can not be used if target is Oracle. Option D can not be used for an SAP BW. Option E is valid since the OS endianness from source to target is the same and if DB release be kept, then it's feasible and it typically offers shorter times than export/import.
</details>


## Question 65

A global utility company is running an SAP S/4HANA system with 15TB of data on-premises. They want to migrate their SAP landscape to AWS to reduce operational costs. The on-premises data center is connected to an AWS Region through a Direct Connect connection and full bandwidth is available for the SAP migration project. Which of the following solutions will meet these requirements with minimal downtime?

 - A. Use SAP Software Update Manager (SUM) Database Migration Option (DMO) with System Move for migration
 - B. Use SAP classical R3load export/import
 - C. Use SAP HANA system replication
 - D. Use SAP HANA backup and restore method

<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: C

> Move of HANA data from A to B with minimal downtime always HSR
</details>


