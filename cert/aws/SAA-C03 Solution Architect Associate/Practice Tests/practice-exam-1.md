# Practice Exam 1

Click on the **Answer** button for the correct answer and its explanation.

If this practice exam has been helpful to you please share it with others and react to this below.

---

1. A company wants to migrate its on-premises application to AWS. The application produces output files that vary in size from tens of gigabytes to hundreds of terabytes. The application data must be stored in a standard file system structure. The company wants a solution that scales automatically. is highly available, and requires minimum operational overhead. Which solution will meet these requirements?
    - A. Migrate the application to run as containers on Amazon Elastic Kubernetes Service (Amazon EKS). Use Amazon Elastic Block Store (Amazon EBS) for storage.
    - B. Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic File System (Amazon EFS) for storage.
    - C. Migrate the application to run as containers on Amazon Elastic Container Service (Amazon ECS). Use Amazon S3 for storage.
    - D. Migrate the application to Amazon EC2 instances in a Multi-AZ Auto Scaling group. Use Amazon Elastic Block Store (Amazon EBS) for storage.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

2. A company has a three-tier web application that is deployed on AWS. The web servers are deployed in a public subnet in a VPC. The application servers and database servers are deployed in private subnets in the same VPC. The company has deployed a third-party virtual firewall appliance from AWS Marketplace in an inspection VPC. The appliance is configured with an IP interface that can accept IP packets. A solutions architect needs to integrate the web application with the appliance to inspect all traffic to the application before the traffic reaches the web server. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Deploy a Gateway Load Balancer in the inspection VPC. Create a Gateway Load Balancer endpoint to receive the incoming packets and forward the packets to the appliance.
    - B. Deploy a transit gateway in the inspection VPConfigure route tables to route the incoming packets through the transit gateway.
    - C. Create a Network Load Balancer in the public subnet of the application's VPC to route the traffic to the appliance for packet inspection.
    - D. Create an Application Load Balancer in the public subnet of the application's VPC to route the traffic to the appliance for packet inspection.
  
3. A company wants to run its critical applications in containers to meet requirements for scalability and availability. The company prefers to focus on maintenance of the critical applications. The company does not want to be responsible for provisioning and managing the underlying infrastructure that runs the containerized workload. What should a solutions architect do to meet these requirements?
    - A. Use Amazon Elastic Container Service (Amazon ECS) on AWS Fargate.
    - B. Use Amazon EC2 instances, and install Docker on the instances.
    - C. Use Amazon EC2 instances from an Amazon Elastic Container Service (Amazon ECS)-optimized Amazon Machine Image (AMI).
    - D. Use Amazon Elastic Container Service (Amazon ECS) on Amazon EC2 worker nodes.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

4. A company is developing an application that provides order shipping statistics for retrieval
by a REST API. The company wants to extract the shipping statistics, organize the data
into an easy-to-read HTML format, and send the report to several email addresses at the
same time every morning. Which combination of steps should a solutions architect take to
meet these requirements? (**Choose two.**)
    - A. Store the application data in Amazon S3. Create an Amazon Simple Notification Service (Amazon SNS) topic as an S3 event destination to send the report by email.
    - B. Configure the application to send the data to Amazon Kinesis Data Firehose.
    - C. Use Amazon Simple Email Service (Amazon SES) to format the data and to send the report by email.
    - D. Create an Amazon EventBridge (Amazon CloudWatch Events) scheduled event that invokes an AWS Glue job to query the application's API for the data.
    - E. Create an Amazon EventBridge (Amazon CloudWatch Events) scheduled event
that invokes an AWS Lambda function to query the application's API for the
data.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C, E
    </details>

