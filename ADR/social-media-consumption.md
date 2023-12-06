#  Ingest Social Media Feed in AWS

**Date**: 04/12/2023

**Status** : Accepted

## Context
We need to design a scalable and reliable architecture to ingest social media feed data into AWS for further processing and analysis. The chosen social media platform is Twitter, and the goal is to periodically retrieve data from the Twitter API and store it in an AWS environment for analytics purposes.

## Decision
We have decided to use a combination of AWS services to implement the data ingestion pipeline. The key components include AWS Lambda for serverless and Amazon CloudWatch Events for triggering data retrieval.

## Alternative Considered
EC2 Instances
We also considered using Amazon EC2 instances for data ingestion instead of AWS Lambda. This alternative would involve deploying and managing EC2 instances to run custom scripts for data retrieval and processing.

## Consequences
### Benefits
1.  **Full Control:** EC2 instances provide more control over the environment and execution, allowing for custom configurations and longer execution times. 
2.  **Flexibility:** EC2 instances can handle a wider range of processing tasks and are not subject to the 15-minute execution time limit of AWS Lambda.
    

### Drawbacks
1.  **Operational Overhead:** Managing and maintaining EC2 instances involves additional operational overhead compared to the serverless model of AWS Lambda.   
2.  **Scaling Challenges:** Scaling EC2 instances requires manual intervention or additional tooling, making it less automatic and potentially slower to adapt to varying workloads.
    

## Decision Rationale
While EC2 instances provide more control and flexibility, the serverless architecture of AWS Lambda aligns better with the project's requirements for scalability, cost-effectiveness, and ease of maintenance. The periodic and event-driven nature of social media data retrieval makes AWS Lambda a suitable choice for this use case.

## Decision Evaluation
The chosen architecture with AWS Lambda remains the preferred option due to its serverless nature, scalability, and cost-effectiveness. Regular reviews will be conducted to ensure the continued efficiency and relevance of the chosen approach, considering any changes to the social media API or AWS services.

