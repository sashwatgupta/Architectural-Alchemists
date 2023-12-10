# Architectural Principles

<!-- TOC depthfrom:2 depthto:2 -->

- [Latency-aware Design Principles](#latency-aware-design-principles)
- [Instrumentation for Comprehensive Data](#instrumentation-for-comprehensive-data)
- [Automation for Operational Efficiency](#automation-for-operational-efficiency)
- [Resource-consumption-aware Solutions](#resource-consumption-aware-solutions)
- [Favor Managed Services](#favor-managed-services)
- [Interoperable, Modular Model](#interoperable-modular-model)
- [Business Event Driven Solutions](#business-event-driven-solutions)
- [Design for Scalability](#design-for-scalability)
- [Secure Solutions](#secure-solutions)
- [Solutions are resilient and available](#solutions-are-resilient-and-available)

<!-- /TOC -->
## Latency-aware Design Principles

### Statement
Design applications with the understanding that responses to requests may experience delays, ranging from milliseconds to seconds.

### Rationale
Acknowledging and accounting for latency ensures a more robust and user-friendly experience, especially in distributed and cloud-based environments.

### Implications
Implement asynchronous processing, optimize data retrieval, and conduct thorough testing to validate the system's responsiveness under various latency scenarios.

---

## Instrumentation for Comprehensive Data

### Statement
All components and solutions must generate comprehensive usage data and send it to a central location for real-time and subsequent decision-making.

### Rationale
Collecting detailed usage information facilitates effective monitoring, troubleshooting, and decision-making for scaling and cost optimization.

### Implications
Implement robust logging, metrics, and monitoring mechanisms, and establish a centralized system for aggregating and analyzing data.

---

## Automation for Operational Efficiency

### Statement
Enable the deployment, start, stop, and reset of components and solutions through automation scripts.

### Rationale
Automation streamlines operational tasks, reduces human error, and supports efficient management of cloud resources.

### Implications
Develop robust automation scripts, integrate continuous integration/continuous deployment (CI/CD) pipelines, and prioritize testing and validation of automation processes.

---

## Resource-consumption-aware Solutions

### Statement
Always consider the cost implications of cloud resources, aiming to use the minimum necessary.

### Rationale
Efficient resource management minimizes costs and ensures optimal utilization of cloud services.

### Implications
Implement dynamic scaling, use cost-effective cloud services, regularly review resource usage, and optimize solutions to minimize unnecessary expenses.

---

## Favor Managed Services

### Statement
Prioritize managed services over self-managed infrastructure.

### Rationale
Opting for managed services reduces operational overhead, allowing teams to focus on core application development and innovation.

### Implications
1. Operational Efficiency: Simplifies routine tasks, enhancing overall efficiency.
2. Enhanced Security: Leverages built-in security features, minimizing vulnerabilities.
3. Cost Optimization: Adopts a cost-effective pay-as-you-go model, eliminating over-provisioning.
4. Scalability: Offers seamless scalability to handle varying workloads.
5. Reliability: Benefits from cloud provider investments in redundancy and high availability.

---

## Interoperable, Modular Model

### Statement
Solutions, software applications, and technology components must be designed, developed, and implemented in support of a modular model.

### Rationale
- Permits change to an architectural element with minimized impact on collaborating elements.
- Allows for the reuse of software components across different modules and within the architectural model.
- Reduces overall IT and Process complexity, in turn reducing Total Cost of Ownership of the systems that work well together.
- Allows for the creation and reuse of common user interfaces and components across multiple business applications.
- Allows for development and maintenance of different modules to be handled individually given well defined interfaces.
- Promotes the use of middleware for system integration, and may provide opportunities to derive greater value from a given system through reuse.
- Enterprise must include adaptive capabilities (interoperability, portability, flexibility, scalability and reusability) in the design, development and/or acquisition of software technology components.

### Implications
- Enterprise must establish and follow an approach to integration and interoperability.
- Enterprise must establish and follow a conceptual architecture that clearly defines architectural tiers as conceptual architecture components.
- The integration and interoperability approach must adhere to the conceptual architectural model.
- Interactions between modules should be accomplished via well-defined interfaces and standard protocols.
- An integration and interoperability approach must be constructed to ensure the separation of business functionality and technology elements.
- Enterprise must ensure established solution components are serviced by multiple layers of operational support (automated monitoring, IT Help Desk, IT operations, subject matter experts).
- Vendor solutions and technologies must be evaluated for their ability to provide interoperability.

---

## Business Event Driven Solutions

### Statement
Solutions must respond to state changes of business transactions; they must preserve the integrity of the event and the solution response.

### Rationale
- Business event driven solutions promote customer-centric architectures and increase visibility to the business.
- Interactions between systems and events are formally defined; adhere to a communication standard and have measured performance.
- Cohesive modules are easier to change, test, and reuse.
- Loosely coupled modules are easier to change, test, and reuse.
- Enables better understanding of the impact or ramifications of a change.
- Reduces development time and total cost of ownership.

### Implications
- Solution revitalization efforts must ensure that the target solution is business event driven.
- Business Transactions are event-initiated and integrity will be maintained and monitored. Business processes should be business event-initiated.
- Each solution component, application, and architecture artifact must be well-documented.
- Solution components and architecture elements must be clearly distinguished from the mechanisms that allow them to interact.
- Compliance business rules must be embedded in solutions in a manner that minimizes the need for change in solution or application programming logic.

---

## Design for Scalability

### Statement
Architect solutions to be inherently scalable, capable of handling increased workloads and growing demands efficiently.

### Rationale
Scalability ensures that the architecture can adapt to changing requirements, accommodating both current and future needs without compromising performance or user experience.

### Implications
1. Modular Design: Create modular and loosely coupled components that can be scaled independently, allowing for granular adjustments based on demand.
2. Horizontal Scaling: Emphasize horizontal scaling by adding more instances of components, distributing the load, and enhancing system capacity.
3. Cloud-native Technologies: Leverage cloud-native technologies and services that facilitate automatic scaling, offering flexibility and cost-effectiveness.
4. Performance Monitoring: Implement robust monitoring to proactively identify performance bottlenecks and scale resources preemptively.
5. Load Balancing: Employ load balancing mechanisms to evenly distribute incoming traffic and optimize resource utilization.
6. Elasticity: Design systems to dynamically scale resources up or down based on demand, ensuring efficient resource utilization during peak and off-peak periods.

Secure:

Statement: Assume that solutions will be subject to malicious activities and implement security measures accordingly.
Rationale: Proactive security measures help protect sensitive data, prevent unauthorized access, and maintain the integrity of the system.
Implications: Enforce strict access controls, employ encryption, regularly update security protocols, and conduct thorough security audits and testing.

---
## Secure Solutions

### Statement
Assume that solutions will be subject to malicious activities and implement security measures accordingly.

### Rationale
Proactive security measures help protect sensitive data, prevent unauthorized access, and maintain the integrity of the system.

### Implications
Enforce strict access controls, employ encryption, regularly update security protocols, and conduct thorough security audits and testing.


---
## Solutions are resilient and available
### Statement
Solutions shall be constructed and implemented in a manner that ensures that business capabilities continue to be available in the face of a component failure, underlying changes in the technology, adverse events and continue to meet the business needs.

### Rationale
-   Ensures business service levels are attained and business can continue even in the face of an adverse event.
-   Ensures that transition from an existing solution to a newly developed or acquired solution is achieved with minimum business impact.
-   Enables service maintenance outages to be planned in a manner that minimizes business impact.
-   Ensures business survival by reducing the impact of a disaster or major failure.

### Implications
-   Enterprise must establish system availability architecture commensurate with stated SLA's.
-   Resiliency and availability is well represented in applicable non-functional requirements.
-   Preventive maintenance shall employ periodic inter-site and intra-site failover testing.
-   Enterprise must periodically perform system portfolio reviews to ensure application health is maintained and consistent with business requirements.
-   The environment, as a whole, must be able to detect attacks or adverse conditions.
-   In the face of component failure, the environment as a whole would remain functional to the level service permitting the completion of its mission.
-   Following a component failure, resiliency procedures exist to restore back to service.
-   Development risk is reduced when stable reliable components are reused.

### References
- https://www.linkedin.com/pulse/developing-enterprise-architecture-principals-which-justice-aj-/
- https://press20.blogspot.com/2019/07/lifespar-cloud-architecture-principles.html
