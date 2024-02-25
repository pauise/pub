# Practice Exam 3

Click on the **Answer** button for the correct answer and its explanation.

If this practice exam has been helpful to you please share it with others and react to this below.

---

1. An application runs on Amazon EC2 instances in private subnets. The application needs to access an Amazon DynamoDB table. What is the MOST secure way to access the table while ensuring that the traffic does not leave the AWS network?
    - A. Use the internet gateway attached to the VPC.
    - B. Use a NAT instance in a private subnet.
    - C. Use a NAT gateway in a public subnet.
    - D. Use a VPC endpoint for DynamoDB.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

2. A company runs a production application on a fleet of Amazon EC2 instances. The application reads the data from an Amazon SQS queue and processes the messages in parallel. The message volume is unpredictable and often has intermittent traffic. This application should continually process messages without any downtime. Which solution meets these requirements MOST cost-effectively?
    - A. Use Reserved Instances exclusively to handle the maximum capacity required.
    - B. Use Reserved Instances for the baseline capacity and use Spot Instances to handle additional capacity.
    - C. Use Spot Instances exclusively to handle the maximum capacity required.
    - D. Use Reserved Instances for the baseline capacity and use On-Demand Instances to handle additional capacity.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

3. A company wants to use high performance computing (HPC) infrastructure on AWS for financial risk modeling. The company’s HPC workloads run on Linux. Each HPC workflow runs on hundreds of Amazon EC2 Spot Instances, is short-lived, and generates thousands of output files that are ultimately stored in persistent storage for analytics and long-term future use. The company seeks a cloud storage solution that permits the copying of on-premises data to long-term persistent storage to make data available for processing by all EC2 instances. The solution should also be a high performance file system that is integrated with persistent storage to read and write datasets and output files. Which combination of AWS services meets these requirements?
    - A. Amazon S3 bucket with a VPC endpoint integrated with an Amazon Elastic Block Store (Amazon EBS) General Purpose SSD (gp2) volume
    - B. Amazon FSx for Windows File Server integrated with Amazon S3
    - C. Amazon S3 Glacier integrated with Amazon Elastic Block Store (Amazon EBS)
    - D. Amazon FSx for Lustre integrated with Amazon S3
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

4. A company wants to move its application to a serverless solution. The serverless solution needs to analyze existing and new data by using SL. The company stores the data in an Amazon S3 bucket. The data requires encryption and must be replicated to a different AWS Region. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Load the data into the existing S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Use Amazon Athena to query the data.
    - B. Load the data into the existing S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Use Amazon RDS to query the data.
    - C. Create a new S3 bucket. Load the data into the new S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with AWS KMS multi-Region kays (SSE-KMS). Use Amazon Athena to query the data.
    - D. Create a new S3 bucket. Load the data into the new S3 bucket. Use S3 Cross-Region Replication (CRR) to replicate encrypted objects to an S3 bucket in another Region. Use server-side encryption with AWS KMS multi-Region keys (SSE-KMS). Use Amazon RDS to query the data.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

5. A company wants to run applications in containers in the AWS Cloud. These applications are stateless and can tolerate disruptions within the underlying infrastructure. The company needs a solution that minimizes cost and operational overhead. What should a solutions architect do to meet these requirements?
    - A. Use Spot Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.
    - B. Use On-Demand Instances in an Amazon Elastic Kubernetes Service (Amazon EKS) managed node group.
    - C. Use On-Demand Instances in an Amazon EC2 Auto Scaling group to run the application containers.
    - D. Use Spot Instances in an Amazon EC2 Auto Scaling group to run the application containers.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

6. A company has two applications: a sender application that sends messages with payloads to be processed and a processing application intended to receive the messages with payloads. The company wants to implement an AWS service to handle messages between the two applications. The sender application can send about 1,000 messages each hour. The messages may take up to 2 days to be processed: If the messages fail to process, they must be retained so that they do not impact the processing of any remaining messages. Which solution meets these requirements and is the MOST operationally efficient?
    - A. Subscribe the processing application to an Amazon Simple Notification Service (Amazon SNS) topic to receive notifications to process. Integrate the sender application to write to the SNS topic.
    - B. Use an Amazon Kinesis data stream to receive the messages from the sender application. Integrate the processing application with the Kinesis Client Library (KCL).
    - C. Set up an Amazon EC2 instance running a Redis database. Configure both applications to use the instance. Store, process, and delete the messages, respectively.
    - D. Integrate the sender and processor applications with an Amazon Simple Queue Service (Amazon SQS) queue. Configure a dead-letter queue to collect the messages that failed to process.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

7. A company needs to save the results from a medical trial to an Amazon S3 repository. The repository must allow a few scientists to add new files and must restrict all other users to read-only access. No users can have the ability to modify or delete any files in the repository. The company must keep every file in the repository for a minimum of 1 year after its creation date. Which solution will meet these requirements?
    - A. Use an IAM role to restrict all users from deleting or changing objects in the S3 bucket. Use an S3 bucket policy to only allow the IAM role.
    - B. Use S3 Object Lock in governance mode with a legal hold of 1 year.
    - C. Use S3 Object Lock in compliance mode with a retention period of 365 days.
    - D. Configure the S3 bucket to invoke an AWS Lambda function every time an object is added. Configure the function to track the hash of the saved object so that modified objects can be marked accordingly.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

8. A company produces batch data that comes from different databases. The company also produces live stream data from network sensors and application APIs. The company needs to consolidate all the data into one place for business analytics. The company needs to process the incoming data and then stage the data in different Amazon S3 buckets. Teams will later run one-time queries and import the 
data into a business intelligence tool to show key performance indicators (KPIs). Which combination of steps will meet these requirements with the LEAST operational overhead? (**Choose two.**)
    - A. Use an AWS Glue extract, transform, and load (ETL) job to convert the data into JSON format. Load the data into multiple Amazon OpenSearch Service (Amazon Elasticsearch Service) clusters.
    - B. Use Amazon Athena for one-time queries. Use Amazon QuickSight to create dashboards for KPIs.
    - C. Use blueprints in AWS Lake Formation to identify the data that can be ingested into a data lake. Use AWS Glue to crawl the source, extract the data, and load the data into Amazon S3 in Apache Parquet format.
    - D. Use Amazon Kinesis Data Analytics for one-time queries. Use Amazon QuickSight to create dashboards for KPIs.
    - E. Create custom AWS Lambda functions to move the individual records from the databases to an Amazon Redshift cluster.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, C
    </details>

