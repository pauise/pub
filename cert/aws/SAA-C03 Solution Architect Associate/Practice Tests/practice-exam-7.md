# Practice Exam 7

Click on the **Answer** button for the correct answer and its explanation.

If this practice exam has been helpful to you please share it with others and react to this below.

---

1. Your application is deployed on EC2 instances fronted by an Application Load Balancer. Recently, your infrastructure has come under attack. Attackers perform over 100 requests per second, while your normal users only make about 5 requests per second. How can you efficiently prevent attackers from overwhelming your application? 

	- A. Use a Web Application Firewall and setup a rate-based rule
	- B. Configure Sticky Sessions on the Application Load Balancer
	- C. Define a Network ACL (NACL) on your Application Load Balancer
	- D. Use AWS Shield Advanced and setup a rate-based rule
	
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>


2. The engineering team at a multi-national company uses AWS Firewall Manager to centrally configure and manage firewall rules across its accounts and applications using AWS Organizations. Which of the following AWS resources can the AWS Firewall Manager configure rules on? (**Select three**)
	- A. AWS WAF
	- B. AWS Shield Advanced
	- C. VPC Security Groups
	- D. Amazon GuardDuty
	- E. Amazon Inspector

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, B, C
    </details>

3. The engineering team at a startup is evaluating the most optimal block storage volume type for the EC2 instances hosting its flagship application. The storage volume should support very low latency but it does not need to persist the data when the instance terminates. As a solutions architect, you have proposed using Instance Store volumes to meet these requirements. Which of the following would you identify as the key characteristics of the Instance Store volumes? (**Select two**)
	- A. You can't detach an instance store volume from one instance and attach it to a different instance
	- B. If you create an AMI from an instance, the data on its instance store volumes isn't preserved
	- C. Instance store is reset when you stop or terminate an instance. 
	- D. Instance store data is preserved during hibernation
	- E. You can specify instance store volumes for an instance when you launch or restart it
	- F. An instance store is a network storage type
	
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, C
	    
	> Instance Store is local attached physical disk and data persists only in case an instance store-backed AMI created from the instance, and instance reboot. All other cases the data is lost. So, D and F are false while A, B and C are TRUE. B is also TRUE but not in all cases and it's not a key characteristic for this case. Finally, the number, size, and type of instance store volumes are determined by the instance type and instance size. So, you can not specify instance store volumes and then E is FALSE. 

	> See more https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html and https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-store-volumes.html
    </details>
    
4. A Big Data consulting company runs large distributed and replicated workloads on the on-premises data center. The company now wants to move these workloads to Amazon EC2 instances by using the placement groups feature and it wants to minimize correlated hardware failures. Which of the following represents the correct placement group configuration for the given requirement?
	- A. Partition placement groups
	- B. Cluster placement groups 
	- C. Spread placement groups
	- D. Multi-AZ placement groups

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C

	> Cluster – Packs instances close together inside an Availability Zone. This strategy enables workloads to achieve the low-latency network performance necessary for tightly-coupled node-to-node communication that is typical of high-performance computing (HPC) applications. So, B FALSE.

	> Partition – Spreads your instances across logical partitions such that groups of instances in one partition do not share the underlying hardware with groups of instances in different partitions. This strategy is typically used by large distributed and replicated workloads, such as Hadoop, Cassandra, and Kafka. So, A FALSE.

	> Spread – Strictly places a small group of instances across distinct underlying hardware to reduce correlated failures. So, C TRUE.

	> Multi-AZ placement groups do not exist! So, D FALSE.

	> https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html
   </details>

6. Your e-commerce application is using an RDS PostgreSQL database and an analytics workload also runs on the same database. When the analytics workload is run, your e-commerce application slows down which further affects your sales. Which of the following is the MOST cost-optimal solution to fix this issue?
	- A. Create a Read Replica in the same Region as the Master database and point the analytics workload there 
	- B. Enable Multi-AZ for the RDS database and run the analytics workload on the standby database
	- C. Migrate the analytics application to AWS Lambda
	- D. Create a Read Replica in another Region as the Master database and point the analytics workload there

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
      
	> A Multi-AZ DB instance deployment has one standby DB instance that provides failover support, but doesn't serve read traffic. So, B FALSE.

	> Option C does not makes sense. The data are on DB, does not matter if it's Lambda or an app on an EC2 who is accessing.

	> If you place the DB in a different Region than the app which is accessing to it will be a dramatic increase of DB access time. For sure the DB must be in the same Region than the app. So, D FALSE and then only A is TRUE.

	> See https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZ.html and https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html.

