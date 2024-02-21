# Practice Exam 5

Click on the **Answer** button for the correct answer and its explanation.

If this practice exam has been helpful to you please share it with others and react to this below.

---

1. A medical research lab produces data that is related to a new study. The lab wants to make the data available with minimum latency to clinics across the country for their on-premises, file-based applications. The data files are stored in an Amazon S3 bucket that has read-only permissions for each clinic. What should a solutions architect recommend to meet these requirements? 
    - A. Migrate the files to each clinic’s on-premises applications by using AWS DataSync for processing.
    - B. Attach an Amazon Elastic File System (Amazon EFS) file system to each clinic’s on-premises servers.
    - C. Deploy an AWS Storage Gateway volume gateway as a virtual machine (VM) on premises at each clinic.
    - D. Deploy an AWS Storage Gateway file gateway as a virtual machine (VM) on premises at each clinic

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

2. An Amazon EC2 instance is located in a private subnet in a new VPC. This subnet does not have outbound internet access, but the EC2 instance needs the ability to download monthly security updates from an outside vendor. What should a solutions architect do to meet these requirements? 
    - A. Create an internet gateway, and attach it to the VPC. Create a NAT instance, and place it in the same subnet where the EC2 instance is located. Configure the private subnet route table to use the internet gateway as the default route.
    - B. Create a NAT gateway, and place it in a public subnet. Configure the private subnet route table to use the NAT gateway as the default route.
    - C. Create an internet gateway, and attach it to the VPC. Configure the private subnet route table to use the internet gateway as the default route.
    - D. Create a NAT instance, and place it in the same subnet where the EC2 instance is located. Configure the private subnet route table to use the NAT instance as the default route.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

3. A company is launching an application on AWS. The application uses an Application Load Balancer (ALB) to direct traffic to at least two Amazon EC2 instances in a single target group. The instances are in an Auto Scaling group for each environment. The company requires a development environment and a production environment. The production environment will have periods of high traffic. Which solution will configure the development environment MOST cost-effectively? 
    - A. Reduce the size of the EC2 instances in both environments.
    - B. Reconfigure the target group in the development environment to have only one EC2 instance as a target.
    - C. Reduce the maximum number of EC2 instances in the development environment’s Auto Scaling group. 
    - D. Change the ALB balancing algorithm to least outstanding requests.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

4. A company is implementing new data retention policies for all databases that run on Amazon RDS DB instances. The company must retain daily backups for a minimum period of 2 years. The backups must be consistent and restorable. Which solution should a solutions architect recommend to meet these requirements? 
    - A. Configure an AWS Database Migration Service (AWS DMS) replication task. Deploy a replication instance, and configure a change data capture (CDC) task to stream database changes to Amazon S3 as the target. Configure S3 Lifecycle policies to delete the snapshots after 2 years.
    - B. Configure a backup window for the RDS DB instances for daily snapshots. Assign a snapshot retention policy of 2 years to each RDS DB instance. Use Amazon Data Lifecycle Manager (Amazon DLM) to schedule snapshot deletions.
    - C. Create a backup vault in AWS Backup to retain RDS backups. Create a new backup plan with a daily schedule and an expiration period of 2 years after creation. Assign the RDS DB instances to the backup plan.
    - D. Configure database transaction logs to be automatically backed up to Amazon CloudWatch Logs with an expiration period of 2 years

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

5. A company has an application that places hundreds of .csv files into an Amazon S3 bucket every hour. The files are 1 GB in size. Each time a file is uploaded, the company needs to convert the file to Apache Parquet format and place the output file into an S3 bucket. Which solution will meet these requirements with the LEAST operational overhead? 
    - A. Create an Apache Spark job to read the .csv files, convert the files to Parquet format, and place the output files in an S3 bucket. Create an AWS Lambda function for each S3 PUT event to invoke the Spark job.
    - B. Create an AWS Lambda function to download the .csv files, convert the files to Parquet format, and place the output files in an S3 bucket. Invoke the Lambda function for each S3 PUT event.
    - C. Create an AWS Glue extract, transform, and load (ETL) job to convert the .csv files to Parquet format and place the output files into an S3 bucket. Create an AWS Lambda function for each S3 PUT event to invoke the ETL job.
    - D. Create an AWS Glue table and an AWS Glue crawler for the S3 bucket where the application places the .csv files. Schedule an AWS Lambda function to periodically use Amazon Athena to query the AWS Glue table, convert the query results into Parquet format, and place the output files into an S3 bucket.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

