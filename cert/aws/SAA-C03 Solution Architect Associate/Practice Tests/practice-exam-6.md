# Practice Exam 6

Click on the **Answer** button for the correct answer and its explanation.

If this practice exam has been helpful to you please share it with others and react to this below.

---

1. A solutions architect must secure a VPC network that hosts Amazon EC2 instances. The EC2 instances contain highly sensitive data and run in a private subnet. According to company policy, the EC2 instances that run in the VPC can access only approved third-party software repositories on the internet for software product updates that use the third party’s URL. Other internet traffic must be blocked. Which solution meets these requirements? 
    - A. Configure an Application Load Balancer (ALB) in front of the EC2 instances. Direct all outbound traffic to the ALB. Use a URL-based rule listener in the ALB’s target group for outbound access to the internet.
    - B. Implement strict inbound security group rules. Configure an outbound rule that allows traffic only to the authorized software repositories on the internet by specifying the URLs.
    - C. Set up an AWS WAF web ACL. Create a custom set of rules that filter traffic requests based on source and destination IP address range sets.
    - D. Update the route table for the private subnet to route the outbound traffic to an AWS Network Firewall firewall. Configure domain list rule groups.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

2. A company that primarily runs its application servers on premises has decided to migrate to AWS. The company wants to minimize its need to scale its Internet Small Computer Systems Interface (iSCSI) storage on premises. The company wants only its recently accessed data to remain stored locally. Which AWS solution should the company use to meet these requirements?
    - A. Amazon S3 File Gateway
    - B. AWS Storage Gateway Volume Gateway cached volumes
    - C. AWS Storage Gateway Volume Gateway stored volumes
    - D. AWS Storage Gateway Tape Gateway

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

3. A company is moving its data management application to AWS. The company wants to transition to an event-driven architecture. The architecture needs to be more distributed and to use serverless concepts while performing the different aspects of the workflow. The company also wants to minimize operational overhead. Which solution will meet these requirements?
   - A. Build out the workflow in AWS Step Functions. Use Step Functions to create a state machine. Use the state machine to invoke AWS Lambda functions to process the workflow steps.
   - B. Build out the workflow in AWS Step Functions. Deploy the application on Amazon EC2 instances. Use Step Functions to invoke the workflow steps on the EC2 instances.
   - C. Build out the workflow in AWS Glue. Use AWS Glue to invoke AWS Lambda functions to process the workflow steps.
   - D. Build out the workflow in Amazon EventBridge. Use EventBridge to invoke AWS Lambda functions on a schedule to process the workflow steps.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

4. A company has a custom application with embedded credentials that retrieves information from an Amazon RDS MySQL DB instance. Management says the application must be made more secure with the least amount of programming effort. What should a solutions architect do to meet these requirements? 
    - A. Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Systems Manager Parameter Store. Configure the application to load the database credentials from Parameter Store. Set up a credentials rotation schedule for the application user in the RDS for MySQL database using Parameter Store.
    - B. Use AWS Key Management Service (AWS KMS) to create keys. Configure the application to load the database credentials from AWS KMS. Enable automatic key rotation.
    - C. Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Secrets Manager. Configure the application to load the database credentials from Secrets Manager. Set up a credentials rotation schedule for the application user in the RDS for MySQL database using Secrets Manager.
    - D. Create credentials on the RDS for MySQL database for the application user and store the credentials in AWS Secrets Manager. Configure the application to load the database credentials from Secrets Manager. Create an AWS Lambda function that rotates the credentials in Secret Manager.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

5. A hospital needs to store patient records in an Amazon S3 bucket. The hospital’s compliance team must ensure that all protected health information (PHI) is encrypted in transit and at rest. The compliance team must administer the encryption key for data at rest. Which solution will meet these requirements? 
    - A. Use the aws:SecureTransport condition on S3 bucket policies to allow only encrypted connections over HTTPS (TLS). Configure default encryption for each S3 bucket to use server-side encryption with AWS KMS keys (SSE-KMS). Assign the compliance team to manage the KMS keys.
    - B. Use the aws:SecureTransport condition on S3 bucket policies to allow only encrypted connections over HTTPS (TLS). Use Amazon Macie to protect the sensitive data that is stored in Amazon S3. Assign the compliance team to manage Macie.
    - C. Create a public SSL/TLS certificate in AWS Certificate Manager (ACM). Associate the certificate with Amazon S3. Configure default encryption for each S3 bucket to use server-side encryption with AWS KMS keys (SSE-KMS). Assign the compliance team to manage the KMS keys.
    - D. Use the aws:SecureTransport condition on S3 bucket policies to allow only encrypted connections over HTTPS (TLS). Configure default encryption for each S3 bucket to use server-side encryption with S3 managed encryption keys (SSE-S3). Assign the compliance team to manage the SSE-S3 keys.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

6. A company is building a mobile app on AWS. The company wants to expand its reach to millions of users. The company needs to build a platform so that authorized users can watch the company’s content on their mobile devices. What should a solutions architect recommend to meet these requirements? 
    - A. Set up AWS Client VPN between the mobile app and the AWS environment to stream content.
    - B. Use Amazon CloudFront. Provide signed URLs to stream content.
    - C. Set up IPsec VPN between the mobile app and the AWS environment to stream content.
    - D. Publish content to a public Amazon S3 bucket. Use AWS Key Management Service (AWS KMS) keys to stream content.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

