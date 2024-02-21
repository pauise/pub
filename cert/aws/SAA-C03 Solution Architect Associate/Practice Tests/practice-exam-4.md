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

31. 

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