6. An ecommerce company has noticed performance degradation of its Amazon RDS based web application. The performance degradation is attributed to an increase in the number of read-only SQL queries triggered by business analysts. A solutions architect needs to solve the problem with minimal changes to the existing web application. What should the solutions architect recommend? 
    - A. Copy the data into an Amazon Redshift cluster and have the business analysts run their queries.
    - B. Create a read replica of the primary database and have the business analysts run their queries.
    - C. Load the data into Amazon ElastiCache and have the business analysts run their queries.
    - D. Export the data to Amazon DynamoDB and have the business analysts run their queries.
  
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

7. A company runs a web application on Amazon EC2 instances in multiple Availability Zones. The EC2 instances are in private subnets. A solutions architect implements an internet-facing Application Load Balancer (ALB) and specifies the EC2 instances as the target group. However, the internet traffic is not reaching the EC2 instances. How should the solutions architect reconfigure the architecture to resolve this issue?
    - A. Replace the ALB with a Network Load Balancer. Configure a NAT gateway in a public subnet to allow internet traffic.
    - B. Create public subnets in each Availability Zone. Associate the public subnets with the ALB. Update the route tables for the public subnets with a route to the private subnets.
    - C. Move the EC2 instances to public subnets. Add a rule to the EC2 instances’ security groups to allow outbound traffic to 0.0.0.0/0.
    - D. Update the route tables for the EC2 instances’ subnets to send 0.0.0.0/0 traffic through the internet gateway route. Add a rule to the EC2 instances’ security groups to allow outbound traffic to 0.0.0.0/0.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

8. A company has an ecommerce checkout workflow that writes an order to a database and calls a service to process the payment. Users are experiencing timeouts during the checkout process. When users resubmit the checkout form, multiple unique orders are created for the same desired transaction. How should a solutions architect refactor this workflow to prevent the creation of multiple orders?
    - A. Store the order in the database. Send a message that includes the order number to an Amazon Simple Queue Service (Amazon SQS) FIFO queue. Set the payment service to retrieve the message and process the order. Delete the message from the queue.
    - B. Configure the web application to send an order message to Amazon Kinesis Data Firehose. Set the payment service to retrieve the message from Kinesis Data Firehose and process the order.
    - C. Create a rule in AWS CloudTrail to invoke an AWS Lambda function based on the logged application path request. Use Lambda to query the database, call the payment service, and pass in the order information.
    - D. Store the order in the database. Send a message that includes the order number to Amazon Simple Notification Service (Amazon SNS). Set the payment service to poll Amazon SNS, retrieve the message, and process the order.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

9. A solutions architect needs to design a system to store client case files. The files are core company assets and are important. The number of files will grow over time. The files must be simultaneously accessible from multiple application servers that run on Amazon EC2 instances. The solution must have built-in redundancy. Which solution meets these requirements?
    - A. AWS Backup
    - B. Amazon S3 Glacier Deep Archive
    - C. Amazon Elastic File System (Amazon EFS)
    - D. Amazon Elastic Block Store (Amazon EBS)

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

10. A company is implementing a shared storage solution for a media application that is hosted in the AWS Cloud. The company needs the ability to use SMB clients to access data. The solution must be fully managed. Which AWS solution meets these requirements? 
    - A. Create an AWS Storage Gateway tape gateway. Configure tapes to use Amazon S3. Connect the application server to the tape gateway.
    - B. Create an Amazon EC2 Windows instance. Install and configure a Windows file share role on the instance. Connect the application server to the file share.
    - C. Create an Amazon FSx for Windows File Server file system. Attach the file system to the origin server. Connect the application server to the file system. 
    - D. Create an AWS Storage Gateway volume gateway. Create a file share that uses the required client protocol. Connect the application server to the file share.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

11. A development team has launched a new application that is hosted on Amazon EC2 instances inside a development VPC. A solutions architect needs to create a new VPC in the same account. The new VPC will be peered with the development VPC. The VPC CIDR block for the development VPC is 192.168.0.0/24. The solutions architect needs to create a CIDR block for the new VPC. The CIDR block must be valid for a VPC peering connection to the development VPC. What is the SMALLEST CIDR block that meets these requirements? 
    - A. 192.168.1.0/32
    - B. 10.0.1.0/32
    - C. 10.0.1.0/24 
    - D. 192.168.0.0/24

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

