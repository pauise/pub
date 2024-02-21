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
      Correct answer: B
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

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>


Please feel free to comment below if any information is inaccurate or if any answers need correction.


