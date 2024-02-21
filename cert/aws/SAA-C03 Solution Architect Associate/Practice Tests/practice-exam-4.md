# Practice Exam 4

Click on the **Answer** button for the correct answer and its explanation.

If this practice exam has been helpful to you please share it with others and react to this below.

---

1. A company runs demonstration environments for its customers on Amazon EC2 instances. Each environment is isolated in its own VPC. The company’s operations team needs to be notified when RDP or SSH access to an environment has been established.
    - A. Publish VPC flow logs to Amazon CloudWatch Logs. Create required metric filters. Create an Amazon CloudWatch metric alarm with a notification action for when the alarm is in the ALARM state.
    - B. Configure an Amazon EventBridge rule to listen for events of type EC2 Instance State-change Notification. Configure an Amazon Simple Notification Service (Amazon SNS) topic as a target. Subscribe the operations team to the topic.
    - C. Configure Amazon CloudWatch Application Insights to create AWS Systems Manager OpsItems when RDP or SSH access is detected.
    - D. Configure the EC2 instances with an IAM instance profile that has an IAM role with the AmazonSSMManagedInstanceCore policy attached.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

2. A company is running a batch application on Amazon EC2 instances. The application consists of a backend with multiple Amazon RDS databases. The application is causing a high number of reads on the databases. A solutions architect must reduce the number of
database reads while ensuring high availability. What should the solutions architect do to meet this requirement?
    - A. Use Amazon Route 53 DNS caching.
    - B. Use Amazon ElastiCache for Redis.
    - C. Use Amazon ElastiCache for Memcached.
    - D. Add Amazon RDS read replicas.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

3. A company has a Microsoft .NET application that runs on an on-premises Windows
Server. The application stores data by using an Oracle Database Standard Edition server.
The company is planning a migration to AWS and wants to minimize development changes
while moving the application. The AWS application environment should be highly
available. Which combination of actions should the company take to meet these
requirements? (**Choose two.**)
    - A. Refactor the application as serverless with AWS Lambda functions running .NET Core.
    - B. Replatform the application to run on Amazon EC2 with the Amazon Linux Amazon Machine Image (AMI).
    - C. Rehost the application in AWS Elastic Beanstalk with the .NET platform in a Multi-AZ deployment.(Correct)
    - D. Use AWS Database Migration Service (AWS DMS) to migrate from the Oracle database to Oracle on Amazon RDS in a Multi-AZ  deployment.
    - E. Use AWS Database Migration Service (AWS DMS) to migrate from the Oracle database to Amazon DynamoDB in a Multi-AZ deployment.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C, D
    </details>

4. A company runs an application on a group of Amazon Linux EC2 instances. For
compliance reasons, the company must retain all application log files for 7 years. The log
files will be analyzed by a reporting tool that must be able to access all the files
concurrently. Which storage solution meets these requirements MOST cost-effectively?
    - A. Amazon S3
    - B. Amazon Elastic Block Store (Amazon EBS)
    - C. Amazon Elastic File System (Amazon EFS)
    - D. Amazon EC2 instance store
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

5. A company hosts its application on AWS. The company uses Amazon Cognito to manage
users. When users log in to the application, the application fetches required data from
Amazon DynamoDB by using a REST API that is hosted in Amazon API Gateway. The
company wants an AWS managed solution that will control access to the REST API to
reduce development efforts. Which solution will meet these requirements with the LEAST
operational overhead?
    - A. Send the user’s email address in the header with every request. Invoke an AWS Lambda function to validate that the user with that email address has proper access.
    - B. For each user, create and assign an API key that must be sent with each request. Validate the key by using an AWS Lambda function.
    - C. Configure an AWS Lambda function to be an authorizer in API Gateway to validate which user made the request.
    - D. Configure an Amazon Cognito user pool authorizer in API Gateway to allow Amazon Cognito to validate each request.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

6. A company is building a new web-based customer relationship management application. The application will use several Amazon EC2 instances that are backed by Amazon Elastic Block Store (Amazon EBS) volumes behind an Application Load Balancer (ALB). The application will also use an Amazon Aurora database. All data for the application must be encrypted at rest and in transit. Which solution will meet these requirements?
    - A. Use the AWS root account to log in to the AWS Management Console. Upload the company’s encryption certificates. While in the root account, select the option to turn on encryption for all data at rest and in transit for the account.
    - B. Use BitLocker to encrypt all data at rest. Import the company’s TLS certificate keys to AWS Key Management Service (AWS KMS) Attach the KMS keys to the ALB to encrypt data in transit.
    - C. Use AWS Key Management Service (AWS KMS) to encrypt the EBS volumes and Aurora database storage at rest. Attach an AWS Certificate Manager (ACM) certificate to the ALB to encrypt data in transit.
    - D. Use AWS Key Management Service (AWS KMS) certificates on the ALB to encrypt data in transit. Use AWS Certificate Manager (ACM) to encrypt the EBS volumes and Aurora database storage at rest.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

7. A company has an AWS account used for software engineering. The AWS account has access to the company’s on-premises data center through a pair of AWS Direct Connect connections. All non-VPC traffic routes to the virtual private gateway. A development team recently created an AWS Lambda function through the console. The development team needs to allow the function to access a database that runs in a private subnet in the company’s data center. Which solution will meet these requirements? 
    - A. Update the route tables in the VPC to allow the Lambda function to access the on-premises data center through Direct Connect.
    - B. Configure the Lambda function to run in the VPC with the appropriate security group. 
    - C. Set up a VPN connection from AWS to the data center. Route the traffic from the Lambda function through the VPN.
    - D. Create an Elastic IP address. Configure the Lambda function to send traffic through the Elastic IP address without an elastic network interface.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

8. A company collects data from thousands of remote devices by using a RESTful web
services application that runs on an Amazon EC2 instance. The EC2 instance receives the
raw data, transforms the raw data, and stores all the data in an Amazon S3 bucket. The
number of remote devices will increase into the millions soon. The company needs a highly
scalable solution that minimizes operational overhead. Which combination of steps should
a solutions architect take to meet these requirements? (**Choose two.**)
    - A. Use Amazon Route 53 to route traffic to different EC2 instances.
    - B. Use AWS Glue to process the raw data in Amazon S3.
    - C. Use Amazon API Gateway to send the raw data to an Amazon Kinesis data stream. Configure Amazon Kinesis Data Firehose to use the data stream as a source to deliver the data to Amazon S3.
    - D. Add more EC2 instances to accommodate the increasing amount of incoming data.
    - E. Send the raw data to Amazon Simple Queue Service (Amazon SQS). Use EC2 instances to process the data.
      
   <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, C
    </details>