12. A research laboratory needs to process approximately 8 TB of data. The laboratory requires sub-millisecond latencies and a minimum throughput of 6 GBps for the storage subsystem. Hundreds of Amazon EC2 instances that run Amazon Linux will distribute and process the data. Which solution will meet the performance requirements? 
    - A. Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent SSD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.
    - B. Create an Amazon FSx for NetApp ONTAP file system. Sat each volume’ tiering policy to ALL. Import the raw data into the file system. Mount the fila system on the EC2 instances.
    - C. Create an Amazon FSx for NetApp ONTAP file system. Set each volume’s tiering policy to NONE. Import the raw data into the file system. Mount the file system on the EC2 instances.
    - D. Create an Amazon S3 bucket to store the raw data. Create an Amazon FSx for Lustre file system that uses persistent HDD storage. Select the option to import data from and export data to Amazon S3. Mount the file system on the EC2 instances.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

13. A company is building a solution that will report Amazon EC2 Auto Scaling events across all the applications in an AWS account. The company needs to use a serverless solution to store the EC2 Auto Scaling status data in Amazon S3. The company then will use the data in Amazon S3 to provide near-real-time updates in a dashboard. The solution must not affect the speed of EC2 instance launches. How should the company move the data to Amazon S3 to meet these requirements? 
    - A. Use a bootstrap script during the launch of an EC2 instance to install Amazon Kinesis Agent. Configure Kinesis Agent to collect the EC2 Auto Scaling status data and send the data to Amazon Kinesis Data Firehose. Store the data in Amazon S3.
    - B. Create an Amazon EventBridge rule to invoke an AWS Lambda function on a schedule. Configure the Lambda function to send the EC2 Auto Scaling status data directly to Amazon S3.
    - C. Launch an Amazon EMR cluster to collect the EC2 Auto Scaling status data and send the data to Amazon Kinesis Data Firehose. Store the data in Amazon S3.
    - D. Use an Amazon CloudWatch metric stream to send the EC2 Auto Scaling status data to Amazon Kinesis Data Firehose. Store the data in Amazon S3.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

14. A solutions architect has created two IAM policies: Policy1 and Policy2. Both policies are
attached to an IAM group. A cloud engineer is added as an IAM user to the IAM group.
Which action will the cloud engineer be able to perform?
    - A. Deleting Amazon EC2 instances
    - B. Deleting logs from Amazon CloudWatch Logs
    - C. Deleting directories
    - D. Deleting IAM users

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

15. A company is building an application that consists of several microservices. The company
has decided to use container technologies to deploy its software on AWS. The company
needs a solution that minimizes the amount of ongoing effort for maintenance and scaling.
The company cannot manage additional infrastructure. Which combination of actions
should a solutions architect take to meet these requirements? (**Choose two.**)
    - A. Deploy the Kubernetes control plane on Amazon EC2 instances that span multiple Availability Zones.
    - B. Deploy an Amazon Elastic Container Service (Amazon ECS) service with a Fargate launch type. Specify a desired task number level of greater than or equal to 2.
    - C. Deploy an Amazon Elastic Container Service (Amazon ECS) cluster.
    - D. Deploy an Amazon Elastic Container Service (Amazon ECS) service with an Amazon EC2 launch type. Specify a desired task number level of greater than or equal to 2.
    - E. Deploy Kubernetes worker nodes on Amazon EC2 instances that span multiple Availability Zones. Create a deployment that specifies two or more replicas for each microservice.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, C
    </details>

16. A company has a web application hosted over 10 Amazon EC2 instances with traffic
directed by Amazon Route 53. The company occasionally experiences a timeout error when
attempting to browse the application. The networking team finds that some DNS queries
return IP addresses of unhealthy instances, resulting in the timeout error. What should a
solutions architect implement to overcome these timeout errors?
    - A. Create an Amazon CloudFront distribution with EC2 instances as its origin. Associate a health check with the EC2 instances.
    - B. Create a Route 53 simple routing policy record for each EC2 instance. Associate a health check with each record.
    - C. Create a Route 53 failover routing policy record for each EC2 instance. Associate a health check with each record.
    - D. Create an Application Load Balancer (ALB) with a health check in front of the EC2 instances. Route to the ALB from Route 53.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

