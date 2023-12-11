<!-- TOC -->

- [Objective](#objective)
- [Solution Context](#solution-context)
- [Logical Architecture](#logical-architecture)
- [System Architecture](#system-architecture)

<!-- /TOC -->

## Objective
Design a customer management platform that enables the foundation of data-driven, customer centric organization.

## Solution Context
The below diagram depicts the context view for the solution.
![context view](/resources/context-view.jpg)

## Logical Architecture 
A high level logical architecture is shown below.

Our vision for the data architecture of our organization is centered around the principles of Data Mesh [ADR](/ADR/data-mesh-architecture.md), an approach that promotes decentralization and domain-oriented thinking. This visionary architecture aims to transform our data landscape, empowering teams, improving agility, and fostering a culture of data-driven innovation.
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

The operational data is published as a data domain.
![domain design](/resources/Logical%20architecture-domain.jpg)

## System Architecture
We are using AWS as the platform for all the services [ADR](/ADR/cloud-platform-selection.md)

[Reference architecture](/intent/reference-architecture.md) is provided for guidance and reference for building data products and systems.

Refer to [ADR](/ADR/Readme.md) for Architecture Decision records.

A high level simplified diagram of the customer data platform. 

![context](/resources/Logical%20Diagram.jpg)
1. **Data Sources:** Data is produced from different systems, SAAS applications, social media etc in variety of formats.

1. **Data ingestion and integration:** Data flows into AWS through batch processing, real-time data and Secure File Transfer Protocol.
    - AWS Transfer Family - Easily manage and share data with simple, secure, and scalable file transfers
    - AWS Eventbridge - is a serverless service that ingests events from own apps, SAAS application etc. It can also schedule data sync or pull events from supported sources.
    - AWS Kinesis - is a serverless streaming data service that simplifies the capture, processing, and storage of data streams
    - AWS Data exchange - is a service that can easily find, subscribe to, and use third-party data in the cloud
    - AWS Lambda is used for scraping information from social media and posted Kinesis for ingestion.

2. **Producer Domain Accounts:** Data sources are managed by the Business Domain. Producers use organization-level blueprints to provide core services such as security, governance, and open standards.
    - Operational Data Store is built using Amazon DynamoDB and Amazon DynamoDB Accelerator (DAX) to provide consistent single digit-millisecond latency performance. The data is published using lambda and API gateway to consumers. DynamoDB data streams along with kinesis can be used to publish events to listening applications.
    - Entity resolution if required is done in the producer domain using AWS Entity Resolution.
    - The data is published as events, API as well as S3 buckets to meet the needs of different consumer.

3. **Central IT Platform:** AWS Lake Formation provides centralized management of security, governance and auditing policies including fine-grain permissions. It also enables automatic schema discovery and conversion to the required format.

    **Metadata:** Metadata is managed via multiple services. AWS Glue is used for data cataloguing. Data lineage is stored in Amazon Neptune. Data contracts are stored in DynamoDB.

    **Governance:** Data governance can be done by the multiple services like AWS CloudTrail to record API calls for auditing and compliance monitoring, Amazon CloudWatch for monitoring services for metrics and log files and AWS  CloudFormation to enforce enforcing governance policies.

    **Privacy Management:** Privacy is managed using AWS MACIE to discover and protect sensitive data at scale.

    **Security & Access Management Services:** Security and access management can be achieved using multiple services provided by AWS. These services provide key and secrets managements, access management, privacy management, threat detection, vulnerability management etc.

    **Discovery:** AWS services like Athena, Glue Crawler and Data Quality are used for auto-discovery of metadata of services and assess the data quality.


4. **Account - Machine Learning:** ML (Machine Learning) is performed using Lake Formation. Use Amazon SageMaker to provide standard AI/ML models for customer segmentation, lifetime value and sentiment analysis. Other AI services such as Amazon Personalize can be utilized to get actionable insight and personalization. 

5. **Account - Business Analytics Domain:** Build all reportable data sets in Amazon S3 and leverage Amazon Redshift and Amazon Athena for analytics. Optionally, for heavily used analytics, build data marts in Amazon Redshift.For ad-hoc requirements, use Athena to analyze data in the data lake with standard SQL.

6. **Customer 360:** Build an aggregate domain to serve the Customer 360 view to other systems. Interactions are also logged in chronological order from different channels.Neptune a graph database is used  [Customer 360 Database selection](/ADR/customer-360-database.md). Lambda functions can be used to capture events from multiple systems and save them in the graph database. Relevant data requests are made to the systems via the central governance to access the data. Data is found using the data catalog to add to the customer view.

8. **Compensation Management:** 
- The [compensation management](/intent/compensation-management.md) gets events for flight cancellations, delays and baggage handling.
- The event initiates the automated or manual compensation management.

9. **Case Management:** 
[Case management](/intent/case-management.md) creates cases automatically based on system identified issues, through agents, different entry points in web and mobile applications and manually by the users in the system.

# Deployment architecture
- All the services are deployed on three availability zones in the same region. 
- [Pilot light](/ADR/dr-strategy.md) for DR will be used across multiple regions
- Separate accounts will be used for different business units
- Centralized accounts for security, logging and monitoring - - Separation of private and public subnets for security

### Architecturally Significant Requirement Realization
| Business Requirement                     | Realization                                   |
|------------------------------------------|--------------------------------------------------------|
| Centralized Customer Data Repository     | Customer 360 view has been provided, data can be viewed directly from source systems or viewed from customer 360 view based on the requirements |
| Segmentation and Personalization Tools   | Segmentation, personalization and machine learning has been provided |
| Privacy and Compliance                   | Data owner domain give access to the relevant data so data is more secure, Macie is used to identify any missing PII/sensitive information   |
| Comprehensive Customer Profiles          | Comprehensive data is available in the data mash for discovery and usage |
| Interaction Logs and Timeline Views       | Customer 360 graph database can store relevant timeline vies |
| Order Management and Personalization     | Machine learning and personalization has been integrated, all the data will be discoverable through the data mesh   |
| Compensation Management                  | Compensation management module is added |
| Intuitive Interfaces and Navigation      | Customer Experience Improvement, Operational Efficiency, Employee Empowerment |
| Real-time Data Processing and Analysis    | Data is available as API, events as well as for batch ingestion for variety of use-cases  |
| Sentiment Analysis and Action Planning    | Machine Learning to do sentiment analysis and next best action use-cases |
| Authentication and Authorization         | All components are secure and fine grained data security is implemented                                |
| Logging and Auditing                      | All systems integrate with the auditing, logging and monitoring tools                                |

### Architecturally Significant Non-functional Requirement Realization
| Business Requirement                     | Realization                                   |
|------------------------------------------|--------------------------------------------------------|
|Performance                               | The systems are built for high performance. The architecture reduces latency by leveraging caching, providing realtime APIs where required, providing CDN for fast access for users. The services are horizontally scalable and have high throughput.|
|Scalability                               | All services as scalable by design |
|Reliability   | Services have been deployed in multiple AZs for fault tolerance. DR pilot light site is available for Disaster recovery |
|Availability | All services are fault tolerant and automatically can switch over to reduce downtime |
| Security | Security is build by design. Separation of account for different business units adds an additional level of security. |
|Maintainability | All domains taking care of their own data and self serving the requests reduces the overhead of a central team maintaining and sharing data. Managed services also reduce operational overheads |
|Flexibility and Extensibility | The architecture can be extended to add more systems and data products without creating a bottleneck. |
|Usability | Front end cn be served faster by using CDN |
|Compliance | Compliance can be handled easily as the data owners give the other system access to the data. Also governance an sensitive data identification can be done by Macie |
|Performance Efficiency, Cost| Most of the services used are managed services and can be scaled as required to ensure optimised resource usage and costs. |
|Interoperability | Data is produced in multiple formats for different systems to use |
|Monitoring and Logging | All the systems produce data to cloudwatch for logging and X-Ray for debugging |
|Data Management | Appropriate data storage can be used for the requirements |