5. A company is hosting a web application on AWS using a single Amazon EC2 instance that stores user-uploaded documents in an Amazon EBS volume. For better scalability and availability, the company duplicated the architecture and created a second EC2 instance and EBS volume in another Availability Zone, placing both behind an Application Load Balancer. After completing this change, users reported that, each time they refreshed the website, they could see one subset of their documents or the other, but never all of the documents at the same time. What should a solutions architect propose to ensure users see all of their documents at once?
    - A. Copy the data from both EBS volumes to Amazon EFS. Modify the application to save new documents to Amazon EFS
    - B. Configure the Application Load Balancer to send the request to both servers. Return each document from the correct server
    - C. Copy the data so both EBS volumes contain all the documents
    - D. Configure the Application Load Balancer to direct a user to the server with the documents

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

6. A company is migrating a distributed application to AWS. The application serves variable workloads. The legacy platform consists of a primary server that coordinates jobs across multiple compute nodes. The company wants to modernize the application with a solution that maximizes resiliency and scalability. How should a solutions architect design the architecture to meet these requirements?
    - A. Implement the primary server and the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure AWS CloudTrail as a destination for the jobs. Configure EC2 Auto Scaling based on the load on the primary server.
    - B. Configure an Amazon Simple Queue Service (Amazon SQS) queue as a destination for the jobs. Implement the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure EC2 Auto Scaling based on the size of the queue.
    - C. Implement the primary server and the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure Amazon EventBridge (Amazon CloudWatch Events) as a destination for the jobs. Configure EC2 Auto Scaling based on the load on the compute nodes.
    - D. Configure an Amazon Simple Queue Service (Amazon SQS) queue as a destination for the jobs. Implement the compute nodes with Amazon EC2 instances that are managed in an Auto Scaling group. Configure EC2 Auto Scaling to use scheduled scaling.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

7. A company is building an application in the AWS Cloud. The application will store data in Amazon S3 buckets in two AWS Regions. The company must use an AWS Key Management Service (AWS KMS) customer managed key to encrypt all data that is stored in the S3 buckets. The data in both S3 buckets must be encrypted and decrypted with the same KMS key. The data and the key must be stored in each of the two Regions. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Create a customer managed KMS key and an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Configure replication between the S3 buckets.
    - B. Create a customer managed multi-Region KMS key. Create an S3 bucket in each Region. Configure replication between the S3 buckets. Configure the application to use the KMS key with client-side encryption.
    - C. Create an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Configure replication between the S3 buckets.
    - D. Create a customer managed KMS key and an S3 bucket in each Region. Configure the S3 buckets to use server-side encryption with AWS KMS keys (SSE-KMS). Configure replication between the S3 buckets.

   <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

8. A company wants to improve its ability to clone large amounts of production data into a test environment in the same AWS Region. The data is stored in Amazon EC2 instances on Amazon Elastic Block Store (Amazon EBS) volumes. Modifications to the cloned data must not affect the production environment. The software that accesses this data requires consistently high I/O performance. A solutions architect needs to minimize the time that is required to clone the production data into the test environment. Which solution will meet these requirements?
    - A. Configure the production EBS volumes to use the EBS Multi-Attach feature. Take EBS snapshots of the production EBS volumes. Attach the production EBS volumes to the EC2 instances in the test environment.
    - B. Take EBS snapshots of the production EBS volumes. Create and initialize new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment before restoring the volumes from the production EBS snapshots.
    - C. Take EBS snapshots of the production EBS volumes. Turn on the EBS fast snapshot restore feature on the EBS snapshots. Restore the snapshots into new EBS volumes. Attach the new EBS volumes to EC2 instances in the test environment.
    - D. Take EBS snapshots of the production EBS volumes. Restore the snapshots onto EC2 instance store volumes in the test environment.
   
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

9. A company observes an increase in Amazon EC2 costs in its most recent bill. The billing team notices unwanted vertical scaling of instance types for a couple of EC2 instances. A solutions architect needs to create a graph comparing the last 2 months of EC2 costs and perform an in-depth analysis to identify the root cause of the vertical scaling. How should the solutions architect generate the information with the LEAST operational overhead?
    - A. Use AWS Budgets to create a budget report and compare EC2 costs based on instance types.
    - B. Use AWS Cost and Usage Reports to create a report and send it to an Amazon S3 bucket. Use Amazon QuickSight with Amazon S3 as a source to generate an interactive graph based on instance types.
    - C. Use graphs from the AWS Billing and Cost Management dashboard to compare EC2 costs based on instance types for the last 2 months.
    - D. Use Cost Explorer's granular filtering feature to perform an in-depth analysis of EC2 costs based on instance types.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