17. A company has a multi-tier application deployed on several Amazon EC2 instances in an
Auto Scaling group. An Amazon RDS for Oracle instance is the application’ s data layer
that uses Oracle-specific PL/SQL functions. Traffic to the application has been steadily
increasing. This is causing the EC2 instances to become overloaded and the RDS instance
to run out of storage. The Auto Scaling group does not have any scaling metrics and defines
the minimum healthy instance count only. The company predicts that traffic will continue
to increase at a steady but unpredictable rate before leveling off. What should a solutions
architect do to ensure the system can automatically scale for the increased traffic? (**Choose two.**)
    - A. Configure the Auto Scaling group to use the average CPU as the scaling metric.
    - B. Configure the Auto Scaling group to use the average free memory as the scaling metric.
    - C. Configure an alarm on the RDS for Oracle instance for low free storage space.
    - D. Configure storage Auto Scaling on the RDS for Oracle instance.
    - E. Migrate the database to Amazon Aurora to use Auto Scaling storage.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, D
    </details>

18. A company runs a fleet of web servers using an Amazon RDS for PostgreSQL DB instance. After a routine compliance check, the company sets a standard that requires a recovery point objective (RPO) of less than 1 second for all its production databases. Which solution meets these requirements? 
    - A. Configure the DB instance in one Availability Zone, and create multiple read replicas in a separate Availability Zone.
    - B. Enable a Multi-AZ deployment for the DB instance. 
    - C. Enable auto scaling for the DB instance in one Availability Zone.
    - D. Configure the DB instance in one Availability Zone, and configure AWS Database Migration Service (AWS DMS) change data capture (CDC) tasks.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

19. An application that is hosted on Amazon EC2 instances needs to access an Amazon S3 bucket. Traffic must not traverse the internet. How should a solutions architect configure access to meet these requirements? 
    - A. Create a private hosted zone by using Amazon Route 53.
    - B. Establish an AWS Site-to-Site VPN connection between the VPC and the S3 bucket.
    - C. Set up a gateway VPC endpoint for Amazon S3 in the VPC.
    - D. Configure the EC2 instances to use a NAT gateway to access the S3 bucket.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

20. A company hosts a web application on multiple Amazon EC2 instances. The EC2 instances are in an Auto Scaling group that scales in response to user demand. The company wants to optimize cost savings without making a long-term commitment. Which EC2 instance purchasing option should a solutions architect recommend to meet these requirements?
    - A. Dedicated Instances only
    - B. A mix of On-Demand Instances and Spot Instances
    - C. A mix of On-Demand Instances and Reserved Instances
    - D. On-Demand Instances only

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

21. A company provides an online service for posting video content and transcoding it for use by any mobile platform. The application architecture uses Amazon Elastic File System (Amazon EFS) Standard to collect and store the videos so that multiple Amazon EC2 Linux instances can access the video content for processing. As the popularity of the service has grown over time, the storage costs have become too expensive. Which storage solution is MOST cost-effective? 
    - A. Use AWS Storage Gateway for volumes to store and process the video content.
    - B. Use Amazon S3 for storing the video content. Move the files temporarily over to an Amazon Elastic Block Store (Amazon EBS) volume attached to the server for processing.
    - C. Use AWS Storage Gateway for files to store and process the video content.
    - D. Use Amazon EFS for storing the video content. Once processing is complete, transfer the files to Amazon Elastic Block Store (Amazon EBS).

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

22. A solutions architect needs to design a highly available application consisting of web, application, and database tiers. HTTPS content delivery should be as close to the edge as possible, with the least delivery time. Which solution meets these requirements and is MOST secure? 
    - A. Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.
    - B. Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in public subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
    - C. Configure a public Application Load Balancer (ALB) with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the public ALB as the origin.
    - D. Configure a public Application Load Balancer with multiple redundant Amazon EC2 instances in private subnets. Configure Amazon CloudFront to deliver HTTPS content using the EC2 instances as the origin.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