7. A company wants to implement a disaster recovery plan for its primary on-premises file storage volume. The file storage volume is mounted from an Internet Small Computer Systems Interface (iSCSI) device on a local storage server. The file storage volume holds hundreds of terabytes (TB) of data. The company wants to ensure that end users retain immediate access to all file types from the on-premises systems without experiencing latency. Which solution will meet these requirements with the LEAST amount of change to the company's existing infrastructure? 
    - A. Provision an Amazon S3 File Gateway as a virtual machine (VM) that is hosted on premises. Set the local cache to 10 TB. Modify existing applications to access the files through the NFS protocol. To recover from a disaster, provision an Amazon EC2 instance and mount the S3 bucket that contains the files.
    - B. Provision an AWS Storage Gateway Volume Gateway stored volume with the same amount of disk space as the existing file storage volume. Mount the Volume Gateway stored volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.
    - C. Provision an AWS Storage Gateway tape gateway. Use a data backup solution to back up all existing data to a virtual tape library. Configure the data backup solution to run nightly after the initial backup is complete. To recover from a disaster, provision an Amazon EC2 instance and restore the data to an Amazon Elastic Block Store (Amazon EBS) volume from the volumes in the virtual tape library.
    - D. Provision an AWS Storage Gateway Volume Gateway cached volume. Set the local cache to 10 TB. Mount the Volume Gateway cached volume to the existing file server by using iSCSI, and copy all files to the storage volume. Configure scheduled snapshots of the storage volume. To recover from a disaster, restore a snapshot to an Amazon Elastic Block Store (Amazon EBS) volume and attach the EBS volume to an Amazon EC2 instance.


    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

8. A company is launching a new application deployed on an Amazon Elastic Container Service (Amazon ECS) cluster and is using the Fargate launch type for ECS tasks. The company is monitoring CPU and memory usage because it is expecting high traffic to the application upon its launch. However, the company wants to reduce costs when utilization decreases. What should a solutions architect recommend?
    - A. Use AWS Application Auto Scaling with target tracking policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.
    - B. Use Amazon EC2 Auto Scaling to scale at certain periods based on previous traffic patterns.
    - C. Use an AWS Lambda function to scale Amazon ECS based on metric breaches that trigger an Amazon CloudWatch alarm.
    - D. Use Amazon EC2 Auto Scaling with simple scaling policies to scale when ECS metric breaches trigger an Amazon CloudWatch alarm.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

9. A company stores its data objects in Amazon S3 Standard storage. A solutions architect has found that 75% of the data is rarely accessed after 30 days. The company needs all the data to remain immediately accessible with the same high availability and resiliency, but the company wants to minimize storage costs. Which storage solution will meet these requirements? 
    - A. Move the data objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 30 days.
    - B. Move the data objects to S3 One Zone-Infrequent Access (S3 One Zone-IA) immediately.
    - C. Move the data objects to S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days.
    - D. Move the data objects to S3 Glacier Deep Archive after 30 days.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

10. A company sells datasets to customers who do research in artificial intelligence and machine learning (AI/ML). The datasets are large, formatted files that are stored in an Amazon S3 bucket in the us-east-1 Region. The company hosts a web application that the customers use to purchase access to a given dataset. The web application is deployed on multiple Amazon EC2 instances behind an Application Load Balancer. After a purchase is made, customers receive an S3 signed URL that allows access to the files. The customers are distributed across North America and Europe. The company wants to reduce the cost that is associated with data transfers and wants to maintain or improve performance. What should a solutions architect do to meet these requirements? 
    - A. Deploy an Amazon CloudFront distribution with the existing S3 bucket as the origin. Direct customer requests to the CloudFront URL. Switch to CloudFront signed URLs for access control.
    - B. Set up a second S3 bucket in the eu-central-1 Region with S3 Cross-Region Replication between the buckets. Direct customer requests to the closest Region. Continue to use S3 signed URLs for access control.
    - C. Modify the web application to enable streaming of the datasets to end users. Configure the web application to read the data from the existing S3 bucket. Implement access control directly in the application.
    - D. Configure S3 Transfer Acceleration on the existing S3 bucket. Direct customer requests to the S3 Transfer Acceleration endpoint. Continue to use S3 signed URLs for access control.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

11. A company wants to give a customer the ability to use on-premises Microsoft Active Directory to download files that are stored in Amazon S3. The customer’s application uses an SFTP client to download the files. Which solution will meet these requirements with the LEAST operational overhead and no changes to the customer’s application? 
    - A. Set up AWS DataSync to synchronize between the on-premises location and the S3 location by using AWS IAM Identity Center (AWS Single Sign-On).
    - B. Set up AWS Database Migration Service (AWS DMS) to synchronize the on-premises client with Amazon S3. Configure integrated Active Directory authentication.
    - C. Set up AWS Transfer Family with SFTP for Amazon S3. Configure integrated Active Directory authentication.
    - D. Set up a Windows Amazon EC2 instance with SFTP to connect the on-premises client with Amazon S3. Integrate AWS Identity and Access Management (IAM).

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

