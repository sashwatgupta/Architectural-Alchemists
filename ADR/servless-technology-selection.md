# Serverless Architecture with AWS Fargate

**Date**: 04/12/2023

**Status** : Accepted
## Context

The need for a scalable, cost-effective, and efficient architecture has led us to explore serverless computing options for our applications. AWS Fargate is chosen as the preferred serverless solution for its container orchestration capabilities, ease of use, and flexibility. 

## Decision

We will adopt a serverless architecture using AWS Fargate for containerized workloads. For workloads that do not require business logic and need massive scaling AWS Lambda is preferred.

## Consequences

### Positive

1. **Scalability:** Fargate allows us to scale our applications automatically, handling the infrastructure management and scaling based on demand.

2. **Cost-Efficiency:** With serverless architecture, we only pay for the resources consumed during the execution of our containers, leading to potential cost savings compared to traditional infrastructure.

3. **Operational Efficiency:** Fargate abstracts away the underlying infrastructure, reducing the operational overhead associated with managing servers. This allows our teams to focus more on application development and less on infrastructure management.

4. **Flexibility:** Fargate supports multiple programming languages and frameworks, giving us flexibility in choosing the technology stack for our applications.

5. **Security:** AWS Fargate provides a secure environment for running containers, and AWS takes care of patching and securing the underlying infrastructure.

### Negative

1. **Cold Start Latency:** Cold starts may occur when containers are not readily available, leading to a slight delay in the initial response time. This may impact applications with strict latency requirements.

2. **Learning Curve:** Teams may need some time to adapt to the Fargate model, especially if they are new to container orchestration.

3. **Resource Limitations:** Fargate imposes certain resource limitations on containers, which may require careful consideration of application resource requirements.

## Options Considered

1. **AWS Lambda:** Although Lambda is a popular serverless option, its execution model and limitations might not be suitable for certain workloads, especially those requiring longer execution times or specific runtime environments.

2. **EC2 Instances:** Traditional EC2 instances provide more control over the environment, but they require manual scaling and maintenance, resulting in higher operational overhead.

## Decision Drivers

1. **Containerization:** Our applications are containerized, making Fargate a natural fit for orchestrating and managing container workloads.

2. **AWS Ecosystem:** Fargate seamlessly integrates with other AWS services, enabling us to leverage a wide range of tools and features for building robust and scalable applications.

3. **Operational Simplicity:** Fargate abstracts away the underlying infrastructure, simplifying operations and allowing teams to focus on application development.

## References
- [Fargate vs Lambda](https://www.clickittech.com/devops/fargate-vs-lambda/?utm_source=fargate+vs+lambda&utm_id=Blogs+Medium)