10. A solutions architect is using Amazon S3 to design the storage architecture of a new digital media application. The media files must be resilient to the loss of an Availability Zone. Some files are accessed frequently while other files are rarely accessed in an unpredictable pattern. The solutions architect must minimize the costs of storing and retrieving the media files. Which storage option meets these requirements?
    - A. S3 Intelligent-Tiering
    - B. S3 Standard
    - C. S3 Standard-Infrequent Access (S3 Standard-IA)
    - D. S3 One Zone-Infrequent Access (S3 One Zone-IA)

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

11. A company is implementing a new business application. The application runs on two Amazon EC2 instances and uses an Amazon S3 bucket for document storage. A solutions architect needs to ensure that the EC2 instances can access the S3 bucket. What should the solutions architect do to meet this requirement?
    - A. Create an IAM group that grants access to the S3 bucket. Attach the group to the EC2 instances.
    - B. Create an IAM role that grants access to the S3 bucket. Attach the role to the EC2 instances.
    - C. Create an IAM policy that grants access to the S3 bucket. Attach the policy to the EC2 instances.
    - D. Create an IAM user that grants access to the S3 bucket. Attach the user account to the EC2 instances.
   
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

12. A company recently launched a variety of new workloads on Amazon EC2 instances in its AWS account. The company needs to create a strategy to access and administer the instances remotely and securely. The company needs to implement a repeatable process that works with native AWS services and follows the AWS Well-Architected Framework. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Create an administrative SSH key pair. Load the public key into each EC2 instance. Deploy a bastion host in a public subnet to provide a tunnel for administration of each instance.
    - B. Attach the appropriate IAM role to each existing instance and new instance. Use AWS Systems Manager Session Manager to establish a remote SSH session.
    - C. Establish an AWS Site-to-Site VPN connection. Instruct administrators to use their local on-premises machines to connect directly to the instances by using SSH keys across the VPN tunnel.
    - D. Use the EC2 serial console to directly access the terminal interface of each instance for administration.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

13. A development team needs to host a website that will be accessed by other teams. The website contents consist of HTML, CSS, client-side JavaScript, and images. Which method is the MOST cost-effective for hosting the website?
    - A. Containerize the website and host it in AWS Fargate.
    - B. Create an Amazon S3 bucket and host the website there.
    - C. Deploy a web server on an Amazon EC2 instance to host the website.
    - D. Configure an Application Load Balancer with an AWS Lambda target that uses the Express.js framework. 

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

14. A company runs a highly available image-processing application on Amazon EC2 instances in a single VPC. The EC2 instances run inside several subnets across multiple Availability Zones. The EC2 instances do not communicate with each other. However, the EC2 instances download images from Amazon S3 and upload images to Amazon S3 through a single NAT gateway. The company is concerned about data transfer charges. What is the MOST cost-effective way for the company to avoid Regional data transfer charges?
    - A. Deploy a gateway VPC endpoint for Amazon S3.
    - B. Replace the NAT gateway with a NAT instance.
    - C. Launch the NAT gateway in each Availability Zone.
    - D. Provision an EC2 Dedicated Host to run the EC2 instances.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

15. A development team runs monthly resource-intensive tests on its general purpose Amazon RDS for MySQL DB instance with Performance Insights enabled. The testing lasts for 48 hours once a month and is the only process that uses the database. The team wants to reduce the cost of running the tests without reducing the compute and memory attributes of the DB instance. Which solution meets these requirements MOST cost-effectively?
    - A. Use an Auto Scaling policy with the DB instance to automatically scale when tests are completed.
    - B. Create a snapshot when tests are completed. Terminate the DB instance and restore the snapshot when required.
    - C. Stop the DB instance when tests are completed. Restart the DB instance when required.
    - D. Modify the DB instance to a low-capacity instance when tests are completed. Modify the DB instance again when required.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