12. A solutions architect must create a disaster recovery (DR) plan for a high-volume software as a service (SaaS) platform. All data for the platform is stored in an Amazon Aurora MySQL DB cluster. The DR plan must replicate data to a secondary AWS Region. Which solution will meet these requirements MOST cost-effectively?
    - A. Set up an Aurora global database for the DB cluster. When setup is complete, remove the DB instance from the secondary Region.
    - B. Use MySQL binary log replication to an Aurora cluster in the secondary Region. Provision one DB instance for the Aurora cluster in the secondary Region.
    - C. Set up an Aurora global database for the DB cluster. Specify a minimum of one DB instance in the secondary Region.
    - D. Use AWS Database Migration Service (AWS DMS) to continuously replicate data to an Aurora cluster in the secondary Region. Remove the DB instance from the secondary Region.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

13. A transaction processing company has weekly scripted batch jobs that run on Amazon EC2 instances. The EC2 instances are in an Auto Scaling group. The number of transactions can vary, but the baseline CPU utilization that is noted on each run is at least 60%. The company needs to provision the capacity 30 minutes before the jobs run. Currently, engineers complete this task by manually modifying the Auto Scaling group parameters. The company does not have the resources to analyze the required capacity trends for the
Auto Scaling group counts. The company needs an automated way to modify the Auto Scaling group’s desired capacity. Which solution will meet these requirements with the LEAST operational overhead? 
    - A. Create a dynamic scaling policy for the Auto Scaling group. Configure the policy to scale based on the CPU utilization metric. Set the target value for the metric to 60%.
    - B. Create a scheduled scaling policy for the Auto Scaling group. Set the appropriate desired capacity, minimum capacity, and maximum capacity. Set the recurrence to weekly. Set the start time to 30 minutes before the batch jobs run.
    - C. Create a predictive scaling policy for the Auto Scaling group. Configure the policy to scale based on forecast. Set the scaling metric to CPU utilization. Set the target value for the metric to 60%. In the policy, set the instances to pre-launch 30 minutes before the jobs run.
    - D. Create an Amazon EventBridge event to invoke an AWS Lambda function when the CPU utilization metric value for the Auto Scaling group reaches 60%. Configure the Lambda function to increase the Auto Scaling group’s desired capacity and maximum capacity by 20%.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

14. A company is hosting a three-tier ecommerce application in the AWS Cloud. The company hosts the website on Amazon S3 and integrates the website with an API that handles sales requests. The company hosts the API on three Amazon EC2 instances behind an Application Load Balancer (ALB). The API consists of static and dynamic front-end content along with backend workers that process sales requests asynchronously. The company is expecting a significant and sudden increase in the number of sales requests during events for the launch of new products. What should a solutions architect recommend to ensure that all the requests are processed successfully? 
    - A. Add an Amazon CloudFront distribution for the static content. Place the EC2 instances in an Auto Scaling group to launch new instances based on network traffic.
    - B. Add an Amazon CloudFront distribution for the dynamic content. Add an Amazon ElastiCache instance in front of the ALB to reduce traffic for the API to handle.
    - C. Add an Amazon CloudFront distribution for the static content. Add an Amazon Simple Queue Service (Amazon SQS) queue to receive requests from the website for later processing by the EC2 instances.
    - D. Add an Amazon CloudFront distribution for the dynamic content. Increase the number of EC2 instances to handle the increase in traffic.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

15. A company’s application runs on Amazon EC2 instances behind an Application Load Balancer (ALB). The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. On the first day of every month at midnight, the application becomes much slower when the month-end financial calculation batch runs. This causes the CPU utilization of the EC2 instances to immediately peak to 100%, which disrupts the application. What should a solutions architect recommend to ensure the application is able to handle the workload and avoid downtime?
    - A. Configure an Amazon CloudFront distribution in front of the ALB.
    - B. Configure an EC2 Auto Scaling simple scaling policy based on CPU utilization.
    - C. Configure Amazon ElastiCache to remove some of the workload from the EC2 instances.
    - D. Configure an EC2 Auto Scaling scheduled scaling policy based on the monthly schedule.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

16. A company hosts a three-tier web application on Amazon EC2 instances in a single Availability Zone. The web application uses a self-managed MySQL database that is hosted on an EC2 instance to store data in an Amazon Elastic Block Store (Amazon EBS) volume. The MySQL database currently uses a 1 TB Provisioned IOPS SSD (io2) EBS volume. The company expects traffic of 1,000 IOPS for both reads and writes at peak traffic. The company wants to minimize any disruptions, stabilize performance, and reduce costs while retaining the capacity for double the IOPS. The company wants to move the database tier to a fully managed solution that is highly available and fault tolerant. Which solution will meet these requirements MOST cost-effectively?
    - A. Use two large EC2 instances to host the database in active-passive mode.
    - B. Use Amazon S3 Intelligent-Tiering access tiers.
    - C. Use a Multi-AZ deployment of an Amazon RDS for MySQL DB instance with an io2 Block Express EBS volume.
    - D. Use a Multi-AZ deployment of an Amazon RDS for MySQL DB instance with a General Purpose SSD (gp2) EBS volume.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

17. A company wants to run an in-memory database for a latency-sensitive application that runs on Amazon EC2 instances. The application processes more than 100,000 transactions each minute and requires high network throughput. A solutions architect needs to provide a cost-effective network design that minimizes data transfer charges. Which solution meets these requirements?
    - A. Launch all EC2 instances in the same Availability Zone within the same AWS Region. Specify a placement group with cluster strategy when launching EC2 instances.
    - B. Deploy an Auto Scaling group to launch EC2 instances in different Availability Zones based on a network utilization target.
    - C. Launch all EC2 instances in different Availability Zones within the same AWS Region. Specify a placement group with partition strategy when launching EC2 instances.
    - D. Deploy an Auto Scaling group with a step scaling policy to launch EC2 instances in different Availability Zones.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