23. A company’s security team requests that network traffic be captured in VPC Flow Logs.
The logs will be frequently accessed for 90 days and then accessed intermittently. What
should a solutions architect do to meet these requirements when configuring the logs?
    - A. Use Amazon CloudWatch as the target. Set the CloudWatch log group with an expiration of 90 days
    - B. Use Amazon Kinesis as the target. Configure the Kinesis stream to always retain the logs for 90 days.
    - C. Use AWS CloudTrail as the target. Configure CloudTrail to save to an Amazon S3 bucket, and enable S3 Intelligent-Tiering.
    - D. Use Amazon S3 as the target. Enable an S3 Lifecycle policy to transition the logs to S3 Standard-Infrequent Access (S3 Standard-IA) after 90 days.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

24. A media company uses Amazon CloudFront for its publicly available streaming video
content. The company wants to secure the video content that is hosted in Amazon S3 by
controlling who has access. Some of the company’s users are using a custom HTTP client
that does not support cookies. Some of the company’s users are unable to change the
hardcoded URLs that they are using for access. Which services or methods will meet these
requirements with the LEAST impact to the users? (**Choose two.**)
    - A. Signed URLs
    - B. Signed cookies
    - C. JSON Web Token (JWT)
    - D. AWS AppSync
    - E. AWS Secrets Manager

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, B
    </details>

25. A company is migrating a Linux-based web server group to AWS. The web servers must
access files in a shared file store for some content. The company must not make any
changes to the application. What should a solutions architect do to meet these
requirements?
    - A. Configure an Amazon CloudFront distribution with an Amazon S3 bucket as the origin.
    - B. Create an Amazon Elastic File System (Amazon EFS) file system. Mount the EFS file system on all web servers.ç
    - C. Create an Amazon S3 Standard bucket with access to the web servers.
    - D. Configure a General Purpose SSD (gp3) Amazon Elastic Block Store (Amazon
EBS) volume. Mount the EBS volume to all web servers.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

26. A company is using Amazon CloudFront with its website. The company has enabled logging on the CloudFront distribution, and logs are saved in one of the company’s Amazon S3 buckets. The company needs to perform advanced analyses on the logs and build visualizations. What should a solutions architect do to meet these requirements? 
    - A. Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.
    - B. Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with Amazon QuickSight.
    - C. Use standard SQL queries in Amazon DynamoDB to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue.
    - D. Use standard SQL queries in Amazon Athena to analyze the CloudFront logs in the S3 bucket. Visualize the results with AWS Glue. 

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

27. A solutions architect observes that a nightly batch processing job is automatically scaled up for 1 hour before the desired Amazon EC2 capacity is reached. The peak capacity is the ‘same every night and the batch jobs always start at 1 AM. The solutions architect needs to find a cost-effective solution that will allow for the desired EC2 capacity to be reached quickly and allow the Auto Scaling group to scale down after the batch jobs are complete. What should the solutions architect do to meet these requirements? 
    - A. Increase the minimum capacity for the Auto Scaling group.
    - B. Increase the maximum capacity for the Auto Scaling group.
    - C. Configure scheduled scaling to scale up to the desired compute level.
    - D. Change the scaling policy to add more EC2 instances during each scaling operation.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

28. A company’s compliance team needs to move its file shares to AWS. The shares run on a Windows Server SMB file share. A self-managed on-premises Active Directory controls access to the files and folders. The company wants to use Amazon FSx for Windows File Server as part of the solution. The company must ensure that the on-premises Active Directory groups restrict access to the FSx for Windows File Server SMB compliance shares, folders, and files after the move to AWS. The company has created an FSx for Windows File Server file system. Which solution will meet these requirements? 
    - A. Assign a tag with a Restrict tag key and a Compliance tag value. Map the Active Directory groups to IAM groups to restrict access.
    - B. Join the file system to the Active Directory to restrict access.
    - C. Create an IAM service-linked role that is linked directly to FSx for Windows File Server to restrict access.
    - D. Create an Active Directory Connector to connect to the Active Directory. Map the Active Directory groups to IAM groups to restrict access.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

29. A company has an AWS Lambda function that needs read access to an Amazon S3 bucket that is located in the same AWS account. Which solution will meet these requirements in the MOST secure manner? 
    - A. Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to the S3 bucket.
    - B. Apply an IAM role to the Lambda function. Apply an IAM policy to the role to grant read access to all S3 buckets in the account.
    - C. Embed an access key and a secret key in the Lambda function’s code to grant the required IAM permissions for read access to the S3 bucket.
    - D. Apply an S3 bucket policy that grants read access to the S3 bucket.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