16. A company needs to review its AWS Cloud deployment to ensure that its Amazon S3 buckets do not have unauthorized configuration changes. What should a solutions architect do to accomplish this goal?
    - A. Turn on Amazon Inspector with the appropriate assessment template.
    - B. Turn on AWS Trusted Advisor with the appropriate checks.
    - C. Turn on AWS Config with the appropriate rules.
    - D. Turn on Amazon S3 server access logging. Configure Amazon EventBridge (Amazon Cloud Watch Events).

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

17. A company needs the ability to analyze the log files of its proprietary application. The logs are stored in JSON format in an Amazon S3 bucket. Queries will be simple and will run on-demand. A solutions architect needs to perform the analysis with minimal changes to the existing architecture. What should the solutions architect do to meet these requirements with the LEAST amount of operational overhead?
    - A. Use Amazon Athena directly with Amazon S3 to run the queries as needed.
    - B. Use AWS Glue to catalog the logs. Use a transient Apache Spark cluster on Amazon EMR to run the SQL queries as needed.
    - C. Use Amazon CloudWatch Logs to store the logs. Run SQL queries as needed from the Amazon CloudWatch console.
    - D. Use Amazon Redshift to load all the content into one place and run the SQL queries as needed.
   
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

18. A company collects data for temperature, humidity, and atmospheric pressure in cities across multiple continents. The average volume of data that the company collects from each site daily is 500 GB. Each site has a high-speed Internet connection. The company wants to aggregate the data from all these global sites as quickly as possible in a single Amazon S3 bucket. The solution must minimize operational complexity. Which solution meets these requirements?
    - A. Upload the data from each site to an S3 bucket in the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket. Then remove the data from the origin S3 bucket.
    - B. Turn on S3 Transfer Acceleration on the destination S3 bucket. Use multipart uploads to directly upload site data to the destination S3 bucket.
    - C. Schedule AWS Snowball Edge Storage Optimized device jobs daily to transfer data from each site to the closest Region. Use S3 Cross-Region Replication to copy objects to the destination S3 bucket.
    - D. Upload the data from each site to an Amazon EC2 instance in the closest Region. Store the data in an Amazon Elastic Block Store (Amazon EBS) volume. At regular intervals, take an EBS snapshot and copy it to the Region that contains the destination S3 bucket. Restore the EBS volume in that Region.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

19. A company has an Amazon S3 bucket that contains critical data. The company must protect the data from accidental deletion. Which combination of steps should a solutions architect take to meet these requirements? (**Choose two.**)
    - A. Enable default encryption on the S3 bucket.
    - B. Create a lifecycle policy for the objects in the S3 bucket.
    - C. Create a bucket policy on the S3 bucket.
    - D. Enable versioning on the S3 bucket.
    - E. Enable MFA Delete on the S3 bucket.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D, E
    </details>

20. An application development team is designing a microservice that will convert large images to smaller, compressed images. When a user uploads an image through the web interface, the microservice should store the image in an Amazon S3 bucket, process and compress the image with an AWS Lambda function, and store the image in its compressed form in a different S3 bucket. A solutions architect needs to design a solution that uses durable, stateless components to process the images automatically. Which combination of actions
will meet these requirements? (**Choose two.**)
    - A. Configure the Lambda function to monitor the S3 bucket for new uploads. When an uploaded image is detected, write the file name to a text file in memory and use the text file to keep track of the images that were processed.
    - B. Configure the Lambda function to use the Amazon Simple Queue Service (Amazon SQS) queue as the invocation source. When the SQS message is successfully processed, delete the message in the queue.
    - C. Create an Amazon Simple Queue Service (Amazon SQS) queue. Configure the S3 bucket to send a notification to the SQS queue when an image is uploaded to the S3 bucket.
    - D. Configure an Amazon EventBridge (Amazon CloudWatch Events) event to monitor the S3 bucket. When an image is uploaded, send an alert to an Amazon ample Notification Service (Amazon SNS) topic with the application owner's email address for further processing.
    - E. Launch an Amazon EC2 instance to monitor an Amazon Simple Queue Service (Amazon SQS) queue. When items are added to the queue, log the file name in a text file on the EC2 instance and invoke the Lambda function.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, C
    </details>