18. A social media company runs its application on Amazon EC2 instances behind an Application Load Balancer (ALB). The ALB is the origin for an Amazon CloudFront distribution. The application has more than a billion images stored in an Amazon S3 bucket and processes thousands of images each second. The company wants to resize the images dynamically and serve appropriate formats to clients. Which solution will meet these requirements with the LEAST operational overhead? 
    - A. Create a CloudFront origin request policy. Use the policy to automatically resize images and to serve the appropriate format based on the User-Agent HTTP header in the request.
    - B. Create a CloudFront response headers policy. Use the policy to automatically resize images and to serve the appropriate format based on the User-Agent HTTP header in the request.
    - C. Use a Lambda@Edge function with an external image management library. Associate the Lambda@Edge function with the CloudFront behaviors that serve the images.
    - D. Install an external image management library on an EC2 instance. Use the image management library to process the images.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

19. A company has multiple AWS accounts that use consolidated billing. The company runs
several active high performance Amazon RDS for Oracle On-Demand DB instances for 90
days. The company’s finance team has access to AWS Trusted Advisor in the consolidated
billing account and all other AWS accounts. The finance team needs to use the appropriate
AWS account to access the Trusted Advisor check recommendations for RDS. The finance
team must review the appropriate Trusted Advisor check to reduce RDS costs. Which
combination of steps should the finance team take to meet these requirements? (**Choose two.**)
    - A. Review the Trusted Advisor check for Amazon RDS Reserved Instance Optimization.
    - B. Use the Trusted Advisor recommendations from the consolidated billing account to see all RDS instance checks at the same time.
    - C. Use the Trusted Advisor recommendations from the account where the RDS instances are running.
    - D. Review the Trusted Advisor check for Amazon Redshift Reserved Node Optimization.
    - E. Review the Trusted Advisor check for Amazon RDS Idle DB Instances.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, E
    </details>

20. A company recently migrated its entire IT environment to the AWS Cloud. The company
discovers that users are provisioning oversized Amazon EC2 instances and modifying
security group rules without using the appropriate change control process. A solutions
architect must devise a strategy to track and audit these inventory and configuration
changes. Which actions should the solutions architect take to meet these requirements?
(**Choose two.**)
    - A. Enable AWS Trusted Advisor and reference the security dashboard.
    - B. Use data lifecycle policies for the Amazon EC2 instances.
    - C. Enable AWS Config and create rules for auditing and compliance purposes.
    - D. Enable AWS CloudTrail and use it for auditing.
    - E. Restore previous resource configurations with an AWS CloudFormation template.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C, D
    </details>

21. A company has deployed a web application on AWS. The company hosts the backend
database on Amazon RDS for MySQL with a primary DB instance and five read replicas to
support scaling needs. The read replicas must lag no more than 1 second behind the
primary DB instance. The database routinely runs scheduled stored procedures. As traffic
on the website increases, the replicas experience additional lag during periods of peak load.
A solutions architect must reduce the replication lag as much as possible. The solutions
architect must minimize changes to the application code and must minimize ongoing operational overhead. Which solution will meet these requirements? 
    - A. Migrate the database to a MySQL database that runs on Amazon EC2 instances. Choose large, compute optimized EC2 instances for all replica nodes. Maintain the stored procedures on the EC2 instances.
    - B. Migrate the database to Amazon Aurora MySQL. Replace the read replicas with Aurora Replicas, and configure Aurora Auto Scaling. Replace the stored procedures with Aurora MySQL native functions.
    - C. Migrate the database to Amazon DynamoDB. Provision a large number of read capacity units (RCUs) to support the required throughput, and configure on-demand capacity scaling. Replace the stored procedures with DynamoDB streams.
    - D. Deploy an Amazon ElastiCache for Redis cluster in front of the database. Modify the application to check the cache before the application queries the database. Replace the stored procedures with AWS Lambda functions.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

22. A company is designing a shared storage solution for a gaming application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed. Which AWS solution meets these requirements?
    - A. Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.
    - B. Create an Amazon S3 bucket. Assign an IAM role to the application to grant access to the S3 bucket. Mount the S3 bucket to the application server.
    - C. Create an AWS DataSync task that shares the data as a mountable file system. Mount the file system to the application server.
    - D. Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the file system. 

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

23. A solutions architect is designing a company’s disaster recovery (DR) architecture. The company has a MySQL database that runs on an Amazon EC2 instance in a private subnet with scheduled backup. The DR design needs to include multiple AWS Regions. Which solution will meet these requirements with the LEAST operational overhead? 
    - A. Migrate the MySQL database to multiple EC2 instances. Configure a standby EC2 instance in the DR Region. Turn on replication.
    - B. Migrate the MySQL database to Amazon RDS. Use a Multi-AZ deployment. Turn on read replication for the primary DB instance in the different Availability Zones.
    - C. Store the scheduled backup of the MySQL database in an Amazon S3 bucket that is configured for S3 Cross-Region Replication (CRR). Use the data backup to restore the database in the DR Region.
    - D. Migrate the MySQL database to an Amazon Aurora global database. Host the primary DB cluster in the primary Region. Host the secondary DB cluster in the DR Region.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