9. A company uses Amazon S3 as its data lake. The company has a new partner that must use
SFTP to upload data files. A solutions architect needs to implement a highly available
SFTP solution that minimizes operational overhead. Which solution will meet these
requirements?
    - A. Use AWS Transfer Family to configure an SFTP-enabled server with a publicly accessible endpoint. Choose the S3 data lake as the destination.
    - B. Launch Amazon EC2 instances in a private subnet in a VPC. Place a Network Load Balancer (NLB) in front of the EC2 instances. Create an SFTP listener port for the NLB. Share the NLB hostname with the new partner. Run a cron job script on the EC2 instances to upload files to the S3 data lake.
    - C. Launch an Amazon EC2 instance in a private subnet in a VPInstruct the new partner to upload files to the EC2 instance by using a VPN. Run a cron job script, on the EC2 instance to upload files to the S3 data lake.
    - D. Use Amazon S3 File Gateway as an SFTP server. Expose the S3 File Gateway endpoint URL to the new partner. Share the S3 File Gateway endpoint with the new partner.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

10. A company runs an application using Amazon ECS. The application creates resized versions of an original image and then makes Amazon S3 API calls to store the resized images in Amazon S3. How can a solutions architect ensure that the application has permission to access Amazon S3?
    - A. Create an IAM role with S3 permissions, and then specify that role as the taskRoleArn in the task definition.
    - B. Update the S3 role in AWS IAM to allow read/write access from Amazon ECS, and then relaunch the container.
    - C. Create an IAM user with S3 permissions, and then relaunch the Amazon EC2 instances for the ECS cluster while logged in as this account.
    - D. Create a security group that allows access from Amazon ECS to Amazon S3, and update the launch configuration used by the ECS cluster.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

11. A company is developing a new mobile app. The company must implement proper traffic filtering to protect its Application Load Balancer (ALB) against common application-level attacks, such as cross-site scripting or SQL injection. The company has minimal infrastructure and operational staff. The company needs to reduce its share of the responsibility in managing, updating, and securing servers for its AWS environment. What should a solutions architect recommend to meet these requirements?
    - A. Deploy the application using Amazon S3 with public hosting enabled.
    - B. Configure AWS WAF rules and associate them with the ALB. 
    - C. Deploy AWS Shield Advanced and add the ALB as a protected resource.
    - D. Create a new ALB that directs traffic to an Amazon EC2 instance running a third-party firewall, which then passes the traffic to the current ALB.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

12. A company’s application is having performance issues. The application is stateful and needs to complete in-memory tasks on Amazon EC2 instances. The company used AWS CloudFormation to deploy infrastructure and used the M5 EC2 instance family. As traffic increased, the application performance degraded. Users are reporting delays when the users attempt to access the application. Which solution will resolve these issues in the MOST operationally efficient way?
    - A. Replace the EC2 instances with T3 EC2 instances that run in an Auto Scaling group. Make the changes by using the AWS Management Console.
    - B. Modify the CloudFormation templates to run the EC2 instances in an Auto Scaling group. Increase the desired capacity and the maximum capacity of the Auto Scaling group manually when an increase is necessary.
    - C. Modify the CloudFormation templates. Replace the EC2 instances with R5 EC2 instances. Use Amazon CloudWatch built-in EC2 memory metrics to track the application performance for future capacity planning.
    - D. Modify the CloudFormation templates. Replace the EC2 instances with R5 EC2 instances. Deploy the Amazon CloudWatch agent on the EC2 instances to generate custom application latency metrics for future capacity planning.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

13. A solutions architect has created a new AWS account and must secure AWS account root
user access. Which combination of actions will accomplish this? (**Choose two.**)
    - A. Add the root user to a group containing administrative permissions.
    - B. Enable multi-factor authentication to the root user.
    - C. Ensure the root user uses a strong password.
    - D. Apply the required permissions to the root user with an inline policy document.
    - E. Store root user access keys in an encrypted Amazon S3 bucket.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, C
    </details>

14. A solutions architect is designing the architecture of a new application being deployed to the AWS Cloud. The application will run on Amazon EC2 On-Demand Instances and will automatically scale across multiple Availability Zones. The EC2 instances will scale up and down frequently throughout the day. An Application Load Balancer (ALB) will handle the load distribution. The architecture needs to support distributed session data management. The company is willing to make changes to code if needed. What should the solutions architect do to ensure that the architecture supports distributed session data management?
    - A. Use Amazon ElastiCache to manage and store session data. 
    - B. Use session affinity (sticky sessions) of the ALB to manage session data.
    - C. Use the GetSessionToken API operation in AWS Security Token Service (AWS STS) to manage the session.
    - D. Use Session Manager from AWS Systems Manager to manage the session.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

15. A company’s reporting system delivers hundreds of .csv files to an Amazon S3 bucket each day. The company must convert these files to Apache Parquet format and must store the files in a transformed data bucket. Which solution will meet these requirements with the LEAST development effort?
    - A. Use AWS Batch to create a job definition with Bash syntax to transform the data and output the data to the transformed data bucket. Use the job definition to submit a job. Specify an array job as the job type.
    - B. Create an AWS Glue crawler to discover the data. Create an AWS Glue extract, transform, and load (ETL) job to transform the data. Specify the transformed data bucket in the output step.
    - C. Create an Amazon EMR cluster with Apache Spark installed. Write a Spark application to transform the data. Use EMR File System (EMRFS) to write files to the transformed data bucket.
    - D. Create an AWS Lambda function to transform the data and output the data to the transformed data bucket. Configure an event notification for the S3 bucket. Specify the Lambda function as the destination for the event notification.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

16. A company wants to migrate its MySQL database from on premises to AWS. The company recently experienced a database outage that significantly impacted the business. To ensure this does not happen again, the company wants a reliable database solution on AWS that minimizes data loss and stores every transaction on at least two nodes. Which solution meets these requirements? 
    - A. Create an Amazon RDS MySQL DB instance with Multi-AZ functionality enabled to synchronously replicate the data.
    - B. Create an Amazon RDS DB instance with synchronous replication to three nodes in three Availability Zones.
    - C. Create an Amazon EC2 instance with a MySQL engine installed that triggers an AWS Lambda function to synchronously replicate the data to an Amazon RDS MySQL DB instance.
    - D. Create an Amazon RDS MySQL DB instance and then create a read replica in a separate AWS Region that synchronously replicates the data.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

