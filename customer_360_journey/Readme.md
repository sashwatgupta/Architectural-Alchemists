# High Level System Landscape

## Objective
Design a customer management platform that enables the foundation of data-driven, customer centric organisation.

## Solution Vision
To provide a solution to the above statement we need an architecture that can provide agility to the organisation. The solution should empower systems/teams to get the customer 360 view and share data easily.

Our vision for the data architecture of our organization is centered around the principles of Data Mesh [ADR link- TODO], an approach that promotes decentralization and domain-oriented thinking. This visionary architecture aims to transform our data landscape, empowering teams, improving agility, and fostering a culture of data-driven innovation.

## Logical Architecture Data Mesh

The objective for this design is to create a foundation for building data platforms at scale, supporting the objectives of data producers and consumers with strong and consistent governance.

![simple](/resources/data-mesh-dets1.png)

Major components of the data mesh are:

1. Data Domain - is responsible for creating, owning, and managing specific data domains. Key responsibilities include:
    - Domain Ownership:Manages and owns data within a specific business domain.
    - Data Product Creation:Defines and creates valuable data products within the domain.
    - Data Quality Assurance: Ensures high data quality through checks and adherence to contracts.
    - APIs and Contracts: Defines clear APIs and contracts for seamless interaction.
    - Publishing and Discovery: Publishes data products for consumption by other parts of the organization.
    - Autonomous Decision-Making:Has autonomy in domain-related decisions to foster innovation.
    - Monitoring and Observability:Implements monitoring for performance, usage, and quality.
    - Collaboration:Collaborates with Data Consumers to meet their data needs.

    There are three types of domains classified by data characteristics and data product usage:-
    - Source-aligned - publish data products correspond closely to the domain events and entities generated in their operational systems.
    - Aggregate -  focuses solely on delivering a data product that is aggregated of various data products from other domains
    - Consumer-aligned -  business departments that need data from the whole value stream to make sensible decisions, emphasizes the alignment of data domains with the needs and requirements of specific consumer groups
![Data mesh domains](/resources/data-mesh-domain.jpg)

2. Central Governance -     The central data governance account serves as a hub for managing a comprehensive data catalog that spans all enterprise accounts. Key responsibilities include:
    - Stores a comprehensive data catalog covering all enterprise data across accounts.
    - Allows data producers to register and create catalog entries seamlessly 
    - Contains only logs; no actual data is stored in this account.
    - Centrally defines and manages security, governance, and auditing policies
    - Provides centralized access control for enterprise-wide data sharing.
    - Ensures that security, governance, and auditing policies are consistently applied across shared data.

## Solution Context

A high level simplified diagram of the customer data platform. 

![context](/resources/Logical%20Diagram.jpg)
1. **Data Sources:** Data is produced from different systems, SAAS applications, social media etc in variety of formats.

1. **Data ingestion and integration:** Data flows into AWS through batch processing, real-time data and Secure File Transfer Protocol.
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

4. **Account - Machine Learning:** ML (Machine Learning) is performed using Lake Formation. Use Amazon SageMaker to provide standard AI/ML models for customer segmentations, lifetime value and sentiment analysis. Other AI services such as Amazon Personalize can be utilized to get actionable insight and personalisation. 

5. **Account - Business Analytics Domain:** Build all reportable data sets in Amazon S3 and leverage Amazon Redshift and Amazon Athena for analytics. Optionally, for heavily used analytics, build data marts in Amazon Redshift.For ad-hoc requirements, use Athena to analyse data in the data lake with standard SQL.