24. What should a solutions architect do to ensure that all objects uploaded to an Amazon S3 bucket are encrypted? 
    - A. Update the bucket policy to deny if the PutObject does not have an aws:SecureTransport header set to true.
    - B. Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set.
    - C. Update the bucket policy to deny if the PutObject does not have an x-amz-server-side-encryption header set.
    - D. Update the bucket policy to deny if the PutObject does not have an s3:x-amz-acl header set to private.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

25. A company has an application that is running on Amazon EC2 instances. A solutions architect has standardized the company on a particular instance family and various instance sizes based on the current needs of the company. The company wants to maximize cost savings for the application over the next 3 years. The company needs to be able to change the instance family and sizes in the next 6 months based on application popularity and usage. Which solution will meet these requirements MOST cost-effectively? 
    - A. Zonal Reserved Instances
    - B. Standard Reserved Instances
    - C. EC2 Instance Savings Plan
    - D. Compute Savings Plan

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

26. A company wants to create a mobile app that allows users to stream slow-motion video clips on their mobile devices. Currently, the app captures video clips and uploads the video clips in raw format into an Amazon S3 bucket. The app retrieves these video clips directly from the S3 bucket. However, the videos are large in their raw format. Users are experiencing issues with buffering and playback on mobile devices. The company wants to implement solutions to maximize the performance and scalability of the app while minimizing operational overhead. Which combination of solutions will meet these requirements? (**Choose two.**) 
    - A. Use Amazon Elastic Transcoder to convert the video files to more appropriate formats.
    - B. Use AWS DataSync to replicate the video files across AW'S Regions in other S3 buckets.
    - C. Deploy an Auto Scaling group of Amazon EC2 instances to convert the video files to more appropriate formats.
    - D. Deploy an Auto Sealing group of Amazon EC2 instances in Local Zones for content delivery and caching.
    - E. Deploy Amazon CloudFront for content delivery and caching.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

27. A company is migrating an old application to AWS. The application runs a batch job every hour and is CPU intensive. The batch job takes 15 minutes on average with an on-premises server. The server has 64 virtual CPU (vCPU) and 512 GiB of memory. Which solution will run the batch job within 15 minutes with the LEAST operational overhead? 
    - A. Use Amazon Elastic Container Service (Amazon ECS) with AWS Fargate.
    - B. Use AWS Lambda with functional scaling.
    - C. Use AWS Batch on Amazon EC2. 
    - D. Use Amazon Lightsail with AWS Auto Scaling.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

28. A company has an Amazon S3 data lake that is governed by AWS Lake Formation. The company wants to create a visualization in Amazon QuickSight by joining the data in the data lake with operational data that is stored in an Amazon Aurora MySQL database. The company wants to enforce column-level authorization so that the company’s marketing team can access only a subset of columns in the database. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Use AWS Glue Elastic Views to create a materialized view for the database in Amazon S3. Create an S3 bucket policy to enforce column-level access control for the QuickSight users. Use Amazon S3 as the data source in QuickSight.
    - B. Use Amazon EMR to ingest the data directly from the database to the QuickSight SPICE engine. Include only the required columns.
    - C. Use a Lake Formation blueprint to ingest the data from the database to the S3 data lake. Use Lake Formation to enforce column-level access control for the QuickSight users. Use Amazon Athena as the data source in QuickSight. 
    - D. Use AWS Glue Studio to ingest the data from the database to the S3 data lake. Attach an IAM policy to the QuickSight users to enforce column-level access control. Use Amazon S3 as the data source in QuickSight.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

29. A company hosts a multi-tier web application that uses an Amazon Aurora MySQL DB cluster for storage. The application tier is hosted on Amazon EC2 instances. The company’s IT security guidelines mandate that the database credentials be encrypted and rotated every 14 days. What should a solutions architect do to meet this requirement with the LEAST operational effort? 
    - A. Store a file that contains the credentials in an AWS Key Management Service (AWS KMS) encrypted Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system in all EC2 instances of the application tier. Restrict the access to the file on the file system so that the application can read the file and that only super users can modify the file. Implement an AWS Lambda function that rotates the key in Aurora every 14 days and writes new credentials into the file.
    - B. Create a new AWS Key Management Service (AWS KMS) encryption key. Use AWS Secrets Manager to create a new secret that uses the KMS key with the appropriate credentials. Associate the secret with the Aurora DB cluster. Configure a custom rotation period of 14 days.
    - C. Create two parameters in AWS Systems Manager Parameter Store: one for the user name as a string parameter and one that uses the SecureString type for the password. Select AWS Key Management Service (AWS KMS) encryption for the password parameter, and load these parameters in the application tier. Implement an AWS Lambda function that rotates the password every 14 days.
    - D. Store a file that contains the credentials in an AWS Key Management Service (AWS KMS) encrypted Amazon S3 bucket that the application uses to load the credentials. Download the file to the application regularly to ensure that the correct credentials are used. Implement an AWS Lambda function that rotates the Aurora credentials every 14 days and uploads these credentials to the file
in the S3 bucket. 

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