17. A company needs to run a critical application on AWS. The company needs to use Amazon EC2 for the application’s database. The database must be highly available and must fail over automatically if a disruptive event occurs. Which solution will meet these requirements?
    - A. Launch an EC2 instance in an Availability Zone. Install the database on the EC2 instance. Use an Amazon Machine Image (AMI) to back up the data. Use AWS CloudFormation to automate provisioning of the EC2 instance if a disruptive event occurs.
    - B. Launch two EC2 instances, each in a different Availability Zone in the same AWS Region. Install the database on both EC2 instances. Configure the EC2 instances as a cluster. Set up database replication. 
    - C. Launch two EC2 instances, each in a different AWS Region. Install the database on both EC2 instances. Set up database replication. Fail over the database to a second Region.
    - D. Launch an EC2 instance in an Availability Zone. Install the database on the EC2 instance. Use an Amazon Machine Image (AMI) to back up the data. Use EC2 automatic recovery to recover the instance if a disruptive event occurs.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

18. An online retail company has more than 50 million active customers and receives more than 25,000 orders each day. The company collects purchase data for customers and stores this data in Amazon S3. Additional customer data is stored in Amazon RDS. The company wants to make all the data available to various teams so that the teams can perform analytics. The solution must provide the ability to manage fine-grained permissions for the data and must minimize operational overhead. Which solution will meet these requirements?
    - A. Create an Amazon Redshift cluster. Schedule an AWS Lambda function to periodically copy data from Amazon S3 and Amazon RDS to Amazon Redshift. Use Amazon Redshift access controls to limit access.
    - B. Schedule an AWS Lambda function to periodically copy data from Amazon RDS to Amazon S3. Create an AWS Glue crawler. Use Amazon Athena to query the data. Use S3 policies to limit access.
    - C. Create a data lake by using AWS Lake Formation. Create an AWS Glue JDBC connection to Amazon RDS. Register the S3 bucket in Lake Formation. Use Lake Formation access controls to limit access.
    - D. Migrate the purchase data to write directly to Amazon RDS. Use RDS access
controls to limit access.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

19. A hospital wants to create digital copies for its large collection of historical written records. The hospital will continue to add hundreds of new documents each day. The hospital’s data team will scan the documents and will upload the documents to the AWS Cloud. A solutions architect must implement a solution to analyze the documents, extract the medical information, and store the documents so that an application can run SQL queries on the data. The solution must maximize scalability and operational efficiency. Which combination of steps should the solutions architect take to meet these requirements? (**Choose two.**)
    - A. Create an AWS Lambda function that runs when new documents are uploaded. Use Amazon Textract to convert the documents to raw text. Use Amazon Comprehend Medical to detect and extract relevant medical information from the text.
    - B. Write the document information to an Amazon EC2 instance that runs a MySQL database.
    - C. Create an Auto Scaling group of Amazon EC2 instances to run a custom application that processes the scanned files and  xtracts the medical information.
    - D. Create an AWS Lambda function that runs when new documents are uploaded. Use Amazon Rekognition to convert the documents to raw text. Use Amazon Transcribe Medical to detect and extract relevant medical information from the text.
    - E. Write the document information to an Amazon S3 bucket. Use Amazon Athena to query the data.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, E
    </details>

20. A company is concerned that two NAT instances in use will no longer be able to support
the traffic needed for the company’s application. A solutions architect wants to implement
a solution that is highly available, fault tolerant, and automatically scalable. What should
the solutions architect recommend?
    - A. Use Auto Scaling groups with Network Load Balancers for the NAT instances in different Availability Zones.
    - B. Replace the two NAT instances with Spot Instances in different Availability Zones and deploy a Network Load Balancer.
    - C. Remove the two NAT instances and replace them with two NAT gateways in the same Availability Zone.
    - D. Remove the two NAT instances and replace them with two NAT gateways in different Availability Zones.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

21. A company offers a food delivery service that is growing rapidly. Because of the growth, the company’s order processing system is experiencing scaling problems during peak traffic hours. The current architecture includes the following: • A group of Amazon EC2 instances that run in an Amazon EC2 Auto Scaling group to collect orders from the application • Another group of EC2 instances that run in an Amazon EC2 Auto Scaling group to fulfill orders The order collection process occurs quickly, but the order fulfillment process can take longer. Data must not be lost because of a scaling event. A solutions architect must ensure that the order collection process and the order fulfillment process can both scale properly during peak traffic hours. The solution must optimize utilization of the company’s AWS resources. Which solution meets these requirements?
    - A. Use Amazon CloudWatch metrics to monitor the CPU of each instance in the Auto Scaling groups. Configure a CloudWatch alarm to invoke an Amazon Simple Notification Service (Amazon SNS) topic that creates additional Auto Scaling groups on demand.
    - B. Provision two Amazon Simple Queue Service (Amazon SQS) queues: one for order collection and another for order fulfillment. Configure the EC2 instances to poll their respective queue. Create a metric based on a backlog per instance calculation. Scale the Auto Scaling groups based on this metric.
    - C. Use Amazon CloudWatch metrics to monitor the CPU of each instance in the Auto Scaling groups. Configure each Auto Scaling group’s minimum capacity according to peak workload values.
    - D. Provision two Amazon Simple Queue Service (Amazon SQS) queues: one for order collection and another for order fulfillment. Configure the EC2 instances to poll their respective queue. Scale the Auto Scaling groups based on notifications that the queues send.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

22. A company hosts multiple production applications. One of the applications consists of resources from Amazon EC2, AWS Lambda, Amazon RDS, Amazon Simple Notification Service (Amazon SNS), and Amazon Simple Queue Service (Amazon SQS) across multiple AWS Regions. All company resources are tagged with a tag name of “application” and a value that corresponds to each application. A solutions architect must provide the quickest solution for identifying all of the tagged components. Which solution meets these requirements? 
    - A. Use the AWS CLI to query each service across all Regions to report the tagged components.
    - B. Use AWS CloudTrail to generate a list of resources with the application tag.
    - C. Run a query with the AWS Resource Groups Tag Editor to report on the resources globally with the application tag.
    - D. Run a query in Amazon CloudWatch Logs Insights to report on the components with the application tag.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

23. A company has a legacy data processing application that runs on Amazon EC2 instances. Data is processed sequentially, but the order of results does not matter. The application uses a monolithic architecture. The only way that the company can scale the application to meet increased demand is to increase the size of the instances. The company’s developers have decided to rewrite the application to use a microservices architecture on Amazon Elastic Container Service (Amazon ECS). What should a solutions architect recommend for communication between the microservices?
    - A. Create an Amazon DynamoDB table. Enable DynamoDB Streams. Add code to the data producers to insert data into the table. Add code to the data consumers to use the DynamoDB Streams API to detect new table entries and retrieve the data.
    - B. Create an Amazon Simple Notification Service (Amazon SNS) topic. Add code to the data producers, and publish notifications to the topic. Add code to the data consumers to subscribe to the topic.
    - C. Create an Amazon Simple Queue Service (Amazon SQS) queue. Add code to the data producers, and send data to the queue. Add code to the data consumers to process data from the queue.
    - D. Create an AWS Lambda function to pass messages. Add code to the data producers to call the Lambda function with a data object. Add code to the data consumers to receive a data object that is passed from the Lambda function.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