21. A company that hosts its web application on AWS wants to ensure all Amazon EC2 instances. Amazon RDS DB instances. and Amazon Redshift clusters are configured with tags. The company wants to minimize the effort of configuring and operating this check. What should a solutions architect do to accomplish this?
    - A. Write API calls to check all resources for proper tag allocation. Schedule an AWS Lambda function through Amazon CloudWatch to periodically run the code.
    - B. Use AWS Config rules to define and detect resources that are not properly tagged.
    - C. Write API calls to check all resources for proper tag allocation. Periodically run the code on an EC2 instance.
    - D. Use Cost Explorer to display resources that are not properly tagged. Tag those resources manually.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

22. A company hosts a data lake on AWS. The data lake consists of data in Amazon S3 and Amazon RDS for PostgreSQL. The company needs a reporting solution that provides data visualization and includes all the data sources within the data lake. Only the company's management team should have full access to all the visualizations. The rest of the company should have only limited access. Which solution will meet these requirements?
    - A. Create an AWS Glue table and crawler for the data in Amazon S3. Create an AWS Glue extract, transform, and load (ETL) job to produce reports. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the reports.
    - B. Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data. Share the dashboards with the appropriate IAM roles.
    - C. Create an AWS Glue table and crawler for the data in Amazon S3. Use Amazon Athena Federated Query to access data within Amazon RDS for PostgreSQL. Generate reports by using Amazon Athena. Publish the reports to Amazon S3. Use S3 bucket policies to limit access to the reports.
    - D. Create an analysis in Amazon QuickSight. Connect all the data sources and create new datasets. Publish dashboards to visualize the data. Share the dashboards with the appropriate users and groups.
    
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

23. A company is building an ecommerce web application on AWS. The application sends information about new orders to an Amazon API Gateway REST API to process. The company wants to ensure that orders are processed in the order that they are received. Which solution will meet these requirements?
    - A. Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) FIFO queue when the application receives an order. Configure the SQS FIFO queue to invoke an AWS Lambda function for processing.
    - B. Use an API Gateway integration to send a message to an Amazon Simple Queue Service (Amazon SQS) standard queue when the application receives an order. Configure the SQS standard queue to invoke an AWS Lambda function for processing.
    - C. Use an API Gateway integration to publish a message to an Amazon Simple Notification Service (Amazon SNS) topic when the application receives an order. Subscribe an AWS Lambda function to the topic to perform processing.
    - D. Use an API Gateway authorizer to block any requests while the application processes an order.
    
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

24. A company is running a popular social media website. The website gives users the ability to upload images to share with other users. The company wants to make sure that the images do not contain inappropriate content. The company needs a solution that minimizes development effort. What should a solutions architect do to meet these requirements?
    - A. Use Amazon Comprehend to detect inappropriate content. Use human review for low-confidence predictions.
    - B. Use Amazon SageMaker to detect inappropriate content. Use ground truth to label low-confidence predictions.
    - C. Use Amazon Rekognition to detect inappropriate content. Use human review for low-confidence predictions.
    - D. Use AWS Fargate to deploy a custom machine learning model to detect inappropriate content. Use ground truth to label low-confidence predictions.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