30. A gaming company is moving its public scoreboard from a data center to the AWS Cloud.
The company uses Amazon EC2 Windows Server instances behind an Application Load
Balancer to host its dynamic application. The company needs a highly available storage
solution for the application. The application consists of static files and dynamic server-side
code. Which combination of steps should a solutions architect take to meet these
requirements? (**Choose two**.)
    - A. Store the server-side code on a General Purpose SSD (gp2) Amazon Elastic Block Store (Amazon EBS) volume. Mount the EBS volume on each EC2 instance to share the files.
    - B. Store the static files on Amazon S3. Use Amazon ElastiCache to cache objects at the edge.
    - C. Store the server-side code on Amazon Elastic File System (Amazon EFS). Mount the EFS volume on each EC2 instance to share the files.
    - D. Store the server-side code on Amazon FSx for Windows File Server. Mount the FSx for Windows File Server volume on each EC2 instance to share the files.
    - E. Store the static files on Amazon S3. Use Amazon CloudFront to cache objects at the edge.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D, E
    </details>

31. A company uses an Amazon EC2 instance to run a script to poll for and process messages in an Amazon Simple Queue Service (Amazon SQS) queue. The company wants to reduce operational costs while maintaining its ability to process a growing number of messages that are added to the queue. What should a solutions architect recommend to meet these requirements? 
    - A. Use AWS Systems Manager Run Command to run the script on demand.
    - B. Migrate the script on the EC2 instance to an AWS Lambda function with the appropriate runtime. 
    - C. Increase the size of the EC2 instance to process messages faster.
    - D. Use Amazon EventBridge to turn off the EC2 instance when the instance is underutilized.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

32. A company has a Java application that uses Amazon Simple Queue Service (Amazon SQS) to parse messages. The application cannot parse messages that are larger than 256 KB in size. The company wants to implement a solution to give the application the ability to parse messages as large as 50 MB. Which solution will meet these requirements with the FEWEST changes to the code?
    - A. Use Amazon EventBridge to post large messages from the application instead of Amazon SQS.
    - B. Store messages that are larger than 256 KB in Amazon Elastic File System (Amazon EFS). Configure Amazon SQS to reference this location in the messages.
    - C. Use the Amazon SQS Extended Client Library for Java to host messages that are larger than 256 KB in Amazon S3.
    - D. Change the limit in Amazon SQS to handle messages that are larger than 256 KB.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

33. A company has an application that runs on several Amazon EC2 instances. Each EC2 instance has multiple Amazon Elastic Block Store (Amazon EBS) data volumes attached to it. The application’s EC2 instance configuration and data need to be backed up nightly. The application also needs to be recoverable in a different AWS Region. Which solution will meet these requirements in the MOST operationally efficient way?
    - A. Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EC2 instances as resources.
    - B. Write an AWS Lambda function that schedules nightly snapshots of the application’s EBS volumes and copies the snapshots to a different Region.
    - C. Create a backup plan by using AWS Backup to perform nightly backups. Copy the backups to another Region. Add the application’s EBS volumes as resources.
    - D. Write an AWS Lambda function that schedules nightly snapshots of the application's EBS volumes and copies the snapshots to a different Availability Zone.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

34. A company must migrate 20 TB of data from a data center to the AWS Cloud within 30
days. The company’s network bandwidth is limited to 15 Mbps and cannot exceed 70%
utilization. What should a solutions architect do to meet these requirements?
    - A. Use AWS DataSync.
    - B. Use a secure VPN connection.
    - C. Use AWS Snowball.
    - D. Use Amazon S3 Transfer Acceleration.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

35. An image hosting company uploads its large assets to Amazon S3 Standard buckets. The
company uses multipart upload in parallel by using S3 APIs and overwrites if the same
object is uploaded again. For the first 30 days after upload, the objects will be accessed
frequently. The objects will be used less frequently after 30 days, but the access patterns
for each object will be inconsistent. The company must optimize its S3 storage costs while
maintaining high availability and resiliency of stored assets. Which combination of actions
should a solutions architect recommend to meet these requirements? (**Choose two.**)
    - A. Configure an S3 Lifecycle policy to clean up incomplete multipart uploads.
    - B. Move assets to S3 Intelligent-Tiering after 30 days.
    - C. Move assets to S3 One Zone-Infrequent Access (S3 One Zone-IA) after 30 days.
    - D. Move assets to S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days.
    - E. Configure an S3 Lifecycle policy to clean up expired object delete markers.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, B
    </details>

36. A company is hosting a web application from an Amazon S3 bucket. The application uses
Amazon Cognito as an identity provider to authenticate users and return a JSON Web
Token (JWT) that provides access to protected resources that are stored in another S3
bucket. Upon deployment of the application, users report errors and are unable to access
the protected content. A solutions architect must resolve this issue by providing proper
permissions so that users can access the protected content. Which solution meets these
requirements?
    - A. Update the S3 ACL to allow the application to access the protected content.
    - B. Update the Amazon Cognito identity pool to assume the proper IAM role for access to the protected content.
    - C. Redeploy the application to Amazon S3 to prevent eventually consistent reads in the S3 bucket from affecting the ability of users to access the protected content.
    - D. Update the Amazon Cognito pool to use custom attribute mappings within the identity pool and grant users the proper permissions to access the protected content.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