24. A company has a three-tier application for image sharing. The application uses an Amazon EC2 instance for the front-end layer, another EC2 instance for the application layer, and a third EC2 instance for a MySQL database. A solutions architect must design a scalable and highly available solution that requires the least amount of change to the application. Which solution meets these requirements?
    - A. Use load-balanced Multi-AZ AWS Elastic Beanstalk environments for the front-end layer and the application layer. Move the database to an Amazon RDS DB instance with multiple read replicas to serve users’ images.
    - B. Use Amazon S3 to host the front-end layer. Use AWS Lambda functions for the application layer. Move the database to an Amazon DynamoDB table. Use Amazon S3 to store and serve users’ images.
    - C. Use load-balanced Multi-AZ AWS Elastic Beanstalk environments for the front-end layer and the application layer. Move the database to an Amazon RDS Multi-AZ DB instance. Use Amazon S3 to store and serve users’ images.
    - D. Use Amazon S3 to host the front-end layer. Use a fleet of EC2 instances in an Auto Scaling group for the application layer. Move the database to a memory optimized instance type to store and serve users’ images.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

25. A company runs a global web application on Amazon EC2 instances behind an Application Load Balancer. The application stores data in Amazon Aurora. The company needs to create a disaster recovery solution and can tolerate up to 30 minutes of downtime and potential data loss. The solution does not need to handle the load when the primary infrastructure is healthy. What should a solutions architect do to meet these requirements?
    - A. Back up data with AWS Backup. Use the backup to create the required infrastructure in a second AWS Region. Use Amazon Route 53 to configure active-passive failover. Create an Aurora second primary instance in the second Region.
    - B. Replicate the primary infrastructure in a second AWS Region. Use Amazon Route 53 to configure active-active failover. Create an Aurora database that is restored from the latest snapshot.
    - C. Host a scaled-down deployment of the application in a second AWS Region. Use Amazon Route 53 to configure active-active failover. Create an Aurora Replica in the second Region.
    - D. Deploy the application with the required infrastructure elements in place. Use Amazon Route 53 to configure active-passive failover. Create an Aurora Replica in a second AWS Region.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

26. A media company collects and analyzes user activity data on premises. The company wants to migrate this capability to AWS. The user activity data store will continue to grow and will be petabytes in size. The company needs to build a highly available data ingestion solution that facilitates on-demand analytics of existing data and new data with SQL. Which solution will meet these requirements with the LEAST operational overhead?
    - A. Send activity data to an Amazon Kinesis data stream. Configure the stream to deliver the data to an Amazon S3 bucket.
    - B. Place activity data in an Amazon S3 bucket. Configure Amazon S3 to run an AWS Lambda function on the data as the data arrives in the S3 bucket.
    - C. Send activity data to an Amazon Kinesis Data Firehose delivery stream. Configure the stream to deliver the data to an Amazon Redshift cluster.
    - D. Create an ingestion service on Amazon EC2 instances that are spread across multiple Availability Zones. Configure the service to forward data to an Amazon RDS Multi-AZ database.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

27. A company manages its own Amazon EC2 instances that run MySQL databases. The company is manually managing replication and scaling as demand increases or decreases. The company needs a new solution that simplifies the process of adding or removing compute capacity to or from its database tier as needed. The solution also must offer improved performance, scaling, and durability with minimal effort from operations. Which solution meets these requirements? 
    - A. Combine the databases into one larger MySQL database. Run the larger database on larger EC2 instances.
    - B. Migrate the databases to Amazon Aurora Serverless for Aurora PostgreSQL.
    - C. Create an EC2 Auto Scaling group for the database tier. Migrate the existing databases to the new environment.
    - D. Migrate the databases to Amazon Aurora Serverless for Aurora MySQL.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

28. A company has a web application that is based on Java and PHP. The company plans to move the application from on premises to AWS. The company needs the ability to test new site features frequently. The company also needs a highly available and managed solution that requires minimum operational overhead. Which solution will meet these requirements?
    - A. Containerize the web application. Deploy the web application to Amazon EC2 instances. Use the AWS Load Balancer Controller to dynamically route traffic between containers that contain the new site features for testing.
    - B. Deploy the web application to Amazon EC2 instances that are configured with Java and PHP. Use Auto Scaling groups and an Application Load Balancer to manage the website’s availability.
    - C. Deploy the web application to an AWS Elastic Beanstalk environment. Use URL swapping to switch between multiple Elastic Beanstalk environments for feature testing.
    - D. Create an Amazon S3 bucket. Enable static web hosting on the S3 bucket. Upload the static content to the S3 bucket. Use AWS Lambda to process all dynamic content.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

29. A solutions architect is designing a new API using Amazon API Gateway that will receive requests from users. The volume of requests is highly variable; several hours can pass without receiving a single request. The data processing will take place asynchronously, but should be completed within a few seconds after a request is made. Which compute service should the solutions architect have the API invoke to deliver the requirements at the lowest cost?
    - A. A containerized service hosted in Amazon Elastic Kubernetes Service (Amazon EKS)
    - B. A containerized service hosted in Amazon ECS with Amazon EC2
    - C. An AWS Lambda function
    - D. An AWS Glue job

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

30. A company wants to experiment with individual AWS accounts for its engineer team. The company wants to be notified as soon as the Amazon EC2 instance usage for a given month exceeds a specific threshold for each account. What should a solutions architect do to meet this requirement MOST cost-effectively?
    - A. Use AWS Budgets to create a cost budget for each account. Set the period to monthly. Set the scope to EC2 instances. Set an alert threshold for the budget. Configure an Amazon Simple Notification Service (Amazon SNS) topic to receive a notification when a threshold is exceeded.
    - B. Use Cost Explorer to create a monthly report of costs by service. Filter the report by EC2 instances. Configure Cost Explorer to send an Amazon Simple Email Service (Amazon SES) notification when a threshold is exceeded.
    - C. Use AWS Cost and Usage Reports to create a report with hourly granularity. Integrate the report data with Amazon Athena. Use Amazon EventBridge to schedule an Athena query. Configure an Amazon Simple Notification Service (Amazon SNS) topic to receive a notification when a threshold is exceeded.
    - D. Use Cost Explorer to create a daily report of costs by service. Filter the report by EC2 instances. Configure Cost Explorer to send an Amazon Simple Email Service (Amazon SES) notification when a threshold is exceeded.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

