# Adoption of AWS as cloud platform

**Date**: 04/12/2023

**Status** : Accepted

## Context
In formulating our architectural design, a Cloud Native [ADR](/ADR/cloud-native.md) approach is pivotal. This methodology necessitates a cloud platform that can adeptly provision infrastructure and services. Given the myriad public cloud providers available, each boasting an extensive service catalogue, distinguished reputation, and a thriving user base, a judicious decision must be made regarding the optimal vendor to host our infrastructure.

## Decision
We point out that any of the leading cloud providers such as Google Cloud Platform, Amazon Web Services or Azure would have the capabilities to fit our needs. Most of the services used in our case can be provisioned with slight modifications on each and every platform. We regard a multi-cloud solution as significant overhead and the integration of multiple cloud providers would simply hinder progress. Thus the decision for a specific vendor boils down to preference, pre-existing know-how and interoperability with other tools in the stack.
Due to our advanced knowledge of AWS we propose a solution architecture based on AWS. Furthermore the different services provided by AWS is more than any other cloud provider.

We would like to point out that all the services shown in the solution architecture are available in slight modification for other cloud providers making the design, although focusing on AWS specific components, portable to other cloud providers. This might be a need if for example the devloper team has a more profound knowledge on another platform.


## Decision Drivers

1. **Scalability and Elasticity:**
   - Design the architecture to scale horizontally, ensuring the platform can seamlessly handle growing data volumes and user demands.
   - Leverage AWS Auto Scaling to dynamically adjust resources based on workload fluctuations, optimizing cost efficiency.

2. **Security and Compliance:**
   - Implement a multi-layered security approach, incorporating AWS Identity and Access Management (IAM), encryption, and network security measures.
   - Adhere to industry-specific compliance standards and best practices to safeguard sensitive data.

3. **Data Integration and Ingestion:**
   - Establish robust data pipelines for efficient and reliable ingestion from diverse sources, including on-premises databases, third-party APIs, and streaming data.
   - Leverage AWS services such as AWS Glue, AWS DataSync, and AWS Direct Connect to streamline data integration processes.

4. **Data Storage and Management:**
   - Utilize Amazon S3 for scalable and cost-effective data storage, with appropriate data partitioning and organization.
   - Implement data lifecycle management strategies to optimize storage costs and ensure timely data availability.

5. **Analytics and Processing:**
   - Leverage AWS services such as Amazon Redshift for high-performance data warehousing and Amazon EMR for distributed data processing.
   - Integrate serverless computing with AWS Lambda for event-driven processing and real-time analytics.

6. **Machine Learning and AI Integration:**
   - Integrate machine learning services such as Amazon SageMaker for building, training, and deploying machine learning models.
   - Explore opportunities to embed AI-driven insights into data processing workflows for enhanced decision support.

7. **Monitoring and Logging:**
   - Implement comprehensive monitoring and logging using AWS CloudWatch and AWS CloudTrail to ensure visibility into system performance, security events, and user activities.
   - Establish automated alerting for proactive issue detection and resolution.

8. **Cost Optimization:**
   - Continuously monitor and optimize resource usage to manage costs effectively.
   - Utilize AWS Cost Explorer and AWS Budgets to gain insights into spending patterns and enforce cost controls.

9. **High Availability and Disaster Recovery:**
   - Design for high availability across multiple AWS Availability Zones to ensure business continuity.
   - Implement robust backup and disaster recovery mechanisms using AWS services like Amazon S3 versioning and AWS Backup.

10. **Continuous Improvement:**
    - Embrace an agile mindset, regularly reviewing and refining the architecture based on evolving business requirements, technological advancements, and feedback from stakeholders.
    - Foster a culture of innovation, encouraging the exploration of new AWS services and features to enhance the capabilities of the data platform.

## Considered Alternatives

|                              | **Amazon Web Services**         | **Microsoft Azure**            | **Google Cloud Platform**      |
|----------------------------- | ------------------------------ | ------------------------------ | ------------------------------ |
| **Launched**                 | 2006                           | 2008                           | 2011                           |
| **Availability points**      | 450+                           | 160+                           | 112+                           |
| **Strength**                 | Infrastructure-as-a-Service (IaaS) | Platform-as-a-Service (PaaS)    | Database-as-a-Service (DaaS)   |
| **Services**                 | 237+                           | 172+                           | 100+                           |
| **Strongest areas of cloud deployments** | Public cloud, private cloud on AWS | Public, Hybrid cloud, On-premises | Public cloud, Multi-cloud       |
| **Pricing**                  | Pay-as-you-go, by product/service | Pay-as-you-go, by product/service | Pay-as-you-go, by product/service |