30. A rapidly growing ecommerce company is running its workloads in a single AWS Region. A solutions architect must create a disaster recovery (DR) strategy that includes a different AWS Region. The company wants its database to be up to date in the DR Region with the least possible latency. The remaining infrastructure in the DR Region needs to run at reduced capacity and must be able to scale up if necessary. Which solution will meet these requirements with the LOWEST recovery time objective (RTO)? 
    - A. Use an Amazon Aurora global database with a warm standby deployment.
    - B. Use an Amazon RDS Multi-AZ DB instance with a warm standby deployment.
    - C. Use an Amazon RDS Multi-AZ DB instance with a pilot light deployment.
    - D. Use an Amazon Aurora global database with a pilot light deployment.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

31. A company has a static website that is hosted on Amazon CloudFront in front of Amazon S3. The static website uses a database backend. The company notices that the website does not reflect updates that have been made in the website’s Git repository. The company checks the continuous integration and continuous delivery (CI/CD) pipeline between the Git repository and Amazon S3. The company verifies that the webhooks are configured properly and that the CI/CD pipeline is sending messages that indicate successful deployments. A solutions architect needs to implement a solution that displays the updates on the website. Which solution will meet these requirements? 
    - A. Invalidate the CloudFront cache.
    - B. Add Amazon ElastiCache for Redis or Memcached to the database layer of the web application.
    - C. Add an Application Load Balancer.
    - D. Use AWS Certificate Manager (ACM) to validate the website’s SSL certificate.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

32. A company serves a dynamic website from a fleet of Amazon EC2 instances behind an Application Load Balancer (ALB). The website needs to support multiple languages to serve customers around the world. The website’s architecture is running in the us-west-1 Region and is exhibiting high request latency for users that are located in other parts of the world. The website needs to serve requests quickly and efficiently regardless of a user’s location. However, the company does not want to recreate the existing architecture across multiple Regions. What should a solutions architect do to meet these requirements?
    - A. Replace the existing architecture with a website that is served from an Amazon S3 bucket. Configure an Amazon CloudFront distribution with the S3 bucket as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.
    - B. Create an Amazon API Gateway API that is integrated with the ALB. Configure the API to use the HTTP integration type. Set up an API Gateway stage to enable the API cache based on the Accept-Language request header.
    - C. Configure an Amazon CloudFront distribution with the ALB as the origin. Set the cache behavior settings to cache based on the Accept-Language request header.
    - D. Launch an EC2 instance in each additional Region and configure NGINX to act as a cache server for that Region. Put all the EC2 instances and the ALB behind an Amazon Route 53 record set with a geolocation routing policy.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

33. A company hosts its web application on AWS using seven Amazon EC2 instances. The company requires that the IP addresses of all healthy EC2 instances be returned in response to DNS queries. Which policy should be used to meet this requirement? 
    - A. Geolocation routing policy
    - B. Simple routing policy
    - C. Latency routing policy
    - D. Multivalue routing policy

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

34. A company is using a centralized AWS account to store log data in various Amazon S3 buckets. A solutions architect needs to ensure that the data is encrypted at rest before the data is uploaded to the S3 buckets. The data also must be encrypted in transit. Which solution meets these requirements? 
    - A. Use server-side encryption to encrypt the data that is being uploaded to the S3 buckets.
    - B. Enable the security option to encrypt the S3 buckets through the use of a default AWS Key Management Service (AWS KMS) key.
    - C. Create bucket policies that require the use of server-side encryption with S3 managed encryption keys (SSE-S3) for S3 uploads.
    - D. Use client-side encryption to encrypt the data that is being uploaded to the S3 buckets.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

35. As part of budget planning, management wants a report of AWS billed items listed by user. The data will be used to create department budgets. A solutions architect needs to determine the most efficient way to obtain this report information. Which solution meets these requirements? 
    - A. Access the bill details from the billing dashboard and download the bill.
    - B. Modify a cost budget in AWS Budgets to alert with Amazon Simple Email Service (Amazon SES).
    - C. Create a report in Cost Explorer and download the report. 
    - D. Run a query with Amazon Athena to generate the report.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

