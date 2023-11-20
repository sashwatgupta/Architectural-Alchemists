# Architectural Principles

## Solutions should be business event driven

### Statement
Solutions must respond to state changes of business transactions; they must preserve the integrity of the event and the solution response.

### Rationale:
-   Business event driven solutions promote customer centric architectures and increase visibility to the business.
-   Interactions between systems and events are formally defined; adhere to a communication standard and have measured performance.
-   Cohesive modules are easier to change, test and reuse.
-   Loosely coupled modules are easier to change, test and reuse.
-   Enables better understanding of the impact or ramifications of a change.
-   Reduces development time and total cost of ownership.

### Implications:
-   Solution revitalization efforts must ensure that the target solution is business event driven.
-   Business Transactions are event initiated and integrity will be maintained and monitored. Business processes should be business event initiated.
-   Each solution component, application, and architecture artifact must be well documented.
-   Solution components and architecture elements must be clearly distinguished from the mechanisms that allow them to interact.
-   Compliance business rules must be embedded in solutions in a manner that minimizes the need for change in solution or application programming logic.

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

## Solutions must support an interoperability, modular model
### Statement
Solutions, software applications and technology components must be designed, developed and implemented in support of a modular model. 

### Rationale
-   Permits change to an architectural element with minimized impact on collaborating elements.
-   Allows for the reuse of software components across different modules and within the architectural model.
-   Reduces overall IT and Process complexity, in turn reducing Total Cost of Ownership of the systems that work well together.
-   Allows for the creation and reuse of common user interfaces and components across multiple business applications.
-   Allows for development and maintenance of different modules to be handled individually given well defined interfaces.
-   Promotes the use of middleware for system integration, and may provide opportunities to derive greater value from a given system through reuse.
-   Enterprise must include adaptive capabilities (interoperability, portability, flexibility, scalability and reusability) in the design, development and/or acquisition of software technology components.

### Implications
-   Enterprise must establish and follow an approach to integration and interoperability.
-   Enterprise must establish and follow a conceptual architecture that clearly defines architectural tiers as conceptual architecture components.
-   The integration and interoperability approach must adhere to the conceptual architectural model.
-   Interactions between modules should be accomplished via well defined interfaces and standard protocols.
-   An integration and interoperability approach must be constructed to ensure the separation of business functionality and technology elements.
-   Enterprise must ensure established solution components are serviced by multiple layers of operational support (automated monitoring, IT Help Desk, IT operations, subject matter experts).
-   Vendor solutions and technologies must be evaluated for their ability to provide interoperability.

## References
- https://www.linkedin.com/pulse/developing-enterprise-architecture-principals-which-justice-aj-/
- https://press20.blogspot.com/2019/07/lifespar-cloud-architecture-principles.html