25. A company uses NFS to store large video files in on-premises network attached storage. Each video file ranges in size from 1 MB to 500 GB. The total storage is 70 TB and is no longer growing. The company decides to migrate the video files to Amazon S3. The company must migrate the video files as soon as possible while using the least possible network bandwidth. Which solution will meet these requirements?
    - A. Deploy an S3 File Gateway on premises. Create a public service endpoint to connect to the S3 File Gateway. Create an S3 bucket. Create a new NFS file share on the S3 File Gateway. Point the new file share to the S3 bucket. Transfer the data from the existing NFS file share to the S3 File Gateway.
    - B. Create an S3 bucket. Create an IAM role that has permissions to write to the S3 bucket. Use the AWS CLI to copy all files locally to the S3 bucket.
    - C. Create an AWS Snowball Edge job. Receive a Snowball Edge device on premises. Use the Snowball Edge client to transfer data to the device. Return the device so that AWS can import the data into Amazon S3.
    - D. Set up an AWS Direct Connect connection between the on-premises network and AWS. Deploy an S3 File Gateway on premises. Create a public virtual interface (VIF) to connect to the S3 File Gateway. Create an S3 bucket. Create a new NFS file share on the S3 File Gateway. Point the new file share to the S3 bucket. Transfer the data from the existing NFS file share to the S3 File Gateway.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

26. An application runs on an Amazon EC2 instance in a VPC. The application processes logs that are stored in an Amazon S3 bucket. The EC2 instance needs to access the S3 bucket without connectivity to the internet. Which solution will provide private network connectivity to Amazon S3?
    - A. Create a gateway VPC endpoint to the S3 bucket.
    - B. Stream the logs to Amazon CloudWatch Logs. Export the logs to the S3 bucket.
    - C. Create an instance profile on Amazon EC2 to allow S3 access.
    - D. Create an Amazon API Gateway API with a private link to access the S3 endpoint.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

27. A company hosts more than 300 global websites and applications. The company requires a platform to analyze more than 30 TB of clickstream data each day. What should a solutions architect do to transmit and process the clickstream data?
    - A. Design an AWS Data Pipeline to archive the data to an Amazon S3 bucket and run an Amazon EMR cluster with the data to generate analytics.
    - B. Cache the data to Amazon CloudFront. Store the data in an Amazon S3 bucket. When an object is added to the S3 bucket. run an AWS Lambda function to process the data for analysis.
    - C. Create an Auto Scaling group of Amazon EC2 instances to process the data and send it to an Amazon S3 data lake for Amazon Redshift to use for analysis.
    - D. Collect the data from Amazon Kinesis Data Streams. Use Amazon Kinesis Data Firehose to transmit the data to an Amazon S3 data lake. Load the data in Amazon Redshift for analysis.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

28. A company performs monthly maintenance on its AWS infrastructure. During these maintenance activities, the company needs to rotate the credentials for its Amazon RDS for MySQL databases across multiple AWS Regions. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Store the credentials as secrets in AWS Systems Manager by creating a secure string parameter. Use multi-Region secret replication for the required Regions. Configure Systems Manager to rotate the secrets on a schedule.
    - B. Store the credentials as secrets in AWS Secrets Manager. Use multi-Region secret replication for the required Regions. Configure Secrets Manager to rotate the secrets on a schedule.
    - C. Encrypt the credentials as secrets by using AWS Key Management Service (AWS KMS) multi-Region customer managed keys. Store the secrets in an Amazon DynamoDB global table. Use an AWS Lambda function to retrieve the secrets from DynamoDB. Use the RDS API to rotate the secrets.
    - D. Store the credentials in an Amazon S3 bucket that has server-side encryption (SSE) enabled. Use Amazon EventBridge (Amazon CloudWatch Events) to invoke an AWS Lambda function to rotate the credentials.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

29. A solutions architect is developing a VPC architecture that includes multiple subnets. The architecture will host applications that use Amazon EC2 instances and Amazon RDS DB instances. The architecture consists of six subnets in two Availability Zones. Each Availability Zone includes a public subnet, a private subnet, and a dedicated subnet for databases. Only EC2 instances that run in the private subnets can have access to the RDS databases. Which solution will meet these requirements?
    - A. Create a security group that allows inbound traffic from the security group that is assigned to instances in the private subnets. Attach the security group to the DB instances.
    - B. Create a new peering connection between the public subnets and the private subnets. Create a different peering connection between the private subnets and the database subnets.
    - C. Create a new route table that excludes the route to the public subnets' CIDR blocks. Associate the route table with the database subnets.
    - D. Create a security group that denies inbound traffic from the security group that is assigned to instances in the public subnets. Attach the security group to the DB instances.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

