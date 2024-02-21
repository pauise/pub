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

11. 

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