37. A company needs to provide its employees with secure access to confidential and sensitive files. The company wants to ensure that the files can be accessed only by authorized users. The files must be downloaded securely to the employees’ devices. The files are stored in an on-premises Windows file server. However, due to an increase in remote usage, the file server is running out of capacity.  Which solution will meet these requirements? 
    - A. Migrate the files to Amazon S3, and create a private VPC endpoint. Create a signed URL to allow download.
    - B. Migrate the file server to an Amazon EC2 instance in a public subnet. Configure the security group to limit inbound traffic to the employees’ IP addresses.
    - C. Migrate the files to Amazon S3, and create a public VPC endpoint. Allow employees to sign on with AWS IAM Identity Center (AWS Single Sign-On).
    - D. Migrate the files to an Amazon FSx for Windows File Server file system. Integrate the Amazon FSx file system with the on-premises Active Directory. Configure AWS Client VPN.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

38. A company wants to restrict access to the content of one of its main web applications and to protect the content by using authorization techniques available on AWS. The company wants to implement a serverless architecture and an authentication solution for fewer than 100 users. The solution needs to integrate with the main web application and serve web content globally. The solution must also scale as the company's user base grows while providing the lowest login latency possible. Which solution will meet these requirements MOST cost-effectively?
    - A. Use Amazon Cognito for authentication. Use AWS Lambda for authorization. Use Amazon S3 Transfer Acceleration to serve the web application globally.
    - B. Use Amazon Cognito for authentication. Use Lambda@Edge for authorization. Use Amazon CloudFront to serve the web application globally.
    - C. Use AWS Directory Service for Microsoft Active Directory for authentication. Use AWS Lambda for authorization. Use an Application Load Balancer to serve the web application globally.
    - D. Use AWS Directory Service for Microsoft Active Directory for authentication. Use Lambda@Edge for authorization. Use AWS Elastic Beanstalk to serve the web application globally.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

39. A company has an aging network-attached storage (NAS) array in its data center. The NAS array presents SMB shares and NFS shares to client workstations. The company does not want to purchase a new NAS array. The company also does not want to incur the cost of renewing the NAS array’s support contract. Some of the data is accessed frequently, but much of the data is inactive. A solutions architect needs to implement a solution that migrates the data to Amazon S3, uses S3 Lifecycle policies, and maintains the same look and feel for the client workstations. The solutions architect has identified AWS Storage Gateway as part of the solution. Which type of storage gateway should the solutions architect provision to meet these requirements? 
    - A. Amazon S3 File Gateway 
    - B. Volume Gateway
    - C. Tape Gateway
    - D. Amazon FSx File Gateway

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

40. A university research laboratory needs to migrate 30 TB of data from an on-premises Windows file server to Amazon FSx for Windows File Server. The laboratory has a 1 Gbps network link that many other departments in the university share. The laboratory wants to implement a data migration service that will maximize the performance of the data transfer. However, the laboratory needs to be able to control the amount of bandwidth that the service uses to minimize the impact on other departments. The data migration must take place within the next 5 days. Which AWS solution will meet these requirements? 
    - A. AWS Snowcone
    - B. AWS DataSync 
    - C. Amazon FSx File Gateway
    - D. AWS Transfer Family

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

41. A company stores confidential data in an Amazon Aurora PostgreSQL database in the ap-southeast-3 Region. The database is encrypted with an AWS Key Management Service (AWS KMS) customer managed key. The company was recently acquired and must securely share a backup of the database with the acquiring company’s AWS account in ap-southeast-3. What should a solutions architect do to meet these requirements? 
    - A. Create a database snapshot that uses a different AWS managed KMS key. Add the acquiring company’s AWS account to the KMS key alias. Share the snapshot with the acquiring company's AWS account.
    - B. Create a database snapshot. Add the acquiring company’s AWS account to the KMS key policy. Share the snapshot with the acquiring company’s AWS account.
    - C. Create a database snapshot. Copy the snapshot to a new unencrypted snapshot. Share the new snapshot with the acquiring company’s AWS account.
    - D. Create a database snapshot. Download the database snapshot. Upload the database snapshot to an Amazon S3 bucket. Update the S3 bucket policy to allow access from the acquiring company’s AWS account.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

42. A company is planning to store data on Amazon RDS DB instances. The company must encrypt the data at rest. What should a solutions architect do to meet this requirement?
    - A. Create a key in AWS Key Management Service (AWS KMS). Enable encryption for the DB instances. 
    - B. Generate a certificate in AWS Identity and Access Management (IAM). Enable SSL/TLS on the DB instances by using the certificate.
    - C. Generate a certificate in AWS Certificate Manager (ACM). Enable SSL/TLS on the DB instances by using the certificate.
    - D. Create an encryption key. Store the key in AWS Secrets Manager. Use the key to encrypt the DB instances.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

43. A company is designing the network for an online multi-player game. The game uses the UDP networking protocol and will be deployed in eight AWS Regions. The network architecture needs to minimize latency and packet loss to give end users a high-quality gaming experience. Which solution will meet these requirements? 
    - A. Set up a VPC peering mesh between each Region. Turn on UDP for each VPC.
    - B. Setup a transit gateway in each Region. Create inter-Region peering attachments between each transit gateway.
    - C. Set up Amazon CloudFront with UDP turned on. Configure an origin in each Region.
    - D. Set up AWS Global Accelerator with UDP listeners and endpoint groups in each Region.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

44. A media company hosts its website on AWS. The website application’s architecture includes a fleet of Amazon EC2 instances behind an Application Load Balancer (ALB) and a database that is hosted on Amazon Aurora. The company’s cybersecurity team reports that the application is vulnerable to SQL injection. How should the company resolve this issue? 
    - A. Set up Amazon Inspector to block all SQL injection attempts automatically.
    - B. Create an ALB listener rule to reply to SQL injections with a fixed response.
    - C. Subscribe to AWS Shield Advanced to block all SQL injection attempts automatically.
    - D. Use AWS WAF in front of the ALB. Associate the appropriate web ACLs with AWS WAF.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