36. A company plans to use Amazon ElastiCache for its multi-tier web application. A solutions architect creates a Cache VPC for the ElastiCache cluster and an App VPC for the application’s Amazon EC2 instances. Both VPCs are in the us-east-1 Region. The solutions architect must implement a solution to provide the application’s EC2 instances with access to the ElastiCache cluster. Which solution will meet these requirements MOST cost-effectively? 
    - A. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the peering connection’s security group to allow inbound connection from the application’s security group.
    - B. Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an inbound rule for the Transit VPC’s security group to allow inbound connection from the application’s security group.
    - C. Create a peering connection between the VPCs. Add a route table entry for the peering connection in both VPCs. Configure an inbound rule for the ElastiCache cluster’s security group to allow inbound connection from the application’s security group.
    - D. Create a Transit VPC. Update the VPC route tables in the Cache VPC and the App VPC to route traffic through the Transit VPC. Configure an inbound rule for the ElastiCache cluster's security group to allow inbound connection from the application’s security group.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

37. A company has an on-premises volume backup solution that has reached its end of life. The company wants to use AWS as part of a new backup solution and wants to maintain local access to all the data while it is backed up on AWS. The company wants to ensure that the data backed up on AWS is automatically and securely transferred. Which solution meets these requirements? 
    - A. Use AWS Storage Gateway and configure a stored volume gateway. Run the Storage Gateway software appliance on premises and map the gateway storage volumes to on-premises storage. Mount the gateway storage volumes to provide local access to the data.
    - B. Use AWS Storage Gateway and configure a cached volume gateway. Run the Storage Gateway software appliance on premises and configure a percentage of data to cache locally. Mount the gateway storage volumes to provide local access to the data.
    - C. Use AWS Snowball Edge to migrate data out of the on-premises solution to Amazon S3. Use the Snowball Edge file interface to provide on-premises systems with local access to the data.
    - D. Use AWS Snowball to migrate data out of the on-premises solution to Amazon S3. Configure on-premises systems to mount the Snowball S3 endpoint to provide local access to the data.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

38. A solutions architect is implementing a document review application using an Amazon S3 bucket for storage. The solution must prevent accidental deletion of the documents and ensure that all versions of the documents are available. Users must be able to download,
modify, and upload documents. Which combination of actions should be taken to meet
these requirements? (**Choose two.**)
    - A. Enable versioning on the bucket.
    - B. Attach an IAM policy to the bucket.
    - C. Enable MFA Delete on the bucket.
    - D. Enable a read-only bucket ACL.
    - E. Encrypt the bucket using AWS KMS.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, C
    </details>

39. A company wants to migrate a Windows-based application from on premises to the AWS
Cloud. The application has three tiers: an application tier, a business tier, and a database
tier with Microsoft SQL Server. The company wants to use specific features of SQL Server
such as native backups and Data Quality Services. The company also needs to share files
for processing between the tiers. How should a solutions architect design the architecture to
meet these requirements?
    - A. Host all three tiers on Amazon EC2 instances. Use Amazon FSx for Windows File Server for file sharing between the tiers.
    - B. Host all three tiers on Amazon EC2 instances. Use Amazon FSx File Gateway for file sharing between the tiers.
    - C. Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use Amazon Elastic File System (Amazon EFS) for file sharing between the tiers.
    - D. Host the application tier and the business tier on Amazon EC2 instances. Host the database tier on Amazon RDS. Use a Provisioned IOPS SSD (io2) Amazon Elastic Block Store (Amazon EBS) volume for file sharing between the tiers.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

40. A company runs an application on Amazon EC2 instances. The company needs to implement a disaster recovery (DR) solution for the application. The DR solution needs to have a recovery time objective (RTO) of less than 4 hours. The DR solution also needs to use the fewest possible AWS resources during normal operations. Which solution will meet these requirements in the MOST operationally efficient way? 
    - A. Launch EC2 instances in a secondary Availability Zone. Keep the EC2 instances in the secondary Availability Zone active at all times.
    - B. Launch EC2 instances in a secondary AWS Region. Keep the EC2 instances in the secondary Region active at all times.
    - C. Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS Lambda and custom scripts.
    - D. Create Amazon Machine Images (AMIs) to back up the EC2 instances. Copy the AMIs to a secondary AWS Region. Automate infrastructure deployment in the secondary Region by using AWS CloudFormation.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

41. 

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


