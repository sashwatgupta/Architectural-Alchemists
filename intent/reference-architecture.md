
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

# Reference architecture for a operational system
The reference architecture for microservices is provided below. Operational systems can follow the below guidance.
Optionally Fargate can be replaced by Lambda if required.
![microservice reference architecture](/resources/microservice-reference-architecture.jpg)

# Deployment architecture
- All the services are deployed on three availability zones. 
- Pilot light for DR will be used across multiple regions
- Separate accounts will be used for different business units
- 