30. A company's application integrates with multiple software-as-a-service (SaaS) sources for data collection. The company runs Amazon EC2 instances to receive the data and to upload the data to an Amazon S3 bucket for analysis. The same EC2 instance that receives and uploads the data also sends a notification to the user when an upload is complete. The company has noticed slow application performance and wants to improve the performance as much as possible. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Create an Amazon AppFlow flow to transfer data between each SaaS source and the S3 bucket. Configure an S3 event notification to send events to an Amazon Simple Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.
    - B. Create an Auto Scaling group so that EC2 instances can scale out. Configure an S3 event notification to send events to an Amazon Simple Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.
    - C. Create an Amazon EventBridge (Amazon CloudWatch Events) rule for each SaaS source to send output data. Configure the S3 bucket as the rule's target. Create a second EventBridge (Cloud Watch Events) rule to send events when the upload to the S3 bucket is complete. Configure an Amazon Simple Notification Service (Amazon SNS) topic as the second rule's target.
    - D. Create a Docker container to use instead of an EC2 instance. Host the containerized application on Amazon Elastic Container Service (Amazon ECS). Configure Amazon CloudWatch Container Insights to send events to an Amazon Simple Notification Service (Amazon SNS) topic when the upload to the S3 bucket is complete.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

31. A company maintains a searchable repository of items on its website. The data is stored in an Amazon RDS for MySQL database table that contains more than 10 million rows. The database has 2 TB of General Purpose SSD storage. There are millions of updates against this data every day through the company's website. The company has noticed that some insert operations are taking 10 seconds or longer. The company has determined that the database storage performance is the problem. Which solution addresses this performance issue?
    - A. Enable Multi-AZ RDS read replicas with MySQL native asynchronous replication.
    - B. Change the storage type to Provisioned IOPS SSD.
    - C. Change the DB instance to a burstable performance instance class.
    - D. Change the DB instance to a memory optimized instance class.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

32. A company is migrating applications to AWS. The applications are deployed in different accounts. The company manages the accounts centrally by using AWS Organizations. The company's security team needs a single sign-on (SSO) solution across all the company's accounts. The company must continue managing the users and groups in its on-premises self-managed Microsoft Active Directory. Which solution will meet these requirements?
    - A. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a one-way forest trust or a one-way domain trust to connect the company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.
    - B. Deploy an identity provider (IdP) on premises. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console.
    - C. Enable AWS Single Sign-On (AWS SSO) from the AWS SSO console. Create a two-way forest trust to connect the company's self-managed Microsoft Active Directory with AWS SSO by using AWS Directory Service for Microsoft Active Directory.
    - D. Use AWS Directory Service. Create a two-way trust relationship with the company's self-managed Microsoft Active Directory.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

33. A company recently migrated to AWS and wants to implement a solution to protect the traffic that flows in and out of the production VPC. The company had an inspection server in its on-premises data center. The inspection server performed specific operations such as traffic flow inspection and traffic filtering. The company wants to have the same functionalities in the AWS Cloud. Which solution will meet these requirements?
    - A. Use AWS Network Firewall to create the required rules for traffic inspection and traffic filtering for the production VPC.
    - B. Use Traffic Mirroring to mirror traffic from the production VPC for traffic inspection and filtering.
    - C. Use AWS Firewall Manager to create the required rules for traffic inspection and traffic filtering for the production VPC.
    - D. Use Amazon GuardDuty for traffic inspection and traffic filtering in the production VPC.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

34. An ecommerce company wants to launch a one-deal-a-day website on AWS. Each day will feature exactly one product on sale for a period of 24 hours. The company wants to be able to handle millions of requests each hour with millisecond latency during peak hours. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Deploy the full website on Amazon EC2 instances that run in Auto Scaling groups across multiple Availability Zones. Add an Application Load Balancer (ALB) to distribute the website traffic. Add another ALB for the backend APIs. Store the data in Amazon RDS for MySQL.
    - B. 
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

