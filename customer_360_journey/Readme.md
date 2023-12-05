# High Level System Landscape

A high level simplified diagram of the customer data platform. 

![context](/resources/Logical%20Diagram.jpg)
# Data Sources
Data is produced from different systems, SAAS applications, social media etc in variety of formats.

# Data Hub
The data produced by the data sources is published to the data hub for different systems to consume.

1. **Data ingestion and integration:** Data flows into AWS through batch processing,
real-time data and Secure File Transfer Protocol.
- AWS Transfer Family - Easily manage and share data with simple, secure, and scalable file transfers
- AWS Eventbridge - is a serverless service that ingests events from own apps, SAAS application etc. It can also schedule data sync or pull events from supported sources.
- AWS Kinesis - is a serverless streaming data service that simplifies the capture, processing, and storage of data streams
- AWS Data exchange - is a service that can easily find, subscribe to, and use third-party data in the cloud

2. **Producer Domain Accounts:** Data sources are managed by the Business Domain. Producers use organization-level blueprints to provide core services such as security, governance, and open standards.
- Operational Data Store is built using Amazon DynamoDB and Amazon DynamoDB Accelerator (DAX) to provide consistent singledigit-millisecond latency performance. The data is published using lambda and API gateway to consumers. DynamoDB data streams along with kinesis can be used to publish events to listening applications.
- Entity resolution if required is done in the producer domain using AWS Entity Resolution.

3. **Central IT Platform:** AWS Lake Formation provides centralized management of security, governance and auditing policies including fine-grain permissions. It also enables automatic schema discovery and conversion to the required format.

    **Metadata:** Metadata is managed via multiple services. AWS Glue is used for data cataloguing. Data lineage is stored in Amazon Neptune. Data contracts are stored in DynamoDB.

    **Governance:** Data governance can be done by the multiple servies like AWS CloudTrail to record API calls for auditing and compliance monitoring, Amazon CloudWatch for monitoring services for metrics and log files and AWS  CloudFormation to enforce enforcing governance policies.

    **Security & Access Management Services:** Security and access management can be achieved using multiple services provided by AWS. These services provide key and secrets managements, access management, privacy management, threat detection, vulnerability mangement etc.

    **Discovery:** AWS services like Athena, Glue Crawler and Data Quality are used for auto-discovery of metadata of services and asseses the data quality.

4. **Account - Machine Learning:**ML (Machine Learning) is performed using Lake Formation. Use Amazon SageMaker to provide standard AI/ML models for customer segmentations, lifetime value and sentiment analysis. Other AI services such as Amazon Personalize can be utilized to get actionable insight.

5. **Consumer Account - Business Analytics Domain:** Build all reportable data sets in Amazon S3 and leverage Amazon Redshift and Amazon Athena for analytics. Optionally, for heavily used analytics, build data marts in Amazon Redshift.For ad-hoc requirements, use Athena to analyse data in the data lake with standard SQL.
