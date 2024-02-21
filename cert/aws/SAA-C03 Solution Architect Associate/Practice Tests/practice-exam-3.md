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


Please feel free to comment below if any information is inaccurate or if any answers need correction.