45. company has an on-premises MySQL database used by the global sales team with infrequent access patterns. The sales team requires the database to have minimal downtime. A database administrator wants to migrate this database to AWS without selecting a particular instance type in anticipation of more users in the future. Which service should a solutions architect recommend? 
    - A. Amazon RDS for MySQL
    - B. Amazon Redshift Spectrum
    - C. Amazon Aurora Serverless for MySQL 
    - D. Amazon Aurora MySQL

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

46. A company hosts a serverless application on AWS. The application uses Amazon API Gateway, AWS Lambda, and an Amazon RDS for PostgreSQL database. The company notices an increase in application errors that result from database connection timeouts during times of peak traffic or unpredictable traffic. The company needs a solution that reduces the application failures with the least amount of change to the code. What should a solutions architect do to meet these requirements?
    - A. Migrate the database to Amazon DynamoDB with on-demand scaling.
    - B. Resize the RDS DB instance class to accept more connections.
    - C. Enable RDS Proxy on the RDS DB instance. 
    - D. Reduce the Lambda concurrency rate.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

47. A company uses a legacy application to produce data in CSV format. The legacy application stores the output data in Amazon S3. The company is deploying a new commercial off-the-shelf (COTS) application that can perform complex SQL queries to analyze data that is stored in Amazon Redshift and Amazon S3 only. However, the COTS application cannot process the .csv files that the legacy application produces. The company cannot update the legacy application to produce data in another format. The company needs to implement a solution so that the COTS application can use the data that the legacy application produces. Which solution will meet these requirements with the LEAST operational overhead? 
    - A. Use Amazon EventBridge to launch an Amazon EMR cluster on a weekly schedule. Configure the EMR cluster to perform an extract, transform, and load (ETL) job to process the .csv files and store the processed data in an Amazon Redshift table.
    - B. Create an AWS Glue extract, transform, and load (ETL) job that runs on a schedule. Configure the ETL job to process the .csv files and store the processed data in Amazon Redshift.
    - C. Develop a Python script that runs on Amazon EC2 instances to convert the .csv files to .sql files. Invoke the Python script on a cron schedule to store the output files in Amazon S3.
    - D. Create an AWS Lambda function and an Amazon DynamoDB table. Use an S3 event to invoke the Lambda function. Configure the Lambda function to perform an extract, transform, and load (ETL) job to process the .csv files and store the processed data in the DynamoDB table.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

48. A company is using AWS to design a web application that will process insurance quotes. Users will request quotes from the application. Quotes must be separated by quote type, must be responded to within 24 hours, and must not get lost. The solution must maximize operational efficiency and must minimize maintenance. Which solution meets these requirements? 
    - A. Create multiple Amazon Kinesis data streams based on the quote type. Configure the web application to send messages to the proper data stream. Configure each backend group of application servers to use the Kinesis Client Library (KCL) to pool messages from its own data stream.
    - B. Create multiple Amazon Kinesis Data Firehose delivery streams based on the quote type to deliver data streams to an Amazon OpenSearch Service cluster. Configure the application to send messages to the proper delivery stream. Configure each backend group of application servers to search for the messages from OpenSearch Service and process them accordingly.
    - C. Create a single Amazon Simple Notification Service (Amazon SNS) topic. Subscribe Amazon Simple Queue Service (Amazon SQS) queues to the SNS topic. Configure SNS message filtering to publish messages to the proper SQS queue based on the quote type. Configure each backend application server to use its own SQS queue.
    - D. Create an AWS Lambda function and an Amazon Simple Notification Service (Amazon SNS) topic for each quote type. Subscribe the Lambda function to its associated SNS topic. Configure the application to publish requests for quotes to the appropriate SNS topic.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

49. A company is using a fleet of Amazon EC2 instances to ingest data from on-premises data sources. The data is in JSON format and ingestion rates can be as high as 1 MB/s. When an EC2 instance is rebooted, the data in-flight is lost. The company’s data science team wants to query ingested data in near-real time. Which solution provides near-real-time data querying that is scalable with minimal data loss? 
    - A. Publish data to Amazon Kinesis Data Firehose with Amazon Redshift as the destination. Use Amazon Redshift to query the data.
    - B. Store ingested data in an Amazon Elastic Block Store (Amazon EBS) volume. Publish data to Amazon ElastiCache for Redis. Subscribe to the Redis channel to query the data.
    - C. Store ingested data in an EC2 instance store. Publish data to Amazon Kinesis Data Firehose with Amazon S3 as the destination. Use Amazon Athena to query the data.
    - D. Publish data to Amazon Kinesis Data Streams, Use Kinesis Data Analytics to query the data.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

50. A company recently created a disaster recovery site in a different AWS Region. The company needs to transfer large amounts of data back and forth between NFS file systems in the two Regions on a periodic basis. Which solution will meet these requirements with the LEAST operational overhead? 
    - A. Use AWS Database Migration Service (AWS DMS).
    - B. Use AWS Snowball devices.
    - C. Set up an SFTP server on Amazon EC2.
    - D. Use AWS DataSync.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

51. 

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


