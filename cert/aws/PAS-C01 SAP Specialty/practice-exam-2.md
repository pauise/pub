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
Correct answer: BE

> SAP workloads always in private subnet, so A discarded. The HANA version of the restore target must be always greater or equal to the backup source one, so B valid and C discarded. And to perform any system copy with HANA you always need SYSTEMDB and tenant db, so E valid and D discarded.
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


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>


## Question 



<details markdown=1><summary markdown='span'>Answer</summary>
Correct answer: A

    > 
</details>

Please feel free to comment below if any information is inaccurate or if any answers need correction.