31. A company is developing a marketing communications service that targets mobile app users. The company needs to send confirmation messages with Short Message Service (SMS) to its users. The users must be able to reply to the SMS messages. The company must store the responses for a year for analysis. What should a solutions architect do to meet these requirements?
    - A. Create an Amazon Simple Notification Service (Amazon SNS) FIFO topic. Subscribe an Amazon Kinesis data stream to the SNS topic for analysis and archiving.
    - B. Create an Amazon Connect contact flow to send the SMS messages. Use AWS Lambda to process the responses.
    - C. Build an Amazon Pinpoint journey. Configure Amazon Pinpoint to send events to an Amazon Kinesis data stream for analysis and archiving.
    - D. Use Amazon Simple Queue Service (Amazon SQS) to distribute the SMS messages. Use AWS Lambda to process the responses.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

32. A company hosts a marketing website in an on-premises data center. The website consists of static documents and runs on a single server. An administrator updates the website content infrequently and uses an SFTP client to upload new documents. The company decides to host its website on AWS and to use Amazon CloudFront. The company’s solutions architect creates a CloudFront distribution. The solutions architect must design the most cost-effective and resilient architecture for website hosting to serve as the CloudFront origin. Which solution will meet these requirements?
    - A. Create a public Amazon S3 bucket. Configure AWS Transfer for SFTP. Configure the S3 bucket for website hosting. Upload website content by using the SFTP client.
    - B. Create an AWS Auto Scaling group for Amazon EC2 instances. Use an Application Load Balancer. Upload website content by using an SFTP client.
    - C. Create a virtual server by using Amazon Lightsail. Configure the web server in the Lightsail instance. Upload website content by using an SFTP client.
    - D. Create a private Amazon S3 bucket. Use an S3 bucket policy to allow access from a CloudFront origin access identity (OAI). Upload website content by using the AWS CLI.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

33. A company has a serverless website with millions of objects in an Amazon S3 bucket. The company uses the S3 bucket as the origin for an Amazon CloudFront distribution. The company did not set encryption on the S3 bucket before the objects were loaded. A solutions architect needs to enable encryption for all existing objects and for all objects that are added to the S3 bucket in the future. Which solution will meet these requirements with the LEAST amount of effort?
    - A. Create a new S3 bucket. Turn on the default encryption settings for the new S3 bucket. Download all existing objects to temporary local storage. Upload the objects to the new S3 bucket.
    - B. Create a new encryption key by using AWS Key Management Service (AWS KMS). Change the settings on the S3 bucket to use server-side encryption with AWS KMS managed encryption keys (SSE-KMS). Turn on versioning for the S3 bucket.
    - C. Navigate to Amazon S3 in the AWS Management Console. Browse the S3 bucket’s objects. Sort by the encryption field. Select each unencrypted object. Use the Modify button to apply default encryption settings to every unencrypted object in the S3 bucket.
    - D. Turn on the default encryption settings for the S3 bucket. Use the S3 Inventory feature to create a .csv file that lists the unencrypted objects. Run an S3 Batch Operations job that uses the copy command to encrypt those objects.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

34. A company needs to move data from an Amazon EC2 instance to an Amazon S3 bucket. The company must ensure that no API calls and no data are routed through public internet routes. Only the EC2 instance can have access to upload data to the S3 bucket. Which solution will meet these requirements? 
    - A. Create a gateway VPC endpoint for Amazon S3 in the Availability Zone where the EC2 instance is located. Attach appropriate security groups to the endpoint. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
    - B. Use the AWS provided, publicly available ip-ranges.json file to obtain the private IP address of the S3 bucket’s service API endpoint. Create a route in the VPC route table to provide the EC2 instance with access to the S3 bucket. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
    - C. Run the nslookup tool from inside the EC2 instance to obtain the private IP address of the S3 bucket’s service API endpoint. Create a route in the VPC route table to provide the EC2 instance with access to the S3 bucket. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.
    - D. Create an interface VPC endpoint for Amazon S3 in the subnet where the EC2 instance is located. Attach a resource policy to the S3 bucket to only allow the EC2 instance’s IAM role for access.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

35. A company needs to export its database once a day to Amazon S3 for other teams to access. The exported object size varies between 2 GB and 5 GB. The S3 access pattern for the data is variable and changes rapidly. The data must be immediately available and must remain accessible for up to 3 months. The company needs the most cost-effective solution that will not increase retrieval time. Which S3 storage class should the company use to meet these requirements? 
    - A. S3 Standard
    - B. S3 Intelligent-Tiering 
    - C. S3 Glacier Instant Retrieval
    - D. S3 Standard-Infrequent Access (S3 Standard-IA)

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

36. A company is moving its on-premises Oracle database to Amazon Aurora PostgreSQL. The
database has several applications that write to the same tables. The applications need to be
migrated one by one with a month in between each migration. Management has expressed
concerns that the database has a high number of reads and writes. The data must be kept
in sync across both databases throughout the migration. What should a solutions architect
recommend?
    - A. Use AWS DataSync for the initial migration. Use AWS Database Migration Service (AWS DMS) to create a change data capture (CDC) replication task and a table mapping to select all tables.
    - B. Use the AWS Schema Conversion Tool with AWS Database Migration Service (AWS DMS) using a compute optimized replication instance. Create a full load plus change data capture (CDC) replication task and a table mapping to select the largest tables.
    - C. Use the AWS Schema Conversion Tool with AWS Database Migration Service (AWS DMS) using a memory optimized replication instance. Create a full load plus change data capture (CDC) replication task and a table mapping to select all tables.
    - D. Use AWS DataSync for the initial migration. Use AWS Database Migration Service (AWS DMS) to create a full load plus change data capture (CDC) replication task and a table mapping to select all tables.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

37. A company needs to store contract documents. A contract lasts for 5 years. During the 5-
year period, the company must ensure that the documents cannot be overwritten or
deleted. The company needs to encrypt the documents at rest and rotate the encryption
keys automatically every year. Which combination of steps should a solutions architect
take to meet these requirements with the LEAST operational overhead? (**Choose two.**)
    - A. Use server-side encryption with Amazon S3 managed encryption keys (SSES3). Configure key rotation.
    - B. Store the documents in Amazon S3. Use S3 Object Lock in compliance mode.
    - C. Use server-side encryption with AWS Key Management Service (AWS KMS) customer provided (imported) keys. Configure key rotation.
    - D. Store the documents in Amazon S3. Use S3 Object Lock in governance mode.
    - E. Use server-side encryption with AWS Key Management Service (AWS KMS) customer managed keys. Configure key rotation.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, E
    </details>

