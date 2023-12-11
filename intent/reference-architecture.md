<!-- TOC -->

- [Reference architecture for a operational system](#reference-architecture-for-a-operational-system)
    - [Key Components](#key-components)
        - [Route 53](#route-53)
        - [CloudFront](#cloudfront)
        - [Amazon Cognito](#amazon-cognito)
        - [Amazon S3](#amazon-s3)
        - [API Gateway](#api-gateway)
        - [Load Balancer](#load-balancer)
        - [AWS Fargate](#aws-fargate)
        - [Amazon Aurora](#amazon-aurora)
        - [ElastiCache](#elasticache)
        - [DynamoDB](#dynamodb)
        - [Kinesis](#kinesis)
- [Reference architecture for a data product](#reference-architecture-for-a-data-product)
- [Deployment architecture](#deployment-architecture)

<!-- /TOC -->

# Reference architecture for a operational system
The reference architecture for microservices is provided below. Operational systems can follow the below guidance.
Optionally Fargate can be replaced by Lambda if required.
![microservice reference architecture](/resources/microservice-reference-architecture.jpg)

## Key Components

### 1. Route 53

- **Intent:** Route 53 will be used for domain registration and DNS management, providing reliable and scalable routing to the web application.

### 2. CloudFront

- **Intent:** CloudFront will act as a content delivery network (CDN) to distribute static and dynamic content globally, reducing latency and enhancing the user experience.

### 3. Amazon Cognito

- **Intent:** Cognito will be employed for secure user authentication and authorization. It will manage user pools and federate identities across multiple identity providers.

### 4. Amazon S3

- **Intent:** S3 will serve as a scalable and cost-effective storage solution for static content, such as images, stylesheets, and client-side scripts.

### 5. API Gateway

- **Intent:** API Gateway will be used to create, publish, and manage APIs securely. It will facilitate communication between client applications and backend services.

### 6. Load Balancer

- **Intent:** A Load Balancer (e.g., AWS Application Load Balancer) will distribute incoming web traffic across multiple Fargate containers, ensuring high availability, fault tolerance, and efficient resource utilization.

### 7. AWS Fargate

- **Intent:** Fargate will host containerized applications, providing a serverless computing environment. It allows for easy deployment, scaling, and management of application containers without the need to manage the underlying infrastructure.

### 8. Amazon Aurora

- **Intent:** Aurora will serve as a highly available and scalable relational database, ensuring data consistency, durability, and high performance for the web application.

### 9. ElastiCache

- **Intent:** ElastiCache (e.g., Redis) will be used for caching frequently accessed data, reducing database load and improving application responsiveness.

### 10. DynamoDB

- **Intent:** DynamoDB will be utilized as a NoSQL database for flexible and scalable storage of non-relational data.

### 11. Kinesis

- **Intent:** Kinesis will be used for real-time data streaming and analytics, allowing the system to process and analyze data in near real-time.

## Security Considerations

1. **IAM Roles and Policies:** Define IAM roles with the principle of least privilege for microservices, Step Functions, and Lambda functions.

2. **Encryption:** Enable encryption at rest and in transit for sensitive data, such as compensation details and documents.

3. **Access Controls:** Implement proper access controls on S3 buckets, DynamoDB tables, and other resources to restrict unauthorized access.

## Monitoring and Logging

1. **CloudWatch Metrics and Alarms:** Monitor and set up alarms for key metrics such as Step Functions execution times, Fargate task failures, and Lambda invocations.

2. **CloudTrail:** Enable AWS CloudTrail for auditing and logging AWS API calls for compliance and security purposes.

3. **Logging Services:** Utilize CloudWatch Logs and centralized logging solutions to aggregate and analyze logs from microservices and Lambda functions.


# Reference architecture for a data product
The below is a reference architecture for a data product. This new to build a data platform that serves both operational and analytical needs by using domain owned design, maintained data properties, open data standards, purpose-built databases, and extensible serverless architecture. This data delivery platform architecture helps relieve and eventually replace the on-premises data platform load, leading to cost savings and an agile environment.

**Logical architecture**
![domain architecture](/resources/domain-architecture.png)

**Reference implementation**
![Reference Implementation](/resources/domain-architecture-ref-implementation.jpg)
1. Data flows into AWS through batch processing,
real-time data, Secure File Transfer Protocol, event streams.
2. Data sources are managed by the Business Domain. Producers use organization-level blueprints to provide core services such as
security, governance, and open standards.Producers build the Operational Data Store using Amazon DynamoDB and Amazon DynamoDB
Accelerator (DAX) to provide consistent single digit-millisecond latency performance.
3. An AWS Glue crawler creates the table metadata in the data catalog. The AWS Glue data catalog is an index of the location, schema, and runtime metrics of your data. Use the information in the data catalog to create and monitor your ETL (extract, transform, and load) jobs.
4. Use purpose-built databases such as Amazon DynamoDB and serverless architecture to deliver microservices and events to the operational data
store.
5. Build all reportable data sets in Amazon S3 and this can be shared using Lakeformation.

## Security Considerations

1. **IAM Roles and Policies:** Define IAM roles with the principle of least privilege for microservices, Step Functions, and Lambda functions.

2. **Encryption:** Enable encryption at rest and in transit for sensitive data, such as compensation details and documents.

3. **Access Controls:** Implement proper access controls on S3 buckets, DynamoDB tables, and other resources to restrict unauthorized access.

## Monitoring and Logging

1. **CloudWatch Metrics and Alarms:** Monitor and set up alarms for key metrics such as Step Functions execution times, Fargate task failures, and Lambda invocations.

2. **CloudTrail:** Enable AWS CloudTrail for auditing and logging AWS API calls for compliance and security purposes.

3. **Logging Services:** Utilize CloudWatch Logs and centralized logging solutions to aggregate and analyze logs from microservices and Lambda functions.


# Deployment architecture
- All the services are deployed on three availability zones in the same region. 
- [Pilot light](/ADR/dr-strategy.md) for DR will be used across multiple regions
- Separate accounts will be used for different business units