9. An ecommerce company has an order-processing application that uses Amazon API Gateway and an AWS Lambda function. The application stores data in an Amazon Aurora PostgreSQL database. During a recent sales event, a sudden surge in customer orders occurred. Some customers experienced timeouts, and the application did not process the orders of those customers. A solutions architect determined that the CPU utilization and memory utilization were high on the database because of a large number of open connections. The solutions architect needs to prevent the timeout errors while making the least possible changes to the application. Which solution will meet these requirements?
    - A. Create a read replica for the database in a different AWS Region. Use query string parameters in API Gateway to route traffic to the read replica.
    - B. Configure provisioned concurrency for the Lambda function. Modify the database to be a global database in multiple AWS Regions.
    - C. Use Amazon RDS Proxy to create a proxy for the database. Modify the Lambda function to use the RDS Proxy endpoint instead of the database endpoint.
    - D. Migrate the data from Aurora PostgreSQL to Amazon DynamoDB by using AWS Database Migration Service (AWS DMS). Modify the Lambda function to use the DynamoDB table.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

10. A media company is evaluating the possibility of moving its systems to the AWS Cloud. The company needs at least 10 TB of storage with the maximum possible I/O performance for video processing, 300 TB of very durable storage for storing media content, and 900 TB of storage to meet requirements for archival media that is not in use anymore. Which set of services should a solutions architect recommend to meet these requirements?
    - A. Amazon EC2 instance store for maximum performance, Amazon EFS for durable data storage, and Amazon S3 for archival storage
    - B. Amazon EBS for maximum performance, Amazon EFS for durable data storage, and Amazon S3 Glacier for archival storage
    - C. Amazon EC2 instance store for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage
    - D. Amazon EBS for maximum performance, Amazon S3 for durable data storage, and Amazon S3 Glacier for archival storage
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

11. A company has a data ingestion workflow that includes the following components: An Amazon Simple Notification Service (Amazon SNS) topic that receives notifications about new data deliveries An AWS Lambda function that processes and stores the data The ingestion workflow occasionally fails because of network connectivity issues. When failure occurs, the corresponding data is not ingested unless the company manually reruns the job. What should a solutions architect do to ensure that all notifications are eventually processed?
    - A. Modify the Lambda function's configuration to increase the CPU and memory allocations for the function.
    - B. Configure an Amazon Simple Queue Service (Amazon SQS) queue as the on-failure destination. Modify the Lambda function to process messages in the queue.
    - C. Configure the SNS topic’s retry strategy to increase both the number of retries and the wait time between retries.
    - D. Configure the Lambda function for deployment across multiple Availability Zones.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

12. An ecommerce company hosts its analytics application in the AWS Cloud. The application generates about 300 MB of data each month. The data is stored in JSON format. The company is evaluating a disaster recovery solution to back up the data. The data must be accessible in milliseconds if it is needed, and the data must be kept for 30 days. Which solution meets these requirements MOST cost-effectively?
    - A. Amazon RDS for PostgreSQL
    - B. Amazon S3 Glacier
    - C. Amazon S3 Standard
    - D. Amazon OpenSearch Service (Amazon Elasticsearch Service)
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

13. A reporting team receives files each day in an Amazon S3 bucket. The reporting team manually reviews and copies the files from this initial S3 bucket to an analysis S3 bucket each day at the same time to use with Amazon QuickSight. Additional teams are starting to send more files in larger sizes to the initial S3 bucket. The reporting team wants to move the files automatically analysis S3 bucket as the files enter the initial S3 bucket. The reporting team also wants to use AWS Lambda functions to run pattern-matching code on the copied data. In addition, the reporting team wants to send the data files to a pipeline in Amazon SageMaker Pipelines. What should a solutions architect do to meet these requirements with the LEAST operational overhead?
    - A. Configure S3 replication between the S3 buckets. Configure the analysis S3 bucket to send event notifications to Amazon EventBridge (Amazon CloudWatch Events). Configure an ObjectCreated rule in EventBridge (CloudWatch Events). Configure Lambda and SageMaker Pipelines as targets for the rule.
    - B. Create a Lambda function to copy the files to the analysis S3 bucket. Create an S3 event notification for the analysis S3 bucket. Configure Lambda and SageMaker Pipelines as destinations of the event notification. Configure s3:ObjectCreated:Put as the event type.
    - C. Configure S3 replication between the S3 buckets. Create an S3 event notification for the analysis S3 bucket. Configure Lambda and SageMaker Pipelines as destinations of the event notification. Configure s3:ObjectCreated:Put as the event type.
    - D. Create a Lambda function to copy the files to the analysis S3 bucket. Configure the analysis S3 bucket to send event notifications to Amazon EventBridge (Amazon CloudWatch Events). Configure an ObjectCreated rule in EventBridge (CloudWatch Events). Configure Lambda and SageMaker Pipelines as targets for the rule.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

14. A company is migrating its on-premises PostgreSQL database to Amazon Aurora PostgreSQL. The on-premises database must remain online and accessible during the migration. The Aurora database must remain synchronized with the on-premises database. Which combination of actions must a solutions architect take to meet these requirements? (**Choose two.**)
    - A. Create an ongoing replication task.
    - B. Create a database backup of the on-premises database.
    - C. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to monitor the database synchronization.
    - D. Create an AWS Database Migration Service (AWS DMS) replication server.
    - E. Convert the database schema by using the AWS Schema Conversion Tool (AWS SCT).

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, D
    </details>