38. A company runs a containerized application on a Kubernetes cluster in an on-premises
data center. The company is using a MongoDB database for data storage. The company
wants to migrate some of these environments to AWS, but no code changes or deployment
method changes are possible at this time. The company needs a solution that minimizes
operational overhead. Which solution meets these requirements?
    - A. Use Amazon Elastic Container Service (Amazon ECS) with AWS Fargate for compute and Amazon DynamoDB for data storage
    - B. Use Amazon Elastic Kubernetes Service (Amazon EKS) with AWS Fargate for compute and Amazon DocumentDB (with MongoDB compatibility) for data storage.
    - C. Use Amazon Elastic Container Service (Amazon ECS) with Amazon EC2 worker nodes for compute and MongoDB on EC2 for data storage.
    - D. Use Amazon Elastic Kubernetes Service (Amazon EKS) with Amazon EC2 worker nodes for compute and Amazon DynamoDB for data storage.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

39. A company is planning to move its data to an Amazon S3 bucket. The data must be encrypted when it is stored in the S3 bucket. Additionally, the encryption key must be automatically rotated every year. Which solution will meet these requirements with the LEAST operational overhead? 
    - A. Create an AWS Key Management Service (AWS KMS) customer managed key. Enable automatic key rotation. Set the S3 bucket’s default encryption behavior to use the customer managed KMS key. Move the data to the S3 bucket.
    - B. Encrypt the data with customer key material before moving the data to the S3 bucket. Create an AWS Key Management Service (AWS KMS) key without key material. Import the customer key material into the KMS key. Enable automatic key rotation.
    - C. Move the data to the S3 bucket. Use server-side encryption with Amazon S3 managed encryption keys (SSE-S3). Use the built-in key rotation behavior of SSE-S3 encryption keys.
    - D. Create an AWS Key Management Service (AWS KMS) customer managed key. Set the S3 bucket’s default encryption behavior to use the customer managed KMS key. Move the data to the S3 bucket. Manually rotate the KMS key every year.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

40. A company has a web server running on an Amazon EC2 instance in a public subnet with
an Elastic IP address. The default security group is assigned to the EC2 instance. The
default network ACL has been modified to block all traffic. A solutions architect needs to
make the web server accessible from everywhere on port 443. Which combination of steps
will accomplish this task? (**Choose two.**)
    - A. Update the network ACL to allow inbound/outbound TCP port 443 from source 0.0.0.0/0 and to destination 0.0.0.0/0.
    - B. Update the network ACL to allow inbound TCP port 443 from source 0.0.0.0/0 and outbound TCP port 32768-65535 to destination 0.0.0.0/0.
    - C. Create a security group with a rule to allow TCP port 443 to destination 0.0.0.0/0.
    - D. Update the network ACL to allow TCP port 443 from source 0.0.0.0/0.
    - E. Create a security group with a rule to allow TCP port 443 from source 0.0.0.0/0.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B, E
    </details>

41. The customers of a finance company request appointments with financial advisors by
sending text messages. A web application that runs on Amazon EC2 instances accepts the
appointment requests. The text messages are published to an Amazon Simple Queue
Service (Amazon SQS) queue through the web application. Another application that runs
on EC2 instances then sends meeting invitations and meeting confirmation email messages
to the customers. After successful scheduling, this application stores the meeting
information in an Amazon DynamoDB database. As the company expands, customers
report that their meeting invitations are taking longer to arrive. What should a solutions
architect recommend to resolve this issue?
    - A. Add an Amazon CloudFront distribution. Set the origin as the web application that accepts the appointment requests.
    - B. Add an Auto Scaling group for the application that sends meeting invitations. Configure the Auto Scaling group to scale based on the depth of the SQS queue.
    - C. Add an Amazon API Gateway API in front of the web application that accepts the appointment requests.
    - D. Add a DynamoDB Accelerator (DAX) cluster in front of the DynamoDB database.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

42. A company is developing an ecommerce application that will consist of a load-balanced
front end, a container-based application, and a relational database. A solutions architect
needs to create a highly available solution that operates with as little manual intervention
as possible. Which solutions meet these requirements? (**Choose two.**)
    - A. Create an Amazon Elastic Container Service (Amazon ECS) cluster with an Amazon EC2 launch type to handle the dynamic application load.
    - B. Create an Amazon EC2 instance-based Docker cluster to handle the dynamic application load.
    - C. Create an Amazon RDS DB instance in Multi-AZ mode.
    - D. Create an Amazon RDS DB instance and one or more replicas in another Availability Zone.
    - E. Create an Amazon Elastic Container Service (Amazon ECS) cluster with a Fargate launch type to handle the dynamic application load.
      
    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C, E
    </details>

43. A company has an ordering application that stores customer information in Amazon RDS
for MySQL. During regular business hours, employees run one-time queries for reporting
purposes. Timeouts are occurring during order processing because the reporting queries
are taking a long time to run. The company needs to eliminate the timeouts without
preventing employees from performing queries. What should a solutions architect do to
meet these requirements?
    - A. Create a read replica. Distribute the ordering application to the primary DB instance and the read replica.
    - B. Create a read replica. Move reporting queries to the read replica.
    - C. Migrate the ordering application to Amazon DynamoDB with on-demand capacity.
    - D. Schedule the reporting queries for non-peak hours.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

44. An application running on an Amazon EC2 instance in VPC-A needs to access files in
another EC2 instance in VPC-B. Both VPCs are in separate AWS accounts. The network
administrator needs to design a solution to configure secure access to EC2 instance in VPCB
from VPC-A. The connectivity should not have a single point of failure or bandwidth
concerns. Which solution will meet these requirements?
    - A.  Attach a virtual private gateway to VPC-B and set up routing from VPC-A.
    - B. Set up a VPC peering connection between VPC-A and VPC-B. 
    - C. Create a private virtual interface (VIF) for the EC2 instance running in VPC-B and add appropriate routes from VPC-A.
    - D. Set up VPC gateway endpoints for the EC2 instance running in VPC-B.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

45. A company has an API that receives real-time data from a fleet of monitoring devices. The API stores this data in an Amazon RDS DB instance for later analysis. The amount of data that the monitoring devices send to the API fluctuates. During periods of heavy traffic, the API often returns timeout errors. After an inspection of the logs, the company determines that the database is not capable of processing the volume of write traffic that comes from the API. A solutions architect must minimize the number of connections to the database and must ensure that data is not lost during periods of heavy traffic. Which solution will meet these requirements?
    - A. Modify the API to write incoming data to an Amazon Simple Queue Service (Amazon SQS) queue. Use an AWS Lambda function that Amazon SQS invokes to write data from the queue to the database. 
    - B. Modify the DB instance to be a Multi-AZ DB instance. Configure the application to write to all active RDS DB instances.
    - C. Modify the API to write incoming data to an Amazon Simple Notification Service (Amazon SNS) topic. Use an AWS Lambda function that Amazon SNS invokes to write data from the topic to the database.
    - D. Increase the size of the DB instance to an instance type that has more available memory.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