6. A company needs an Active Directory service to run directory-aware workloads in the AWS Cloud and it should also support configuring a trust relationship with any existing on-premises Microsoft Active Directory. Which AWS Directory Service is the best fit for this requirement?
	- A. AWS Managed Microsoft AD
	- B. AD Connector
	- C. Simple AD
	- D. AWS Transit Gateway

</details>

7. A company is developing a document management application on AWS. The application runs on EC2 instances in multiple Availability Zones. The company requires the document store to be highly available and the documents need to be returned immediately when requested. The engineering team has configured the application to use EBS to store the documents but the team is willing to consider other options to meet the availability requirement. As a solutions architect, which of the following will you recommend? 
	- A. Set up Amazon EBS as the EC2 instance root volume and then configure the application to use S3 as the document store
	- B. Set up Amazon EBS as the EC2 instance root volume and then configure the application to use S3 Glacier as the document store
	- C. Create snapshots for the EBS volumes regularly and then build new volumes using those snapshots in additional Availability Zones
	- D. Provision at least three Provisioned IOPS EBS volumes for the EC2 instances and then mount these volumes to the EC2 instances in a RAID 5 configuration

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>


8. The CTO of an online home rental marketplace wants to re-engineer the caching layer of the current architecture for its relational database. The CTO wants the caching layer to have replication and archival support built into the architecture. Which of the following AWS service offers the capabilities required for the re-engineering of the caching layer?
	- A. ElastiCache for Redis
	- B. ElastiCache for Memcached
	- C. DynamoDB Accelerator (DAX)
	- D. DocumentDB

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A

	> DocumentDB does not have caching layer and neither DocumentDB neither DAX cache are a "relational" DB as stated, but a No-SQL instead. So, according to https://aws.amazon.com/elasticache/redis-vs-memcached/ Memcached does not support built-in replication. No mention to archival but definetly Redis has more features than Memcached. so, A is TRUE.
    </details>

9. A company is deploying a web application and it wants to ensure that only the web tier of the application is publicly accessible. To accomplish this, the engineering team has designed the VPC with a public subnet and a private subnet. The application will be hosted on several EC2 instances in an Auto Scaling group. The team also wants TLS termination to be offloaded from the EC2 instances. Which solution should a solutions architect implement to address these requirements?
	- A. Set up a Network Load Balancer in the public subnet. Create an Auto Scaling group in the private subnet and associate it with the Network Load Balancer 
	- B. Set up a Network Load Balancer in the public subnet. Create an Auto Scaling group in the public subnet and associate it with the Network Load Balancer
	- C. Set up a Network Load Balancer in the private subnet. Create an Auto Scaling group in the public subnet and associate it with the Network Load Balancer
	- D. Set up a Network Load Balancer in the private subnet. Create an Auto Scaling group in the private subnet and associate it with the Network Load Balancer.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A

      > The ALB/NLB must be placed in the public subnet, so C and D FALSE, and the auto-scaling group is regarding EC2 set of instances which is typically placed in the private subnet (behind of the ALB/NLB), so B FALSE and A TRUE.
    </details>