15. A company is building a containerized application on premises and decides to move the application to AWS. The application will have thousands of users soon after it is deployed. The company is unsure how to manage the deployment of containers at scale. The company needs to deploy the containerized application in a highly available architecture that minimizes operational overhead. Which solution will meet these requirements?
    - A. Store container images in an Amazon Elastic Container Registry (Amazon ECR) repository. Use an Amazon Elastic Container Service (Amazon ECS) cluster with the Amazon EC2 launch type to run the containers. Use target tracking to scale automatically based on demand.
    - B. Store container images in a repository that runs on an Amazon EC2 instance. Run the containers on EC2 instances that are spread across multiple Availability Zones. Monitor the average CPU utilization in Amazon CloudWatch. Launch new EC2 instances as needed.
    - C. Create an Amazon EC2 Amazon Machine Image (AMI) that contains the container image. Launch EC2 instances in an Auto Scaling group across multiple Availability Zones. Use an Amazon CloudWatch alarm to scale out EC2 instances when the average CPU utilization threshold is breached.
    - D. Store container images in an Amazon Elastic Container Registry (Amazon ECR) repository. Use an Amazon Elastic Container Service (Amazon ECS) cluster with the AWS Fargate launch type to run the containers. Use target tracking to scale automatically based on demand.

   <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

16. A company wants to migrate its existing on-premises monolithic application to AWS. The company wants to keep as much of the front-end code and the backend code as possible. However, the company wants to break the application into smaller applications. A different team will manage each application. The company needs a highly scalable solution that minimizes operational overhead. Which solution will meet these requirements?
    - A. Host the application with AWS Amplify. Connect the application to an Amazon API Gateway API that is integrated with AWS Lambda.
    - B. Host the application on AWS Lambda. Integrate the application with Amazon API Gateway.
    - C. Host the application on Amazon EC2 instances. Set up an Application Load Balancer with EC2 instances in an Auto Scaling group as targets.
    - D. Host the application on Amazon Elastic Container Service (Amazon ECS). Set up an Application Load Balancer with Amazon ECS as the target.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

17. A company runs a web-based portal that provides users with global breaking news, local alerts, and weather updates. The portal delivers each user a personalized view by using mixture of static and dynamic content. Content is served over HTTPS through an API server running on an Amazon EC2 instance behind an Application Load Balancer (ALB). The company wants the portal to provide this content to its users across the world as quickly as possible. How should a solutions architect design the application to ensure the LEAST amount of latency for all users?
    - A. Deploy the application stack in two AWS Regions. Use an Amazon Route 53 geolocation routing policy to serve all content from the ALB in the closest Region.
    - B. Deploy the application stack in two AWS Regions. Use an Amazon Route 53 latency routing policy to serve all content from the ALB in the closest Region.
    - C. Deploy the application stack in a single AWS Region. Use Amazon CloudFront to serve the static content. Serve the dynamic content directly from the ALB.
    - D. Deploy the application stack in a single AWS Region. Use Amazon CloudFront to serve all static and dynamic content by specifying the ALB as an origin.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

18. A large media company hosts a web application on AWS. The company wants to start caching confidential media files so that users around the world will have reliable access to the files. The content is stored in Amazon S3 buckets. The company must deliver the content quickly, regardless of where the requests originate geographically. Which solution will meet these requirements?
    - A. Deploy AWS Global Accelerator to connect the S3 buckets to the web application.
    - B. Use AWS DataSync to connect the S3 buckets to the web application.
    - C. Use Amazon Simple Queue Service (Amazon SQS) to connect the S3 buckets to the web application.
    - D. Deploy Amazon CloudFront to connect the S3 buckets to CloudFront edge servers.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

19. A company has a multi-tier application that runs six front-end web servers in an Amazon EC2 Auto Scaling group in a single Availability Zone behind an Application Load Balancer (ALB). A solutions architect needs to modify the infrastructure to be highly available without modifying the application. Which architecture should the solutions architect choose that provides high availability?
    - A. Create an Auto Scaling group that uses three instances across each of two Regions.
    - B. Modify the Auto Scaling group to use three instances across each of two Availability Zones.
    - C. Change the ALB in front of the Amazon EC2 instances in a round-robin configuration to balance traffic to the web tier.
    - D. Create an Auto Scaling template that can be used to quickly create more instances in another Region.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

20. A company runs workloads on AWS. The company needs to connect to a service from an external provider. The service is hosted in the provider's VPC. According to the company’s security team, the connectivity must be private and must be restricted to the target service. The connection must be initiated only from the company’s VPC. Which solution will mast these requirements?
    - A. Create a VPC peering connection between the company's VPC and the provider's VPC. Update the route table to connect to the target service.
    - B. Ask the provider to create a VPC endpoint for the target service. Use AWS PrivateLink to connect to the target service.
    - C. Create a NAT gateway in a public subnet of the company’s VPUpdate the route table to connect to the target service.
    - D. Ask the provider to create a virtual private gateway in its VPC. Use AWS PrivateLink to connect to the target service.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

21. A solutions architect needs to securely store a database user name and password that an
application uses to access an Amazon RDS DB instance. The application that accesses the
database runs on an Amazon EC2 instance. The solutions architect wants to create a secure
parameter in AWS Systems Manager Parameter Store. What should the solutions architect
do to meet this requirement?
    - A. Create an IAM trust relationship between the Parameter Store parameter and the EC2 instance. Specify Amazon RDS as a principal in the trust policy.
    - B. Create an IAM policy that allows read access to the Parameter Store parameter. Allow Decrypt access to an AWS Key Management Service (AWS KMS) key that is used to encrypt the parameter. Assign this IAM policy to the EC2 instance.
    - C. Create an IAM trust relationship between the DB instance and the EC2 instance. Specify Systems Manager as a principal in the trust policy.
    - D. Create an IAM role that has read access to the Parameter Store parameter. Allow Decrypt access to an AWS Key Management Service (AWS KMS) key that is used to encrypt the parameter. Assign this IAM role to the EC2 instance.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