46. A company runs an application on a large fleet of Amazon EC2 instances. The application reads and writes entries into an Amazon DynamoDB table. The size of the DynamoDB table continuously grows, but the application needs only data from the last 30 days. The company needs a solution that minimizes cost and development effort. Which solution meets these requirements? 
    - A. Extend the application to add an attribute that has a value of the current timestamp plus 30 days to each new item that is created in the table. Configure DynamoDB to use the attribute as the TTL attribute.
    - B. Use an AWS CloudFormation template to deploy the complete solution. Redeploy the CloudFormation stack every 30 days, and delete the original stack.
    - C. Use an EC2 instance that runs a monitoring application from AWS Marketplace. Configure the monitoring application to use Amazon DynamoDB Streams to store the timestamp when a new item is created in the table. Use a script that runs on the EC2 instance to delete items that have a timestamp that is older than 30 days.
    - D. Configure Amazon DynamoDB Streams to invoke an AWS Lambda function when a new item is created in the table. Configure the Lambda function to delete items in the table that are older than 30 days.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

47. A telemarketing company is designing its customer call center functionality on AWS. The company needs a solution that provides multiple speaker recognition and generates transcript files. The company wants to query the transcript files to analyze the business patterns. The transcript files must be stored for 7 years for auditing purposes. Which solution will meet these requirements?
    - A. Use Amazon Rekognition for multiple speaker recognition. Store the transcript files in Amazon S3. Use Amazon Textract for transcript file analysis.
    - B. Use Amazon Rekognition for multiple speaker recognition. Store the transcript files in Amazon S3. Use machine learning models for transcript file analysis.
    - C. Use Amazon Transcribe for multiple speaker recognition. Use Amazon Athena for transcript file analysis. 
    - D. Use Amazon Translate for multiple speaker recognition. Store the transcript files in Amazon Redshift. Use SQL queries for transcript file analysis.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

48. A company owns an asynchronous API that is used to ingest user requests and, based on the request type, dispatch requests to the appropriate microservice for processing. The company is using Amazon API Gateway to deploy the API front end, and an AWS Lambda function that invokes Amazon DynamoDB to store user requests before dispatching them to the processing microservices. The company provisioned as much DynamoDB throughput as its budget allows, but the company is still experiencing availability issues and is losing user requests. What should a solutions architect do to address this issue without impacting existing users?
    - A. Create a secondary index in DynamoDB for the table with the user requests.
    - B. Add throttling on the API Gateway with server-side throttling limits.
    - C. Use the Amazon Simple Queue Service (Amazon SQS) queue and Lambda to buffer writes to DynamoDB.
    - D. Use DynamoDB Accelerator (DAX) and Lambda to buffer writes to DynamoDB.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

49. A company wants to manage Amazon Machine Images (AMIs). The company currently copies AMIs to the same AWS Region where the AMIs were created. The company needs to design an application that captures AWS API calls and sends alerts whenever the Amazon EC2 CreateImage API operation is called within the company’s account. Which solution will meet these requirements with the LEAST operational overhead? 
    - A. Create an Amazon EventBridge (Amazon CloudWatch Events) rule for the CreateImage API call. Configure the target as an Amazon Simple Notification Service (Amazon SNS) topic to send an alert when a CreateImage API call is detected.
    - B. Create an AWS Lambda function to query AWS CloudTrail logs and to send an alert when a CreateImage API call is detected.
    - C. Configure AWS CloudTrail with an Amazon Simple Notification Service (Amazon SNS) notification that occurs when updated logs are sent to Amazon S3. Use Amazon Athena to create a new table and to query on CreateImage when an API call is detected.
    - D. Configure an Amazon Simple Queue Service (Amazon SQS) FIFO queue as a target for AWS CloudTrail logs. Create an AWS Lambda function to send an alert to an Amazon Simple Notification Service (Amazon SNS) topic when a CreateImage API call is detected.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

50. A solutions architect needs to design a new microservice for a company’s application. Clients must be able to call an HTTPS endpoint to reach the microservice. The microservice also must use AWS Identity and Access Management (IAM) to authenticate calls. The solutions architect will write the logic for this microservice by using a single AWS Lambda function that is written in Go 1.x. Which solution will deploy the function in the MOST operationally efficient way? 
    - A. Create an Amazon CloudFront distribution. Deploy the function to Lambda@Edge. Integrate IAM authentication logic into the Lambda@Edge function.
    - B. Create an Amazon CloudFront distribution. Deploy the function to CloudFront Functions. Specify AWS_IAM as the authentication type.
    - C. Create a Lambda function URL for the function. Specify AWS_IAM as the authentication type.
    - D. Create an Amazon API Gateway REST API. Configure the method to use the Lambda function. Enable IAM authentication on the API.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

51. A company has 700 TB of backup data stored in network attached storage (NAS) in its data center. This backup data need to be accessible for infrequent regulatory requests and must be retained 7 years. The company has decided to migrate this backup data from its data center to AWS. The migration must be complete within 1 month. The company has 500 Mbps of dedicated bandwidth on its public internet connection available for data transfer. What should a solutions architect do to migrate and store the data at the LOWEST cost? 
    - A. Provision a 500 Mbps AWS Direct Connect connection and transfer the data to Amazon S3. Use a lifecycle policy to transition the files to Amazon S3 Glacier Deep Archive.
    - B. Use AWS DataSync to transfer the data and deploy a DataSync agent on premises. Use the DataSync task to copy files from the on-premises NAS storage to Amazon S3 Glacier.
    - C. Order AWS Snowball devices to transfer the data. Use a lifecycle policy to transition the files to Amazon S3 Glacier Deep Archive.
    - D. Deploy a VPN connection between the data center and Amazon VPC. Use the AWS CLI to copy the data from on premises to Amazon S3 Glacier.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

52. A company has a Windows-based application that must be migrated to AWS. The application requires the use of a shared Windows file system attached to multiple Amazon EC2 Windows instances that are deployed across multiple Availability Zone: What should a solutions architect do to meet this requirement?
    - A. Configure an Amazon Elastic Block Store (Amazon EBS) volume with the required size. Attach each EC2 instance to the volume. Mount the file system within the volume to each Windows instance.
    - B. Configure a file system by using Amazon Elastic File System (Amazon EFS). Mount the EFS file system to each Windows instance.
    - C. Configure AWS Storage Gateway in volume gateway mode. Mount the volume to each Windows instance.
    - D. Configure Amazon FSx for Windows File Server. Mount the Amazon FSx file system to each Windows instance.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

