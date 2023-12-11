# Pilot Light Architecture for Disaster Recovery

**Date**: 04/12/2023

**Status** : Accepted

## Context
Our organization recognizes the critical importance of having a robust Disaster Recovery (DR) strategy in place to ensure business continuity in the event of unforeseen incidents. We are evaluating different approaches and have decided to implement a Pilot Light architecture for our DR strategy.

## Decision
We will adopt a Pilot Light architecture for Disaster Recovery.

![](/resources/pilot-light.png)
## Rationale
1. **Rapid Recovery**: The Pilot Light architecture allows us to maintain a minimal but functional version of our application environment in the cloud, enabling a swift and efficient recovery process.

2. **Cost-Efficiency**: By keeping only essential components running during normal operations, we can minimize costs compared to a fully redundant active-active setup, without compromising on recovery speed.

3. **Resource Optimization**: The minimal environment includes critical components such as a database server, basic application servers, and networking infrastructure, optimizing resource usage and cost.

4. **Automated Scaling**: Implementation of automation tools and scripts for scaling up resources ensures a seamless transition from the Pilot Light to a fully operational environment during a disaster.

## Alternatives Considered
1. **Active-Active Setup**: An active-active setup was considered but deemed more resource-intensive and costly for our current needs.

2. **Backup and Restore**: Traditional backup and restore mechanisms were evaluated, but the Pilot Light architecture offers faster recovery and greater agility.

![](/resources/pilot-light-0.png)

## Implications
1. **Infrastructure as Code (IaC)**: The implementation of the Pilot Light architecture requires the development and maintenance of Infrastructure as Code to ensure consistency and repeatability.

2. **Monitoring and Alerts**: Robust monitoring and alerting systems are crucial to promptly detect any issues and trigger the scaling of resources when needed during a disaster.

3. **Regular Testing**: Regular testing of the disaster recovery process, including failover and failback procedures, is essential to ensure its effectiveness.