22. A company is running a multi-tier web application on premises. The web application is
containerized and runs on a number of Linux hosts connected to a PostgreSQL database
that contains user records. The operational overhead of maintaining the infrastructure and
capacity planning is limiting the company's growth. A solutions architect must improve the
application's infrastructure. Which combination of actions should the solutions architect
take to accomplish this? (**Choose two.**)
    - A. Set up an Amazon CloudFront distribution for the web application content.
    - B. Migrate the PostgreSQL database to Amazon Aurora.
    - C. Migrate the web application to be hosted on AWS Fargate with Amazon Elastic Container Service (Amazon ECS).
    - D. Set up Amazon ElastiCache between the web application and the PostgreSQL database.
    - E. Migrate the web application to be hosted on Amazon EC2 instances.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, C
    </details>

23. A company uses a three-tier web application to provide training to new employees. The
application is accessed for only 12 hours every day. The company is using an Amazon RDS
for MySQL DB instance to store information and wants to minimize costs. What should a
solutions architect do to meet these requirements?
    - A. Launch an Amazon EC2 instance. Create an IAM role that grants access to Amazon RDS. Attach the role to the EC2 instance. Configure a cron job to start and stop the EC2 instance on the desired schedule.
    - B. Create AWS Lambda functions to start and stop the DB instance. Create Amazon EventBridge (Amazon CloudWatch Events) scheduled rules to invoke the Lambda functions. Configure the Lambda functions as event targets for the rules.
    - C. Configure an IAM policy for AWS Systems Manager Session Manager. Create an IAM role for the policy. Update the trust relationship of the role. Set up automatic start and stop for the DB instance.
    - D. Create an Amazon ElastiCache for Redis cache cluster that gives users the ability to access the data from the cache when the  DB instance is stopped. Invalidate the cache after the DB instance is started.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

24. A company needs to retain application log files for a critical application for 10 years. The application team regularly accesses logs from the past month for troubleshooting, but logs older than 1 month are rarely accessed. The application generates more than 10 TB of logs per month. Which storage option meets these requirements MOST cost-effectively?
    - A. Store the logs in Amazon S3. Use S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.
    - B. Store the logs in Amazon S3. Use AWS Backup to move logs more than 1 month old to S3 Glacier Deep Archive.
    - C. Store the logs in Amazon CloudWatch Logs. Use Amazon S3 Lifecycle policies to move logs more than 1 month old to S3 Glacier Deep Archive.
    - D. Store the logs in Amazon CloudWatch Logs. Use AWS Backup to move logs more than 1 month old to S3 Glacier Deep Archive.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

25. A company has a highly dynamic batch processing job that uses many Amazon EC2 instances to complete it. The job is stateless in nature, can be started and stopped at any given time with no negative impact, and typically takes upwards of 60 minutes total to
complete. The company has asked a solutions architect to design a scalable and cost-effective solution that meets the requirements of the job. What should the solutions architect recommend?
    - A. Purchase EC2 Reserved Instances.
    - B. Implement EC2 Spot Instances. 
    - C. Implement EC2 On-Demand Instances.
    - D. Implement the processing on AWS Lambda.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

26. A company runs a stateless web application in production on a group of Amazon EC2 On-Demand Instances behind an Application Load Balancer. The application experiences heavy usage during an 8-hour period each business day. Application usage is moderate and steady overnight. Application usage is low during weekends. The company wants to minimize its EC2 costs without affecting the availability of the application. Which solution will meet these requirements?
    - A. Use Reserved Instances for the baseline level of usage. Use Spot instances for any additional capacity that the application needs.
    - B. Use On-Demand Instances for the baseline level of usage. Use Spot Instances for any additional capacity that the application needs.
    - C. Use Dedicated Instances for the baseline level of usage. Use On-Demand Instances for any additional capacity that the application needs.
    - D. Use Spot Instances for the entire workload.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

27. A company’s infrastructure consists of Amazon EC2 instances and an Amazon RDS DB instance in a single AWS Region. The company wants to back up its data in a separate Region. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Use Amazon Data Lifecycle Manager (Amazon DLM) to copy EC2 backups and RDS backups to the separate Region.
    - B. Create Amazon Machine Images (AMIs) of the EC2 instances. Copy the AMIs to the separate Region. Create a read replica for the RDS DB instance in the separate Region.
    - C. Use AWS Backup to copy EC2 backups and RDS backups to the separate Region.
    - D. Create Amazon Elastic Block Store (Amazon EBS) snapshots. Copy the EBS snapshots to the separate Region. Create RDS snapshots. Export the RDS snapshots to Amazon S3. Configure S3 Cross-Region Replication (CRR) to the separate Region.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

28. A company’s web application is running on Amazon EC2 instances behind an Application Load Balancer. The company recently changed its policy, which now requires the application to be accessed from one specific country only. Which configuration will meet this requirement?
    - A. Configure AWS WAF on the Application Load Balancer in a VPC.
    - B. Configure the network ACL for the subnet that contains the EC2 instances.
    - C. Configure the security group on the Application Load Balancer.
    - D. Configure the security group for the EC2 instances.
    
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

29. A solutions architect must design a solution that uses Amazon CloudFront with an Amazon S3 origin to store a static website. The company’s security policy requires that all website traffic be inspected by AWS WAF. How should the solutions architect comply with these requirements?
    - A. Configure a security group that allows Amazon CloudFront IP addresses to access Amazon S3 only. Associate AWS WAF to CloudFront.
    - B. Configure Amazon CloudFront to forward all incoming requests to AWS WAF before requesting content from the S3 origin.
    - C. Configure Amazon CloudFront and Amazon S3 to use an origin access identity (OAI) to restrict access to the S3 bucket. Enable AWS WAF on the distribution.
    - D. Configure an S3 bucket policy to accept requests coming from the AWS WAF Amazon Resource Name (ARN) only.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