53. A company’s order system sends requests from clients to Amazon EC2 instances. The EC2 instances process the orders and then store the orders in a database on Amazon RDS. Users report that they must reprocess orders when the system fails. The company wants a resilient solution that can process orders automatically if a system outage occurs. What should a solutions architect do to meet these requirements?
    - A. Move the EC2 instances into an Auto Scaling group. Configure the order system to send messages to an Amazon Simple Queue Service (Amazon SQS) queue. Configure the EC2 instances to consume messages from the queue.
    - B. Move the EC2 instances into an Auto Scaling group behind an Application Load Balancer (ALB). Update the order system to send messages to the ALB endpoint.
    - C. Create an Amazon Simple Notification Service (Amazon SNS) topic. Create an AWS Lambda function, and subscribe the function to the SNS topic. Configure the order system to send messages to the SNS topic. Send a command to the EC2 instances to process the messages by using AWS Systems Manager Run Command.
    - D. Move the EC2 instances into an Auto Scaling group. Create an Amazon EventBridge (Amazon CloudWatch Events) rule to target an Amazon Elastic Container Service (Amazon ECS) task.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

54. A company previously migrated its data warehouse solution to AWS. The company also has an AWS Direct Connect connection. Corporate office users query the data warehouse using a visualization tool. The average size of a query returned by the data warehouse is 50
MB and each webpage sent by the visualization tool is approximately 500 KB. Result sets returned by the data warehouse are not cached. Which solution provides the LOWEST data transfer egress cost for the company? 
    - A. Host the visualization tool in the same AWS Region as the data warehouse and access it over a Direct Connect connection at a location in the same Region.
    - B. Host the visualization tool on premises and query the data warehouse directly over a Direct Connect connection at a location in the same AWS Region.
    - C. Host the visualization tool on premises and query the data warehouse directly over the internet.
    - D. Host the visualization tool in the same AWS Region as the data warehouse. Access it over the internet.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

55. An application runs on an Amazon EC2 instance that has an Elastic IP address in VPC A. The application requires access to a database in VPC B. Both VPCs are in the same AWS account. Which solution will provide the required access MOST securely?
    - A. Create a DB instance security group that allows all traffic from the public IP address of the application server in VPC A.
    - B. Launch an EC2 instance with an Elastic IP address into VPC B. Proxy all requests through the new EC2 instance.
    - C. Make the DB instance publicly accessible. Assign a public IP address to the DB instance.
    - D. Configure a VPC peering connection between VPC A and VPC B.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: D
    </details>

56. A company has hired an external vendor to perform work in the company’s AWS account. The vendor uses an automated tool that is hosted in an AWS account that the vendor owns. The vendor does not have IAM access to the company’s AWS account. How should a solutions architect grant this access to the vendor?
    - A. Create a new identity provider by choosing “AWS account” as the provider type in the IAM console. Supply the vendor’s AWS account ID and user name. Attach the appropriate IAM policies to the new provider for the permissions that the vendor requires.
    - B. Create an IAM user in the company’s account with a password that meets the password complexity requirements. Attach the appropriate IAM policies to the user for the permissions that the vendor requires.
    - C. Create an IAM role in the company’s account to delegate access to the vendor’s IAM role. Attach the appropriate IAM policies to the role for the permissions that the vendor requires. 
    - D. Create an IAM group in the company’s account. Add the tool’s IAM user from the vendor account to the group. Attach the appropriate IAM policies to the group for the permissions that the vendor requires.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: C
    </details>

57. A company needs to retain its AWS CloudTrail logs for 3 years. The company is enforcing CloudTrail across a set of AWS accounts by using AWS Organizations from the parent account. The CloudTrail target S3 bucket is configured with S3 Versioning enabled. An S3 Lifecycle policy is in place to delete current objects after 3 years. After the fourth year of use of the S3 bucket, the S3 bucket metrics show that the number of objects has continued to rise. However, the number of new CloudTrail logs that are delivered to the S3 bucket has remained consistent. Which solution will delete objects that are older than 3 years in the MOST cost-effective manner?
    - A. Configure the parent account as the owner of all objects that are delivered to the S3 bucket.
    - B. Configure the S3 Lifecycle policy to delete previous versions as well as current versions. 
    - C. Configure the organization’s centralized CloudTrail trail to expire objects after 3 years.
    - D. Create an AWS Lambda function to enumerate and delete objects from Amazon S3 that are older than 3 years.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: B
    </details>

58. A company is building a new dynamic ordering website. The company wants to minimize server maintenance and patching. The website must be highly available and must scale read and write capacity as quickly as possible to meet changes in user demand. Which solution will meet these requirements? 
    - A. Host static content in Amazon S3. Host dynamic content by using Amazon API Gateway and AWS Lambda. Use Amazon DynamoDB with on-demand capacity for the database. Configure Amazon CloudFront to deliver the website content.
    - B. Host all the website content on Amazon EC2 instances. Create an Auto Scaling group to scale the EC2 instances. Use an Application Load Balancer to distribute traffic. Use Amazon Aurora with Aurora Auto Scaling for the database.
    - C. Host static content in Amazon S3. Host dynamic content by using Amazon API Gateway and AWS Lambda. Use Amazon Aurora with Aurora Auto Scaling for the database. Configure Amazon CloudFront to deliver the website content.
    - D. Host all the website content on Amazon EC2 instances. Create an Auto Scaling group to scale the EC2 instances. Use an Application Load Balancer to distribute traffic. Use Amazon DynamoDB with provisioned write capacity for the database.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A
    </details>

59. A company has deployed a Java Spring Boot application as a pod that runs on Amazon
Elastic Kubernetes Service (Amazon EKS) in private subnets. The application needs to
write data to an Amazon DynamoDB table. A solutions architect must ensure that the
application can interact with the DynamoDB table without exposing traffic to the internet.
Which combination of steps should the solutions architect take to accomplish this goal?
(**Choose two.**)
    - A. Create a VPC endpoint for DynamoDB.
    - B. Attach an IAM role that has sufficient privileges to the EKS pod.
    - C. Allow outbound connectivity to the DynamoDB table through the private subnets’ network ACLs.
    - D. Embed the access keys in the Java Spring Boot code.
    - E. Attach an IAM user that has sufficient privileges to the EKS pod.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, B
    </details>

60. A company recently migrated its web application to AWS by rehosting the application on
Amazon EC2 instances in a single AWS Region. The company wants to redesign its
application architecture to be highly available and fault tolerant. Traffic must reach all
running EC2 instances randomly. Which combination of steps should the company take to
meet these requirements? (**Choose two.**)
    - A. Launch four EC2 instances: two instances in one Availability Zone and two instances in another Availability Zone.
    - B. Launch three EC2 instances: two instances in one Availability Zone and one instance in another Availability Zone.
    - C. Create an Amazon Route 53 failover routing policy.
    - D. Create an Amazon Route 53 multivalue answer routing policy.
    - E. Create an Amazon Route 53 weighted routing policy.

    <details markdown=1><summary markdown='span'>Answer</summary>
      Correct answer: A, D
    </details>