10. An application running on an EC2 instance needs to access a DynamoDB table in the same AWS account. Which of the following solutions should a solutions architect configure for the necessary permissions?
	- A. Set up an IAM service role with the appropriate permissions to allow access to the DynamoDB table. Configure an instance profile to assign this IAM role to the EC2 instance
	- B. Set up an IAM user with the appropriate permissions to allow access to the DynamoDB table. Store the access credentials in an S3 bucket and read them from within the application code directly
	- C. Set up an IAM user with the appropriate permissions to allow access to the DynamoDB table. Store the access credentials in the local storage and read them from within the application code directly
	- D. Set up an IAM service role with the appropriate permissions to allow access to the DynamoDB table. Add the EC2 instance to the trust relationship policy document so that the instance can assume the role.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D

	> Trust policies establish the trust relationship between an IAM role and the entities that are allowed to assume it. Permission policies, on the other hand, define the specific permissions and actions that an IAM user, group, or role is allowed or denied within AWS services and resources. Together, trust policies and permission policies work in tandem to ensure proper access control and security within an AWS environment (https://www.linkedin.com/pulse/permission-policy-vs-trust-aws-rupesh-tiwari/).

	> A service role is a role that an AWS service assumes to perform actions on your behalf. So, an EC2 instance can assume a service role while a specific user can assume a (w/o "service") role.

    	> Even DynamoDB has some constraints regarding IAM as per https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/security_iam_service-with-iam.html 

    	> Finally, B, C are incorrect because the action must be allowed to an AWS service (EC2). A is incorrect because a **resource** policy JSON doc can not be used to assign a role neither a service role to that resource, but a trust relationship policy document instead. So D.
    </details>



D

11. A development team wants to ensure that all objects uploaded to an Amazon S3 bucket are encrypted. Which of the following options represents the correct solution?
	- A. Configure the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set
	- B. Configure the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set to private
	- C. Configure the bucket policy to deny if the PutObject does not have an aws:SecureTransport header set to true
	- D. Configure the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set

B

12. A photo-sharing company is storing user profile pictures in an S3 bucket and an image analysis application is deployed on four EC2 instances. A solutions architect would like to trigger an image analysis procedure only on one of the four EC2 instances for each photo uploaded. What do you recommend?
	- A. Create an S3 Event Notification that sends a message to an SQS queue. Make the EC2 instances read from the SQS queue
	- B. Subscribe the EC2 instances to the S3 Inventory stream
	- C. Create a CloudWatch Event that reacts to objects uploads in S3 and invokes one of the EC2 instances
	- D. Create an S3 Event Notification that sends a message to an SNS topic. Subscribe the EC2 instances to the SNS topic.

D

13. An engineering team wants to orchestrate multiple Amazon ECS task types running on EC2 instances that are part of the ECS cluster. The output and state data for all tasks need to be stored. The amount of data output by each task is approximately 20 MB and there could be hundreds of tasks running at a time. As old outputs are archived, the storage size is not expected to exceed 1 TB. As a solutions architect, which of the following would you recommend as an optimized solution for high-frequency reading and writing?
	- A. Use Amazon EFS with Provisioned Throughput mode
	- B. Use Amazon EFS with Bursting Throughput mode
	- C. Use an Amazon EBS volume mounted to the ECS cluster instances
	- D. Use a DynamoDB table that is accessible by all ECS cluster instances

B

14. As a Solutions Architect, you would like to completely secure the communications between your CloudFront distribution and your S3 bucket which contains the static files for your website. Users should only be able to access the S3 bucket through CloudFront and not directly. What do you recommend?
	- A. Create an origin access identity (OAI) and update the S3 Bucket Policy
	- B. Update the S3 bucket security groups to only allow traffic from the CloudFront security group
	- C. Make the S3 bucket public 
	- D. Create a bucket policy to only authorize the IAM role attached to the CloudFront distribution.

A

15. A company is experiencing stability issues with their cluster of self-managed RabbitMQ message brokers and the company now wants to explore an alternate solution on AWS. As a solutions architect, which of the following AWS services would you recommend that can provide support for quick and easy migration from RabbitMQ?
	- A. Amazon MQ
	- B. Amazon Simple Notification Service (Amazon SNS)
	- C. Amazon SQS Standard
	- D. Amazon SQS FIFO (First-In-First-Out).

A

16. A healthcare company wants to run its applications on single-tenant hardware to meet compliance guidelines. Which of the following is the MOST cost-effective way of isolating the Amazon EC2 instances to a single tenant?
	- A. Dedicated Instances
	- B. Spot Instances
	- C. Dedicated Hosts
	- D. On-Demand Instances.

A

17. A company's real-time streaming application is running on AWS. As the data is ingested, a job runs on the data and takes 30 minutes to complete. The workload frequently experiences high latency due to large amounts of incoming data. A solutions architect needs to design a scalable and serverless solution to enhance performance. Which combination of steps should the solutions architect take? (**Select two**)
	- A. Set up Amazon Kinesis Data Streams to ingest the data
	- B. Set up AWS Fargate with Amazon ECS to process the data
	- C. Set up AWS Database Migration Service (AWS DMS) to ingest the data
	- D. Set up AWS Lambda with AWS Step Functions to process the data
	- E. Provision EC2 instances in an Auto Scaling group to process the data

B,D

18. A Big Data company wants to optimize its daily Extract-Transform-Load (ETL) process that migrates and transforms data from its S3 based data lake to a Redshift cluster. The team wants to manage this daily job in a serverless environment. Which AWS service is the best fit to manage this process without the need to configure or manage the underlying compute resources?
	- A. AWS Glue
	- B. AWS Data Pipeline
	- C. Amazon EMR
	- D. AWS Database Migration Service (DMS).

B

19. You are using AWS Lambda to implement a batch job for a big data analytics workflow. Based on historical trends, a similar job runs for 30 minutes on average. The Lambda function pulls data from Amazon S3, processes it, and then writes the results back to S3. When you deployed your AWS Lambda function, you noticed an issue where the Lambda function abruptly failed after 15 minutes of execution. As a solutions architect, which of the following would you identify as the root cause of the issue?
	- A. The AWS Lambda function is timing out
	- B. The AWS Lambda function is running out of memory
	- C. The AWS Lambda function chosen runtime is wrong
	- D. The AWS Lambda function is missing IAM permissions.

A

20. A Big Data analytics company is using a fleet of Amazon EC2 instances to ingest Internet-of-Things (IoT) data from various data sources. The data is in JSON format and ingestion rates can be as high as 1 MB/s. When an EC2 instance is restarted, the in-flight data is lost. The analytics team at the company wants to store as well as query the ingested data in near-real-time. Which of the following solutions provides near-real-time data querying that is scalable with minimal data loss?
	- A. Capture data in Amazon Kinesis Data Firehose with Amazon Redshift as the destination. Use Amazon Redshift to query the data
	- B. Capture data in an EC2 instance store and then publish this data to Amazon Kinesis Data Firehose with Amazon S3 as the destination.
	- C. Use Amazon Athena to query the data Capture data in an EBS volume and then publish this data to Amazon ElastiCache for Redis. Subscribe to the Redis channel to query the data
	- D. Capture data in Amazon Kinesis Data Streams. Use Kinesis Data Analytics to query and analyze this streaming data in real-time.

D

21. A company has moved its business critical data to Amazon EFS file system which will be accessed by multiple EC2 instances. As an AWS Certified Solutions Architect Associate, which of the following would you recommend to exercise access control such that only the permitted EC2 instances can read from the EFS file system? (**Select two**)
	- A. Use VPC security groups to control the network traffic to and from your file system
	- B. Use an IAM policy to control access for clients who can mount your file system with the required permissions
	- C. Use Network ACLs to control the network traffic to and from your Amazon EC2 instance
	- D. Set up the IAM policy root credentials to control and configure the clients accessing the EFS file system
	- E. Use Amazon GuardDuty to curb unwanted access to EFS file system.

B,C

22. The engineering team at a social media company has noticed that while some of the images stored in S3 are frequently accessed, others sit idle for a considerable span of time. As a solutions architect, what is your recommendation to build the MOST cost-effective solution?
	- A. Store the images using the S3 Intelligent-Tiering storage class
	- B. Store the images using the S3 Standard-IA storage class
	- C. Create a data monitoring application on an EC2 instance in the same region as the bucket storing the images. The application is triggered daily via CloudWatch and it changes the storage class of infrequently accessed objects to S3 One Zone-IA and the frequently accessed objects are migrated to S3 Standard class
	- D. Create a data monitoring application on an EC2 instance in the same region as the bucket storing the images. The application is triggered daily via CloudWatch and it changes the storage class of infrequently accessed objects to S3 Standard-IA and the frequently accessed objects are migrated to S3 Standard class.

B

23. An Auto Scaling group (ASG) has been created to work with an Application Load Balancer (ALB). The scaling group is configured with a minimum size value of 10, a maximum value of 30, and the desired capacity value of 20. One of the 20 EC2 instances has been reported as unhealthy. Which of the following actions will take place?
	- A. The ASG will terminate the EC2 Instance
	- B. The ASG will detach the EC2 instance from the group, and leave it running
	- C. The ASG will keep the instance running and re-start the application
	- D. The ASG will format the root EBS drive on the EC2 instance and run the User Data again.

A

24. During a review, a security team has flagged concerns over an Amazon EC2 instance querying IP addresses used for cryptocurrency mining. The EC2 instance does not host any authorized application related to cryptocurrency mining. Which AWS service can be used to protect the EC2 instances from such unauthorized behavior in the future?
	- A. Amazon GuardDuty
	- B. AWS Web Application Firewall (AWS WAF)
	- C. AWS Shield Advanced
	- D. AWS Firewall Manager

B

25. Your company is building a video streaming service accessible to users who have paid an ongoing subscription. The subscription data is stored in DynamoDB. You would like to expose the users to a serverless architecture allowing them to request the video files that sit on Amazon S3 and are distributed by CloudFront and protected by an origin access identity (OAI). Which of the following options can be combined to build a solution? (**Select two**)
	- A. Use AWS Lambda to generate the URL
	- B. Generate a CloudFront signed URL
	- C. Use DynamoDB triggers to generate the URL
	- D. Use API Gateway to generate the URL
	- E. Generate an S3 pre-signed URL
	
B,E
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>