30. A solutions architect needs to implement a solution to reduce a company's storage costs. All
the company's data is in the Amazon S3 Standard storage class. The company must keep
all data for at least 25 years. Data from the most recent 2 years must be highly available
and immediately retrievable. Which solution will meet these requirements?
    - A. Use S3 Intelligent-Tiering. Activate the archiving option to ensure that data is archived in S3 Glacier Deep Archive.
    - B. Set up an S3 Lifecycle policy to transition objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) immediately and to S3 Glacier Deep Archive after 2 years.
    - C. Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive immediately.
    - D. Set up an S3 Lifecycle policy to transition objects to S3 Glacier Deep Archive after 2 years.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

31. A solutions architect needs to help a company optimize the cost of running an application
on AWS. The application will use Amazon EC2 instances, AWS Fargate, and AWS
Lambda for compute within the architecture. The EC2 instances will run the data ingestion
layer of the application. EC2 usage will be sporadic and unpredictable. Workloads that run
on EC2 instances can be interrupted at any time. The application front end will run on
Fargate, and Lambda will serve the API layer. The front-end utilization and API layer
utilization will be predictable over the course of the next year. Which combination of
purchasing options will provide the MOST cost-effective solution for hosting this
application? (**Choose two.**)
    - A. Purchase a 1-year Compute Savings Plan for the front end and API layer. 
    - B. Use On-Demand Instances for the data ingestion layer
    - C. Use Spot Instances for the data ingestion layer 
    - D. Purchase 1-year All Upfront Reserved instances for the data ingestion layer.
    - E. Purchase a 1-year EC2 instance Savings Plan for the front end and API layer.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, C
    </details>

32. Organizers for a global event want to put daily reports online as static HTML pages. The
pages are expected to generate millions of views from users around the world. The files are
stored in an Amazon S3 bucket. A solutions architect has been asked to design an efficient
and effective solution. Which action should the solutions architect take to accomplish this?
    - A. Use Amazon CloudFront with the S3 bucket as its origin.
    - B. Use cross-Region replication to all Regions.
    - C. Use the geoproximity feature of Amazon Route 53.
    - D. Generate presigned URLs for the files.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

33. An entertainment company is using Amazon DynamoDB to store media metadata. The application is read intensive and experiencing delays. The company does not have staff to handle additional operational overhead and needs to improve the performance efficiency of DynamoDB without reconfiguring the application. What should a solutions architect recommend to meet this requirement? 
    - A. Use Amazon ElastiCache for Redis.
    - B. Use Amazon DynamoDB Accelerator (DAX).
    - C. Replicate data by using DynamoDB global tables.
    - D. Use Amazon ElastiCache for Memcached with Auto Discovery enabled.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

34. A security team wants to limit access to specific services or actions in all of the team’s AWS accounts. All accounts belong to a large organization in AWS Organizations. The solution must be scalable and there must be a single point where permissions can be maintained. What should a solutions architect do to accomplish this?
    - A. Create an ACL to provide access to the services or actions.
    - B. Create cross-account roles in each account to deny access to the services or actions.
    - C. Create a service control policy in the root organizational unit to deny access to the services or actions.
    - D. Create a security group to allow accounts and attach it to user groups.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

35. A gaming company hosts a browser-based application on AWS. The users of the application consume a large number of videos and images that are stored in Amazon S3. This content is the same for all users. The application has increased in popularity, and millions of users worldwide accessing these media files. The company wants to provide the files to the users while reducing the load on the origin. Which solution meets these requirements MOST cost-effectively?
    - A. Deploy an AWS Global Accelerator accelerator in front of the web servers.
    - B. Deploy an Amazon CloudFront web distribution in front of the S3 bucket. 
    - C. Deploy an Amazon ElastiCache for Redis instance in front of the web servers.
    - D. Deploy an Amazon ElastiCache for Memcached instance in front of the web servers.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

36. A company runs its ecommerce application on AWS. Every new order is published as a massage in a RabbitMQ queue that runs on an Amazon EC2 instance in a single Availability Zone. These messages are processed by a different application that runs on a separate EC2 instance. This application stores the details in a PostgreSQL database on another EC2 instance. All the EC2 instances are in the same Availability Zone. The company needs to redesign its architecture to provide the highest availability with the least operational overhead. What should a solutions architect do to meet these requirements?
    - A. Create a Multi-AZ Auto Scaling group for EC2 instances that host the RabbitMQ queue. Create another Multi-AZ Auto Scaling group for EC2 instances that host the application. Migrate the database to run on a Multi-AZ deployment of Amazon RDS for PostgreSQL.
    - B. Migrate the queue to a redundant pair (active/standby) of RabbitMQ instances on Amazon MQ. Create a Multi-AZ Auto Scaling group for EC2 instances that host the application. Migrate the database to run on a Multi-AZ deployment of Amazon RDS for PostgreSQL.
    - C. Migrate the queue to a redundant pair (active/standby) of RabbitMQ instances on Amazon MQ. Create a Multi-AZ Auto Scaling group for EC2 instances that host the application. Create another Multi-AZ Auto Scaling group for EC2 instances that host the PostgreSQL database.
    - D. Create a Multi-AZ Auto Scaling group for EC2 instances that host the RabbitMQ queue. Create another Multi-AZ Auto Scaling group for EC2 instances that host the application. Create a third Multi-AZ Auto Scaling group for EC2 instances that host the PostgreSQL database.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

37. A company hosts a website analytics application on a single Amazon EC2 On-Demand Instance. The analytics software is written in PHP and uses a MySQL database. The analytics software, the web server that provides PHP, and the database server are all hosted on the EC2 instance. The application is showing signs of performance degradation during busy times and is presenting 5xx errors. The company needs to make the application scale seamlessly. Which solution will meet these requirements MOST cost-effectively?
    - A. Migrate the database to an Amazon RDS for MySQL DB instance. Create an AMI of the web application. Use the AMI to launch a second EC2 On-Demand Instance. Use Amazon Route 53 weighted routing to distribute the load across the two EC2 instances.
    - B. Migrate the database to an Amazon Aurora MySQL DB instance. Create an AWS Lambda function to stop the EC2 instance and change the instance type. Create an Amazon CloudWatch alarm to invoke the Lambda function when CPU utilization surpasses 75%.
    - C. Migrate the database to an Amazon RDS for MySQL DB instance. Create an AMI of the web application. Use the AMI to launch a second EC2 On-Demand Instance. Use an Application Load Balancer to distribute the load to each EC2 instance.
    - D. Migrate the database to an Amazon Aurora MySQL DB instance. Create an AMI of the web application. Apply the AMI to a launch template. Create an Auto Scaling group with the launch template Configure the launch template to use a Spot Fleet. Attach an Application Load Balancer to the Auto Scaling group.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

