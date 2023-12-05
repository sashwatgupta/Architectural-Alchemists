# Data storage for Customer Data Platform

**Date**: 04/12/2023
**Status** : Accepted

## Context
The data stored for Customer Data Platform can be stored & managed centrally or can be stored and managed by specific business units.

## Architecture Options & Trade offs
The options and tradeoff are documented below:-
### Centralised storage & mangement
The data is recieved from multiple sources and stored in a common repository. The data is served from the central repository to all the systems.


### Federated storage & mangement (data mesh)
The following principles are followed for a data lake.
 1. domain-oriented decentralized data ownership and architecture
 2. data as a product
 3. self-serve data infrastructure as a platform
 4. federated computational governance.

![logo](/resources/data-mesh.png)


|Centralized data|Federated Data|
|:----|:----|
|Centralized team|Federated team|
|Responsible for data quality|Responsible for defining how to model what constitutes                quality|
|Responsible for data security|Responsible for defining aspects of data security i.e. data                sensitivity levels for the platform to build in and monitor                automatically|
|Responsible for complying with regulation|Responsible for defining the regulation requirements for the                platform to build in and monitor automatically|
|Centralized custodianship of data|Federated custodianship of data by domains|
|Responsible for global canonical data modeling|Responsible for modeling [polysemes](https://en.wikipedia.org/wiki/Polysemy) - data elements that                cross the boundaries of multiple domains|
|Team is independent from domains|Team is made of domains representatives|
|Aiming for a well defined static structure of data|Aiming for enabling effective mesh operation embracing a                continuously changing and a dynamic topology of the mesh|
|Centralized technology used by monolithic lake/warehouse|Self-serve platform technologies used by each domain|
|Measure success based on number or volume of governed data (tables)|Measure success based on the network effect - the                connections representing the consumption of data on the                mesh|
|Manual process with human intervention|Automated processes implemented by the platform|
|Prevent error|Detect error and recover through platform’s automated                processing|

### Decision
The federated model of data governance and storage will be domain driven and can scale well. The mamangement of the data would require to be automated and the different domains will require data expertese. 

## Reference
[Data mesh pronciples](https://martinfowler.com/articles/data-mesh-principles.html)