38. A company is running a publicly accessible serverless application that uses Amazon API
Gateway and AWS Lambda. The application’s traffic recently spiked due to fraudulent
requests from botnets. Which steps should a solutions architect take to block requests from
unauthorized users? (**Choose two.**)
    - A. Create a usage plan with an API key that is shared with genuine users only.
    - B. Implement an AWS WAF rule to target malicious requests and trigger actions to filter them out.
    - C. Create an IAM role for each user attempting to access the API. A user will assume the role when making the API call.
    - D. Integrate logic within the Lambda function to ignore the requests from fraudulent IP addresses.
    - E. Convert the existing public API to a private API. Update the DNS records to redirect users to the new API endpoint.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, B
    </details>

39. A company is migrating an application from on-premises servers to Amazon EC2
instances. As part of the migration design requirements, a solutions architect must
implement infrastructure metric alarms. The company does not need to take action if CPU
utilization increases to more than 50% for a short burst of time. However, if the CPU
utilization increases to more than 50% and read IOPS on the disk are high at the same
time, the company needs to act as soon as possible. The solutions architect also must reduce
false alarms. What should the solutions architect do to meet these requirements?
    - A. Create Amazon CloudWatch dashboards to visualize the metrics and react to issues quickly.
    - B. Create Amazon CloudWatch composite alarms where possible.
    - C. Create Amazon CloudWatch Synthetics canaries to monitor the application and raise an alarm.
    - D. Create single Amazon CloudWatch metric alarms with multiple metric thresholds where possible.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

40. A company recently started using Amazon Aurora as the data store for its global
ecommerce application. When large reports are run, developers report that the ecommerce
application is performing poorly. After reviewing metrics in Amazon CloudWatch, a
solutions architect finds that the ReadIOPS and CPUUtilizalion metrics are spiking when monthly reports run. What is the MOST cost-effective solution?
    - A. Migrate the Aurora database to a larger instance class.
    - B. Increase the Provisioned IOPS on the Aurora instance.
    - C. Migrate the monthly reporting to an Aurora Replica. 
    - D. Migrate the monthly reporting to Amazon Redshift.
    
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

41. A company runs an Oracle database on premises. As part of the company’s migration to AWS, the company wants to upgrade the database to the most recent available version. The company also wants to set up disaster recovery (DR) for the database. The company needs to minimize the operational overhead for normal operations and DR setup. The company also needs to maintain access to the database's underlying operating system. Which solution will meet these requirements?
    - A. Migrate the Oracle database to an Amazon EC2 instance. Set up database replication to a different AWS Region.
    - B. Migrate the Oracle database to Amazon RDS Custom for Oracle. Create a read replica for the database in another AWS Region.
    - C. Migrate the Oracle database to Amazon RDS for Oracle. Create a standby database in another Availability Zone.
    - D. Migrate the Oracle database to Amazon RDS for Oracle. Activate Cross-Region automated backups to replicate the snapshots to another AWS Region.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

42. A company provides an API to its users that automates inquiries for tax computations based on item prices. The company experiences a larger number of inquiries during the holiday season only that cause slower response times. A solutions architect needs to design a solution that is scalable and elastic. What should the solutions architect do to accomplish this?
    - A. Design a REST API using Amazon API Gateway that accepts the item names. API Gateway passes item names to AWS Lambda for tax computations.
    - B. Create an Application Load Balancer that has two Amazon EC2 instances behind it. The EC2 instances will compute the tax on the received item names.
    - C. Design a REST API using Amazon API Gateway that connects with an API hosted on an Amazon EC2 instance. API Gateway accepts and passes the item names to the EC2 instance for tax computations.
    - D. Provide an API hosted on an Amazon EC2 instance. The EC2 instance performs the required computations when the API request is made.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

43. of the information submitted by users is sensitive. The application uses HTTPS but needs another layer of security. The sensitive information should.be protected throughout the entire application stack, and access to the information should be restricted to certain applications. Which action should the solutions architect take?
    - A. Configure CloudFront and set the Origin Protocol Policy setting to HTTPS Only for the Viewer Protocol Policy.
    - B. Configure a CloudFront signed cookie.
    - C. Configure a CloudFront field-level encryption profile.
    - D. Configure a CloudFront signed URL.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

44. A company wants to build a scalable key management infrastructure to support developers who need to encrypt data in their applications. What should a solutions architect do to reduce the operational burden?
    - A. Use an IAM policy to limit the scope of users who have access permissions to protect the encryption keys
    - B. Use AWS Key Management Service (AWS KMS) to protect the encryption keys.
    - C. Use multi-factor authentication (MFA) to protect the encryption keys.
    - D. Use AWS Certificate Manager (ACM) to create, store, and assign the encryption keys.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

45. A company is designing a cloud communications platform that is driven by APIs. The
application is hosted on Amazon EC2 instances behind a Network Load Balancer (NLB).
The company uses Amazon API Gateway to provide external users with access to the
application through APIs. The company wants to protect the platform against web exploits
like SQL injection and also wants to detect and mitigate large, sophisticated DDoS attacks.
Which combination of solutions provides the MOST protection? (**Choose two.**)
    - A. Use AWS WAF to protect the NLB.
    - B. Use Amazon GuardDuty with AWS Shield Standard
    - C. Use AWS Shield Advanced with the NLB.
    - D. Use AWS Shield Standard with Amazon API Gateway.
    - E. Use AWS WAF to protect Amazon API Gateway.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C, E
    </details>

46. A company wants to migrate its on-premises data center to AWS. According to the
company's compliance requirements, the company can use only the ap-northeast-3 Region.
Company administrators are not permitted to connect VPCs to the internet. Which
solutions will meet these requirements? (**Choose two.**)
    - A. Use AWS Organizations to configure service control policies (SCPS) that prevent VPCs from gaining internet access. Deny access to all AWS Regions except ap-northeast-3.
    - B. Use rules in AWS WAF to prevent internet access. Deny access to all AWS Regions except ap-northeast-3 in the AWS account settings.
    - C. Create an outbound rule for the network ACL in each VPC to deny all traffic from 0.0.0.0/0. Create an IAM policy for each user to prevent the use of any AWS Region other than ap-northeast-3.
    - D. Use AWS Control Tower to implement data residency guardrails to deny internet access and deny access to all AWS Regions except ap-northeast-3.
    - E. Use AWS Config to activate managed rules to detect and alert for internet gateways and to detect and alert for new resources deployed outside of apnortheast-3.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, D
    </details>

47. A company has a dynamic web application hosted on two Amazon EC2 instances. The
company has its own SSL certificate, which is on each instance to perform SSL
termination. There has been an increase in traffic recently, and the operations team
determined that SSL encryption and decryption is causing the compute capacity of the web
servers to reach their maximum limit. What should a solutions architect do to increase the
application's performance?
    - A. Import the SSL certificate into AWS Certificate Manager (ACM). Create an Application Load Balancer with an HTTPS listener that uses the SSL certificate from ACM.
    - B. Create another EC2 instance as a proxy server. Migrate the SSL certificate to the new instance and configure it to direct connections to the existing EC2 instances.
    - C. Create an Amazon S3 bucket Migrate the SSL certificate to the S3 bucket. Configure the EC2 instances to reference the bucket for SSL termination.
    - D. Create a new SSL certificate using AWS Certificate Manager (ACM). Install the ACM certificate on each instance.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

48. A solutions architect is optimizing a website for an upcoming musical event. Videos of the performances will be streamed in real time and then will be available on demand. The event is expected to attract a global online audience. Which service will improve the performance of both the real-time and on-demand streaming?
    - A. AWS Global Accelerator
    - B. Amazon CloudFront 
    - C. Amazon Route 53
    - D. Amazon S3 Transfer Acceleration

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

49. A company uses AWS Organizations to create dedicated AWS accounts for each business unit to manage each business unit's account independently upon request. The root email recipient missed a notification that was sent to the root user email address of one account. The company wants to ensure that all future notifications are not missed. Future notifications must be limited to account administrators. Which solution will meet these requirements?
    - A. Configure all AWS account root user email messages to be sent to one administrator who is responsible for monitoring alerts and forwarding those alerts to the appropriate groups.
    - B. Configure all AWS account root user email addresses as distribution lists that go to a few administrators who can respond to alerts. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.
    - C. Configure the company’s email server to forward notification email messages that are sent to the AWS account root user email address to all users in the organization.
    - D. Configure all existing AWS accounts and all newly created accounts to use the same root user email address. Configure AWS account alternate contacts in the AWS Organizations console or programmatically.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

50. A company’s website provides users with downloadable historical performance reports. The website needs a solution that will scale to meet the company’s website demands globally. The solution should be cost-effective, limit the provisioning of infrastructure resources, and provide the fastest possible response time. Which combination should a solutions architect recommend to meet these requirements?
    - A. AWS Lambda and Amazon DynamoDB
    - B. Amazon CloudFront and Amazon S3 
    - C. Amazon Route 53 with internal Application Load Balancers
    - D. Application Load Balancer with Amazon EC2 Auto Scaling

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

51. An application runs on Amazon EC2 instances across multiple Availability Zonas. The instances run in an Amazon EC2 Auto Scaling group behind an Application Load Balancer. The application performs best when the CPU utilization of the EC2 instances is at or near 40%. What should a solutions architect do to maintain the desired performance across all instances in the group?
    - A. Use a simple scaling policy to dynamically scale the Auto Scaling group.
    - B. Use a target tracking policy to dynamically scale the Auto Scaling group. 
    - C. Use scheduled scaling actions to scale up and scale down the Auto Scaling group.
    - D. Use an AWS Lambda function ta update the desired Auto Scaling group capacity.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

52. A company is developing a file-sharing application that will use an Amazon S3 bucket for storage. The company wants to serve all the files through an Amazon CloudFront distribution. The company does not want the files to be accessible through direct navigation to the S3 URL. What should a solutions architect do to meet these requirements?
    - A. Create an IAM user. Grant the user read permission to objects in the S3 bucket. Assign the user to CloudFront.
    - B. Create an origin access identity (OAI). Assign the OAI to the CloudFront distribution. Configure the S3 bucket permissions so that only the OAI has read permission.
    - C. Write individual policies for each S3 bucket to grant read permission for only CloudFront access.
    - D. Write an S3 bucket policy that assigns the CloudFront distribution ID as the Principal and assigns the target S3 bucket as the Amazon Resource Name (ARN).
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

53. A company runs its two-tier ecommerce website on AWS. The web tier consists of a load
balancer that sends traffic to Amazon EC2 instances. The database tier uses an Amazon
RDS DB instance. The EC2 instances and the RDS DB instance should not be exposed to
the public internet. The EC2 instances require internet access to complete payment
processing of orders through a third-party web service. The application must be highly
available. Which combination of configuration options will meet these requirements?
(**Choose two.**)
    - A. Configure a VPC with two public subnets, two private subnets, and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the public subnets.
    - B. Use an Auto Scaling group to launch the EC2 instances in private subnets. Deploy an RDS Multi-AZ DB instance in private  subnets.
    - C. Configure a VPC with two private subnets and two NAT gateways across two Availability Zones. Deploy an Application Load Balancer in the private subnets.
    - D. Use an Auto Scaling group to launch the EC2 instances in public subnets across two Availability Zones. Deploy an RDS Multi-AZ DB instance in private subnets.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, B
    </details>

54. A company is running an online transaction processing (OLTP) workload on AWS. This
workload uses an unencrypted Amazon RDS DB instance in a Multi-AZ deployment. Daily
database snapshots are taken from this instance. What should a solutions architect do to
ensure the database and snapshots are always encrypted moving forward?
    - A. Copy the snapshots to an Amazon S3 bucket that is encrypted using serverside encryption with AWS Key Management Service (AWS KMS) managed keys (SSE-KMS).
    - B. Copy the snapshots and enable encryption using AWS Key Management Service (AWS KMS) Restore encrypted snapshot to an existing DB instance.
    - C. Create a new encrypted Amazon Elastic Block Store (Amazon EBS) volume and copy the snapshots to it. Enable encryption on the DB instance.
    - D. Encrypt a copy of the latest DB snapshot. Replace existing DB instance by restoring the encrypted snapshot.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

55. A company is concerned about the security of its public web application due to recent web
attacks. The application uses an Application Load Balancer (ALB). A solutions architect
must reduce the risk of DDoS attacks against the application. What should the solutions
architect do to meet this requirement?
    - A. Add an Amazon Inspector agent to the ALB.
    - B. Configure Amazon Macie to prevent attacks.
    - C. Configure Amazon GuardDuty to monitor the ALB.
    - D. Enable AWS Shield Advanced to prevent attacks.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

56. A company has a small Python application that processes JSON documents and outputs the results to an on-premises SQL database. The application runs thousands of times each day. The company wants to move the application to the AWS Cloud. The company needs a highly available solution that maximizes scalability and minimizes operational overhead. Which solution will meet these requirements?
    - A. Place the JSON documents in an Amazon S3 bucket. Create an AWS Lambda function that runs the Python code to process the documents as they arrive in the S3 bucket. Store the results in an Amazon Aurora DB cluster.
    - B. Place the JSON documents in an Amazon S3 bucket. Run the Python code on multiple Amazon EC2 instances to process the documents. Store the results in an Amazon Aurora DB cluster.
    - C. Place the JSON documents in an Amazon Simple Queue Service (Amazon SQS) queue as messages. Deploy the Python code as a container on an Amazon Elastic Container Service (Amazon ECS) cluster that is configured with the Amazon EC2 launch type. Use the container to process the SQS messages. Store the results on an Amazon RDS DB instance.
    - D. Place the JSON documents in an Amazon Elastic Block Store (Amazon EBS)  volume. Use the EBS Multi-Attach feature to attach the volume to multiple Amazon EC2 instances. Run the Python code on the EC2 instances to process the documents. Store the results on an Amazon RDS DB instance.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

57. A company stores data in an Amazon Aurora PostgreSQL DB cluster. The company must
store all the data for 5 years and must delete all the data after 5 years. The company also
must indefinitely keep audit logs of actions that are performed within the database.
Currently, the company has automated backups configured for Aurora. Which
combination of steps should a solutions architect take to meet these requirements? (**Choose
two.**)
    - A. Create a lifecycle policy for the automated backups.
    - B. Use AWS Backup to take the backups and to keep the backups for 5 years.
    - C. Take a manual snapshot of the DB cluster.
    - D. Configure automated backup retention for 5 years.
    - E. Configure an Amazon CloudWatch Logs export for the DB cluster.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, E
    </details>
    
58. A company has a service that produces event data. The company wants to use AWS to process the event data as it is received. The data is written in a specific order that must be maintained throughout processing. The company wants to implement a solution that minimizes operational overhead. How should a solutions architect accomplish this?
    - A. Create an Amazon Simple Notification Service (Amazon SNS) topic to deliver notifications containing payloads to process. Configure an AWS Lambda function as a subscriber.
    - B. Create an Amazon Simple Queue Service (Amazon SQS) FIFO queue to hold messages. Set up an AWS Lambda function to process messages from the queue.
    - C. Create an Amazon Simple Notification Service (Amazon SNS) topic to deliver notifications containing payloads to process. Configure an Amazon Simple Queue Service (Amazon SQS) queue as a subscriber.
    - D. Create an Amazon Simple Queue Service (Amazon SQS) standard queue to hold messages. Set up an AWS Lambda function to process messages from the queue independently.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

59. A company sells ringtones created from clips of popular songs. The files containing the ringtones are stored in Amazon S3 Standard and are at least 128 KB in size. The company has millions of files, but downloads are infrequent for ringtones older than 90 days. The company needs to save money on storage while keeping the most accessed files readily available for its users. Which action should the company take to meet these requirements MOST cost-effectively?
    - A. Move the files to S3 Intelligent-Tiering and configure it to move objects to a less expensive storage tier after 90 days.
    - B. Configure S3 Standard-Infrequent Access (S3 Standard-IA) storage for the initial storage tier of the objects.
    - C. Configure S3 inventory to manage objects and move them to S3 Standard-Infrequent Access (S3 Standard-1A) after 90 days.
    - D. Implement an S3 Lifecycle policy that moves the objects from S3 Standard to S3 Standard-Infrequent Access (S3 Standard-1A) after 90 days.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

60. A gaming company is designing a highly available architecture. The application runs on a modified Linux kernel and supports only UDP-based traffic. The company needs the front-end tier to provide the best possible user experience. That tier must have low latency, route traffic to the nearest edge location, and provide static IP addresses for entry into the application endpoints. What should a solutions architect do to meet these requirements?
    - A. Configure AWS Global Accelerator to forward requests to a Network Load Balancer. Use Amazon EC2 instances for the application in an EC2 Auto Scaling group.
    - B. Configure Amazon CloudFront to forward requests to a Network Load Balancer. Use AWS Lambda for the application in an AWS Application Auto Scaling group.
    - C. Configure Amazon Route 53 to forward requests to an Application Load Balancer. Use AWS Lambda for the application in AWS Application Auto Scaling.
    - D. Configure Amazon API Gateway to forward requests to an Application Load Balancer. Use Amazon EC2 instances for the application in an EC2 Auto Scaling group.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

Please feel free to comment below if any information is inaccurate or if any answers need correction.


