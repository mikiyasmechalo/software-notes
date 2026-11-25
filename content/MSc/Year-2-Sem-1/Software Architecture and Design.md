# CH 1: Foundations of Software Architecture 
Software architecture is a foundational aspect of software development that defines the structure and organization of a software system. 
Architecture serves as a blueprint and a guide for the entire development process, influencing design decisions, technology choices, and the overall quality of the software product.

**What is Software Architecture?** 
refers to the set of structures needed to reason about the system: software elements, relations among them, and properties of both. 
It encompasses the following key aspects:
- **Components**: Individual units of function that make up the whole system. classes, modules, services or any other discrete unit of software that performs a specific function.
- **Relationship**: Interaction between components, communicate, share data and depend on each other.
- **Constraints**: limitations and requirements imposed on the architecture, such as performance, security, scalability and maintainability.

**Importance of S.A** 
- *Blueprint for Development*: It provides a high-level structure that serves as a guide for the development team. It ensures consistency and Alignment with business goals.
- *Facilitates Communication*: It enables effective communication among stakeholders, It ensures that everyone has a *shared understanding* of the system's structure and goals.
- *Risk Mitigation*: By *identifying potential risks* early in the development process, the architecture allows teams to make informed decisions that can mitigate these risks. 
- *Quality Assurance*: A strong architectural foundation can lead to a more robust and reliable system. to ensure quality attributes such as performance, security, and maintainability. 
- *Supports Change*: A flexible architecture allows for easier updates and modifications, facilitating the long-term viability of the system. Enables accommodating New Features and Scaling with Demand.

### Historical Context of Software Architecture
**Early Beginnings**
- The term "software engineering" emerged in late 1960s as a response to the growing complexity of software systems.
- In the 1970s the focus shifted toward *Structured Programming*, w/c advocated for breaking down programs into smaller, manageable modules.

**The rise of Architecture** 
- By the 1980s the idea of 'architecture' began to gain prominence. David Parana's "On the criteria to be used in decomposing systems into modules" highlighted the importance of modular design.
- In the 1990s Architectural Patterns are introduced, notably through the work of "Gang of the four", provided vocabulary and framework for discussing architectural solutions.

**The advent of OOP** 
- The 1990s also saw the rise of Object Oriented design (OOD), concepts such as encapsulation, inheritance and polymorphism became integral to architecture, promoting reusability and flexibility.
- The development of Unified Modeling Language (UML), provided a standardized way to model software architecture and design, further enhancing communication among stakeholders.

**The Shift to Component based and Service Oriented Architectures** 
- 2000s - shift towards CBSE, w/c emphasized reusable components.
- SOA revolutionized software architecture by promoting the use of services as fundamental building blocks. This enabled more flexible and scalable systems.

**The Modern Era: Microservices and Cloud-Native Architectures** 
- 2010s - microservices introduced a way to build applications as a suit of small independent services. w/c allowed teams to build, deploy and scale services independently, enhancing agility and responsiveness.
- Cloud computing leverages cloud services to build scalable, resilient systems that can adapt to changing demands. More automation, orchestration and continuous delivery.

**Influential Figures and Their Contributions** 
- *Martin Flower* - written extensively on agile development, microservices and refactoring.
- *Grady Booch* - contributed to OOD and UML.
- *Len Bass, Paul Clements & Rick Kazman* - Their book "Software Architecture in Practice" has been instrumental in defining the practices and principles of software architecture.


### Key Components of Software Architecture
#### Modules
- Are the fundamental units of software architecture, representing cohesive groups of functionality that can be developed, tested and maintained independently.
- A module is a self-contained unit of functionality that encapsulates a specific aspect of a system.

**Key Characteristics** 
- **Cohesion** - internal components of a module are closely related and work together to achieve a specific purpose. High cohesion improves maintainability and understandability.
- **Encapsulation** - hide their internal workings and expose only necessary parts through interfaces. allows for easier changes without affecting external parts.
- **Reusability** - well designed modules can be reused across different projects.

**Types of Modules** - based on their functionality/ role
- *Functional Modules* - perform specific functionality or features, e.g. authentication, 
- *Data Modules* - -manage data storage, retrieval and manipulation, e.g. DB, file storage
- *Service Modules* - In SOA, these modules expose functionalities as services that can be accessed by other components. e.g. REST APIs, Microservices
- *Utility Modules* - provide common functionalities that can be shared across different parts of the application, e.g. logging, error handling

**Best Practices for Module Design** 
- *Single Responsibility Principle* (SRP) - each module should have one reason to change, this enhances maintainability and reduces complexity.
- *Interface Design* - clear and concise interfaces for modules, to facilitate interaction between modules and enhance reusability.
- *Loose Coupling* - changes in one module should have minimal / no impact on others. this can be achieved through well defined interfaces and dependency injection (a design technique where a component receives its dependencies (collaborators) from an external source rather than creating them itself(`new DB()`)).
- *Testing and Validation* - test modules in isolation to validate functionality. 

**Examples of Modular Architecture** 
- an e-commerce application might have: User, Product, Order and notification modules.
- each module can be developed and maintained independently.

#### Interfaces
Defines how modules and components interact with each other.
An **interface** is a boundary across which two or more systems can communicate. It defines methods and properties that must be available for interaction without exposing internal workings.

**Key Characteristics** 
- *Abstraction*: interfaces provide an abstract view of a module's functionality.
- *Decoupling*: modules can be developed and modified independently, since changes won't affect other modules as long as the interface remains the same.
- *Interoperability*: enables different systems or components to work together seamlessly, even if they use different technologies.

**Types of Interfaces** 
- *User Interface (UI)*: for interaction with the system, including GUI and CLIs. focuses on usability and UX.
- *APIs*: define methods and data formats that apps can use to communicate with each other. APIs can be local (in 1 app) or remote (over network like REST or SOAP)
- *Service Interfaces*: In SOA and Micro-S, these define how different services communicate, they specify protocols, data formats and endpoints for service interactions.
- *Data Interfaces*: define how data is exchanged between components, specifying data formats (XML, JSON) and serialization methods.

**Best Practices** 
- *Simplicity* - keep it as simple as possible, this reduces learning curve and enhances usability.
- *Consistency* - in naming conventions, parameter types and return values across the interface.
- *Versioning* - to manage changes over time, this allows existing clients to continue using old versions while enabling new  features in updated interfaces.
- *Error handling* - clear error handling and response mechanisms within interfaces.
- *Documentation* - usage examples, parameter descriptions and error codes. 

#### Data Flows
Refers to the pathway through which data travels in a system. Visualized as a series of interactions between components where data is inputted, processed and outputted.

*Key aspects of data flow*:
- Data sources - Origin of data, which include user inputs, external DBs , APIs and sensors.
- Data Processing - manipulation of data, which can include calculations, filtering or aggregating.
- Data Storage - After processing data may be stored in DBs, files, or other storage system.
- Data Outputs - processed data is delivered to various destinations, users, interfaces, reports.

**Importance of Understanding Data Flows** 
- *System Efficiency* - architects can identify bottlenecks & optimize data processing paths.
- Data Integrity - clear data flow definitions help ensure that data remains accurate and consistent throughout its lifecycle.
- Security: knowing how and where data flows through allows for the implementation of appropriate security measures to protect sensitive information.
- Scalability: helps in designing systems that can scale effectively, to accommodate higher volume or complexity without compromising performance.

**Visualizing Data Flows** 
- Data Flow Diagrams: provide a graphical representation of data movement within a system, showing how data is inputted, transformed and outputted. DFDs typically include processes, data stores, data sources and data flows.
- Flowcharts: depict the sequence of operations involved in the data processing.
- Sequence Diagrams: In OOP, SDs illustrate how objects interact overtime, showcasing the flow of messages and data between them.

**Best Practices for Managing Data Flows** 
- Clear Definitions: clear data flows showing sources, processes, storage and outputs.
- Data Validation: implement validation checks at various points in the data flow to ensure data integrity and prevent errors.
- Data Security: use encryption and secure access control to protect data during flow.
- Monitoring and Logging: to track data flows, enabling quick detection of issues and audits.

**Example** 
In an e-commerce app
1. User registration
	- Data Source: User input from a registration form.
	- Data Processing: Validation of input data (e.g., checking for existing usernames).
	- Data Storage: Storing user details in a database.
	- Data Output: Confirmation message sent to the user.

2. Order Processing:
    - Data Source: User's order details from the checkout page.
    - Data Processing: Calculating total price, applying discounts, and processing payment.
    - Data Storage: Saving order information in the orders database.
    - Data Output: Sending order confirmation and receipt to the user.

### Architectural Patterns and Styles
A pattern is a general reusable solution to a recurring problem. It defines a common structure that can be adapted to various situations, allowing us to leverage proven approaches to design.

**Key Characteristics** 
- *Reusability*: patterns can be used across d/t projects, reducing time and effort needed to design a new architecture.
- *Flexibility*: they can be adapted to meet specific needs of a project, they allow customization while still adhering to best practices.
- *Standardization*: using established patterns promotes consistency across systems, making it easier for teams to collaborate and maintain codebases.

**Common Architectural Patterns** 
- **Layered Architecture**: divides the system into layers each with a specific responsibility (e.g. presentation, logic, data access). each layer only interacts with the adjacent layers, promoting separation of concerns.
- **Client-Server**: the system is divided into clients that request services and the server that provides those services, this allows for scalability and flexibility for deployment.
- **Microservices**: structures the app as a collection of small independent services that communicate over a network. Each service is responsible for a specific business capability, promoting scalability and resilience.
- **Event-Driven**: based on the production, detection and reaction to events by which components communicate, this enables decoupled interactions and real time processing.
- **SOA**: building services that communicate over a network, services are designed to be reusable and interoperable, often using standardized protocols.

##### Architectural Styles
Refers to the general philosophy that guide the design of a system. They are a higher level abstraction and encompass multiple architectural patterns. Some are:

- **Monolithic Architecture**: all components of an app are combined into a single, unified codebase. Simpler to develop initially but it can become challenging to scale and maintain.
- **Microservices**: an evolution of monolithic, it emphasizes breaking down applications into smaller, independently deployable services.
- **Serverless**: developers build apps without managing server infrastructure, they instead leverage cloud services to run code in response to events, this allows automatic scaling and reduced operational overhead.
- **MVC**: separates the app into 3 interconnected components, Model(data), View(UI) and Controller(logic). It enhances maintainability and testability.

**Choosing the right Pattern or Style** 
Factors:
- *Project requirement*: specific needs of the project, performance, scalability and maintainability.
- *Team Expertise*: of the development team, familiarity may lead to more effective implementation.
- *Technology Stack*: tech used may or might not align with potential architectural choices.
- *Future Maintenance*: anticipate future growth and requirement changes, select patters that facilitate adaptability and maintenance.

**Best Practices for Implementing Architectural Patterns** 
- Documentation: architectural decisions, patterns and styles used, for current and future team.
- Modularity: for easy updates and maintenance while adhering to the chosen pattern.
- Testing: automated tests to validate the architecture's effectiveness, for performance and reliability.
- Continuous Review: as the project evolves, make necessary adjustments to accommodate new requirements and technologies.

### Roles and Responsibilities in Software Architecture
#### Architect Vs. Developer
**Architect** 
Responsible for defining the high-level structure of the system, ensuring it meets both technical and business requirements. Key responsibilities:
- *Designing Architecture*: creating the overall architecture, selecting appropriate patterns and technologies.
- *Setting Standards*: coding standards, best practices and guidelines for the team.
- *Stakeholder Communication*: acting as a liaison between technical teams and stakeholders to ensure alignment on objectives.

**Developer** 
Implements the architecture designed by the architect, translating high level designs to functional code. Responsibilities:
- *Coding*: writing, testing and maintaining the software according to the architectural guidelines.
- *Unit testing*: ensuring individual components function correctly before integration.
- *Feedback Loop*: providing feedback on the architecture based on practical implementation experiences, which may lead to architectural adjustments.

**Collaboration between the two** 
- Regular meetings - to discuss progress, challenges and potential adjustments to the architecture.
- Pair programming - encouraging pair-programming sessions to facilitate knowledge sharing and collaborative problem solving.
- Documentation: maintaining clear and accessible documentation to ensure the team members understand the architectural decisions and guidelines.

#### Stakeholder Interaction
Stakeholders are individuals or groups who are affected by or have an interest in the software system being developed. They can include:
- End Users
- Business executives - have a vested interest in the business outcomes of the software, e.g. ROI
- Project managers - overseers
- Developers and QA Teams
- Regulatory bodies e.g. data protection regulations

**It's Importance** 
- Requirement Gathering - architecture must align with their needs and expectations
- Conflict resolution 
- Feedback mechanisms - during development
- Change management - better management of priorities

**Strategies for Effective Interaction** 
- Regular meetings - progress, feedback, alignment. keep them Informed and Engaged.
- Prototyping - to visualize the architecture and gather early feedback for refinement.
- Documentation - clear docs to ensure transparency and facilitate communication.
- Surveys and Interviews - to gather insights from diverse stakeholders.

Example of Stakeholder interaction: Kickoff meetings, UAT sessions, status reports

#### Decision Making Process
Involves selecting selecting design patterns, tools, technologies, and architectural styles that align with the project.
**It's Importance** 
- Alignment with Requirements: ensuring architectural decisions meet both FN and NFN requirements.
- Risk Management: Identifying potential risk associated with architectural choices and developing mitigation strategies.
- Resource Optimization: making decisions that maximize the use of available resources, like time, budget and personnel.
- Long-Term Viability: choosing architectures that support scalability and adaptability,

**Factors influencing Architectural Decisions** 
- Project requirements
- Stakeholder input
- Technical Constraints - existing systems and technologies, or regulations.
- Team Expertise
- Market Trends - to inform decisions about adopting new tools or methodologies.

**Decision-Making Models** 
- Consensus DM: involves gathering input from all stakeholders and striving for agreement.
	- fosters collaboration but may take more time.
- Majority Vote: majority opinion determines the decision, while quicker, it may not fully address minority concerns.
- Expert Opinion: relying on insights of experienced architects to guide decisions.
- Cost-Benefit Analysis: Assessing trade-offs between options, by weighing costs against the expected benefits.

**Best Practices for Effective DM** 
- Define Clear Objectives - to guide the process and ensure objective alignment.
- Engage Stakeholders - for diverse perspectives
- Document Decisions - architectural decisions and the rationale behind them, and any alternatives considered. To promote transparency and aid future reference.
- Review and Iterate: be open to revisit and revise decisions as new info emerges.

### Phases of Development
#### Phases of Development and Architectures importance in each phase
1. **Requirement Gathering:** 
	 - Architects engage with stakeholders to understand their needs, ensuring that the architectural vision aligns with user needs and business goals.
	 - define FN and NFNs.
2. **Design:** 
	 - Architects create a high-level and detailed architectural designs, selecting patterns, defining modules, interfaces, and data flows, and ensuring quality attributes like performance are adequately addressed. This provides a blueprint for development, facilitating communication among team members and stakeholders.
3. **Implementation:** 
	 - Architects may provide guidance on coding standards and best practices, guiding developers in creating maintainable, scalable, and efficient code that adheres to the architectural vision.
4. **Testing:** 
	 - Architects may assist in defining test strategies and ensuring that the system meets quality attributes, helping to identify architectural flaws early and verify functional and non-functional requirements.
5. **Deployment:** 
	 - Architects may be involved in planning deployment strategies and ensuring the system can scale and perform effectively in the production environment, ensuring that the architecture supports effective scaling and performance.
6. **Maintenance:** 
	 - Architects consider how changes will impact the existing architecture and plan for future scalability and adaptability, facilitating ongoing improvements and adaptations as user needs and technology evolve.

**Example of Architecture in the Phases** 
- During requirements gathering, architects might conduct workshops with stakeholders to elicit needs and document them.
- In the design phase, the architect may create diagrams illustrating the system architecture, including modules and interactions.
- During implementation, the architect could conduct code reviews to ensure adherence to architectural standards.
- In testing, the architect may help develop performance tests to validate that the system meets response time requirements.
- For deployment, the architect might design a strategy for rolling out the software, considering load balancing and failover mechanisms.
- In the maintenance phase, the architect could analyze system performance data to identify areas for optimization or refactoring.

#### Agile vs. Waterfall Architectures
**Waterfall Architecture** 
A linear and sequential approach to software development. Each phase must be completed before the next starts.
- Phases: req. gathering, design, implementation, testing, deployment and maintenance.
- Architectural Implications: the architecture is defined early in the process, often in design.
- Benefits:
	- clear structure and documentation
	- easier to manage for smaller projects with well defined requirements
	- predictable timelines and deliverables
- Drawbacks:
	- limited Flexibility for changes once the process has started.
	- Potential for misalignment between initial requirement and final product if  users needs evolve.

**Agile Architecture** 
An iterative and incremental approach that emphasizes flexibility, collaboration and stakeholder feedback.
- Phases: short cycles called iterations/ sprints, where req. gathering, design, implementation and testing occur simultaneously.
- Architectural Implementations: the architecture evolves overtime as feedback is incorporated. architects must be prepared to make adjustments.
- Benefits:
	- Greater flexibility to adapt to changing requirements
	- Enhanced collaboration among team members and stakeholders
	- Faster delivery of functional increments
- Drawbacks:
	- less comprehensive documentation
	- Risk of architectural erosion if not carefully managed

**Choosing Between Agile and Waterfall** 
- Project size: Large, complex projects with well-defined requirements - waterfall. 
	- projects with changing requirements - agile.
- Stakeholder Involvement: agile is ideal for projects where active engagement is needed.
- Time constraints: Agile allows rapid delivery.
- Risk Tolerance: teams comfortable with uncertainty and change - Agile.

#### Documentation Practices
Effective documentation practices support the architectural vision and ensure that knowledge is preserved throughout the project.

**Importance of Documentation in SA** 
- *Communication*: provides common language for architects, developers and stakeholders.
- Knowledge Transfer: to onboard new teams allow smooth transitions.
- Reference: for implementation and maintenance.
- Compliance: in regulated industries, documentation is often required to show compliance.

**Types of Documentation** \*relevant at various stages of SDLC
1. Architectural Decision Records (ADRs): capture architectural decisions, their rationale and alternatives considered. (clear history of architectural choices) 
2. Design Specifications: detailed documents outlining the architecture, including diagrams of components, interfaces, data flows and interactions. guides implementation.
3. User Stories and Use Cases: describe user interactions with the system, capturing requirements from and end-user perspective.
4. Technical Documentation: API docs, coding standards, setup guides & deployment instructions.
5. Testing Documentation: testing strategies, test cases & results.

**Best practices for Documentation** 
- Keep it simple: clarity and conciseness, avoid complex language.
- Use visual aids: diagrams, flowcharts and models to show concepts visually.
- Maintain Up-to-date Docs: review and update docs regularly to reflect changes.
- Encourage collaboration: culture where team members contribute to docs, sharing insights.
- Automate where possible: e.g. code comments or API documentation tools.

### Quality Attributes in Software Architecture
Quality Attributes, AKA NFRs, refer to criteria that evaluate the operation of the system rather than its functionality.
They often dictate how well a system performance under various conditions and can impact user satisfaction and system longevity,
**Key Attributes**:
- **Performance**: speed and efficiency responding to user's requests. measured by: Response time, throughput, Resource usage etc.
- **Scalability**: ability to handle increased loads.
- **Reliability**: how consistently it performs its intended function without failure, can be measured by Uptime, MTBF, and fault tolerance.
- **Security**: protecting the system and data from unauthorized access, breaches and attacks. Confidentiality, Integrity and availability (CIA) are main security attributes.
- **Usability**: ease which users can interact with the system & achieve their goals. it encompasses UI design, accessibility and overall UX.
- **Maintainability**: ease with which a system can be modified, updated & repaired. it is influenced by code quality, modularity, and documentation availability.
- **Portability**: ability for a system to operate in different environments/ platforms without extensive rework.

**Importance of QAs** 
- User satisfaction - QAs impact UX and satisfaction, w/c influence adoption and retention.
- Cost efficiency - can reduce cost associated with reworks, maintenance and downtime.
- Competitive advantage - good software can differentiate itself in the market.
- Long-Term Viability - adapt to changing requirements and tech advancements.

**Balancing QAs** 
QAs often interact in complex ways & trade-offs may be necessary.
- Performance Vs. Security: security measures like encryption introduce processing overhead.
- Scalability Vs. Maintainability: a highly scalable architecture might require complex configurations that could complicate maintenance efforts.
- Usability Vs. Security - Balancing user-friendly interfaces and necessary security protocols.

#### Performance
How efficiently a software system responds to requests and processes data. 

**Key aspects** 
- *Latency*: delay between a request being sent and a response being received. (initial delay)
- *Response time*: time taken by the system to respond to user request. (initial delay + processing & transmission time)
- *Throughput*: number of transactions/requests processed in a given time period.
- *Resource utilization*: amount of resources (CPU, mem, disk, I/O, bandwidth) used to perform tasks. 

**Measuring Performance** 
- Load Testing - simulating a high volume of requests to evaluate the system under stress. tools: Apache `JMeter`, `LoadRunner`.
- Benchmarking: comparing the system's performance against predefined standards or other systems.
- Monitoring Tools: Real time, tools: New Relic, Grafana., provide insights to performance, enabling proactive identification of bottlenecks or issues.

**Performance Optimization Techniques** 
- Caching: can significantly improve response time for read-heavy apps.
- Load Balancing: distributing requests across multiple servers. (better throughput and availability)
- DB Optimization: Indexing, query optimization and partitioning.
- Asynchronous processing: allowing tasks to run in the background and free resources and handle user requests more efficiently.
- Code Optimizations: review and refactor code to eliminate inefficiencies, reduce complexity and enhance performance.
- Compression and Minification 
- Performance monitoring and Profiling

**Trade-offs and Challenges** 
- Cost Vs. Performance: high performance HW increases cost
- Performance Vs. Maintainability: highly optimized can become difficult to maintain.
- Scalability Vs. Performance: ensure performance optimization changes don't hinder system's ability to scale.

#### Scalability
System's ability to handle increased load without compromising performance.

**Types of Scalability** 
1. **Vertical Scalability**(scaling up): adding more power (CPU, RAM, Storage) to a single server to improve performance.
	- Advantages: Simpler architecture and Easier to manage.
	- Disadvantage: limited by the maximum capacity of a single machine. and potentially higher costs for high performance hardware.

2. **Horizontal Scalability**(scaling out): adding more servers to distribute the load. 
	- Advantages: greater flexibility to handle large-scale apps, cost effective as commodity HW can be used,
	- Disadvantages: Increased complexity in managing distributed systems, requires effective load balancing and data synchronization strategies.

**Measuring Scalability** 
- Load Capacity - max (users/ transactions) the system can handle before performance degrades.
- Response time under load - how RT changes as load increases
- Cost efficiency - cost associated with scaling up or out relative to performance gains.

**Scalability Design Considerations** 
- Decoupling components: systems with loosely coupled components allow parts to scale.
- Microservices architecture: can facilitate *scaling out*, w/c allows services to be deployed and scaled independently.
- Load Balancing: preventing a single server from becoming a bottleneck
- Caching strategies: effective caching can reduce load on back-end systems.
- Database `Sharding`: distributing data across multiple DBs or shards can improve performance and scalability, allowing for parallel processing of requests.

**Challenges and Trade-offs** 
- Complexity - scaling can introduce complexities in architecture.
- Cost - additional costs for infra and management, particularly in cloud environments.
- Performance - ensuring high availability and scalability may compromise performance as latency increases due to data replication.

#### Reliability
A system's ability to consistently perform its intended function without failure over a specific period. Critical to ensure user trust and satisfaction, especially in mission critical applications.

**Key Aspects** 
1. Uptime - percentage of time the system is operational and available for use.
2. MTBF - avg time between failures
3. MTTR - avg time taken to recover from failure
4. Fault Tolerance - ability of a system to continue operating correctly in the event of a failure. detect failures and switch to backups.

**Measuring Reliability** 
- **Availability** - e.g. (99% uptime), quantifies how often a system is operational
- **Failure Rate** - frequency of failures over a specific period.
- **Redundancy Testing** - regularly testing backup systems and failover procedures.

**Strategies for Enhancing Reliability** 
- Redundancy - redundant components e.g. servers, DBs, that ensure failover safety.
- Graceful Degradation - designing a system to maintain a limited functionality when a certain component fails
- Regular Backups - prevent data loss
- Health Monitoring - solutions to continuously check health and alert potential issues.
- Automated Recovery - using automation tools to restart failed services or redirect traffic to backup servers

**Challenges and Trade-offs** 
- Cost - redundant systems can increase initial cost
- Complexity - redundancy and failover mechanisms can complicate architecture
- Performance - ensuring reliability may require additional resources or processing.

#### Security
Measures and practices designed to protect a software system from unauthorized access, attacks and data breaches.

**Key aspects** 
1. **Confidentiality** - sensitive data is accessible to only authorized users. Encryption and access control help.
2. **Integrity**: guarantees data is accurate, consistent and hasn't been tampered with. e.g. Hashing.
3. **Availability**: ensures authorized users have timely access to data and resources. Threatened by DOS attacks.
4. **Authentication**: verifies identity of user or systems attempting to access resources. e.g. MFA.
5. **Authorization**: verifies the permission and access levels for authenticated users. e.g. RBAC
6. **Non-Repudiation**: assurance that a user can not deny the authenticity of their actions, often achieved through logging and audit trails.

**Measuring Security** 
- Vulnerability Assessments: with tools like OWASP ZAP or Nessus to identify potential weaknesses.
- Incidental Response Time: time taken to detect and response to security incidents,
- Penetration testing: conducting simulated attacks to identify vulnerabilities.

**Strategies for Enhancing Security** 
- Secure SDLC: integrating security practices throughout SDLC to ensure security is considered at every stage of development.
- *Encryption*: to sensitive data at both rest and in transit
- *Regular Security Audits*: to identify and remediate vulnerabilities proactively.
- *Access Control*: limit user permissions and prevent unauthorized access.
- *Security Awareness Training* - educating developers and users on best practices and potential threats.

**Challenges** 
- Complexity: robust security can add complexity to the system, potentially impacting usability and performance.
- Cost: security tools, training and practice may require resources
- Usability: user convenience can be affected by stronger security.

#### Usability
Measures how effectively and efficiently users can interact with a system to to achieve their goals.

**Key Aspects** 
1. Learnability: The ease which new users can understand and use the system.
2. Efficiency: how quickly users can perform tasks once they are familiar with the system.
3. Memorability: ability of users to remember how to use the system after not using it for a while.
4. Error Management: how well the system handles user errors. clear error messages, guidance to recovery and ability to undo actions make for a good error management.
5. Satisfaction: overall enjoyment and perceived value users experience when interacting.

**Measuring Usability** 
- *User Testing*: observing users to identify pain points and areas for improvement.
- *Task Success Rate*: percentage of successful tasks during testing.
- *Time on Task*: time to complete a specific task, to see efficiency.
- *System Usability Scale (SUS)*: a standardized questionnaire that provides a quick assessment of usability by gauging user perceptions.

**Strategies for Enhancing Usability** 
- User-Centered Design: involving users in design process, personals, scenarios, usability testing.
- Consistent Interface Design: for more intuitiveness.
- Clear Navigation: designing straightforward navigation and information architectures.
- Feedback Mechanisms: providing immediate feedback during interaction.
- Accessibility Considerations: usable by people with disabilities.

**Challenges and Trade-offs** 
- Features Vs. Usability - adding features can sometimes complicate the UI
- Cost and Time constraints - usability testing and iterations can require additional resources
- Diverse user needs - different needs and expectations -> no one-size-fits-all solution.

#### Maintainability
Measures how easily a system can be modified or repaired. to ensure a system ca  adapt to changing requirements, fix defects, and incorporate new features with minimal effort and cost.

**Key Aspects** 
1. **Modularity**: degree to w/c components can be separated and recombined. allows each to be updated and replaced without impacting the system.
2. **Code Readability**: clarity and comprehensibility of the codebase. 
3. **Testability**: ease with which it can be tested to ensure functionality. unit, integration & regression testing.
4. **Documentation**: comprehensive and up-to-date Docs.
5. **Change Management**: processes and tools used to manage changes to the system effectively.

**Measuring Maintainability** 
- *Cyclomatic Complexity*: Measures complexity of a program based on the number of linearly dependent paths through its source code. Lower CC means good maintainability.
- *Code Churn*: the percentage of code that changes over time. to identify areas that may require more attention for maintainability.
- *Defect Density*: number of defects relative to the size of the software.
- Time to Implement Changes: can provide insight into its maintainability.

**Strategies for Enhancing Maintainability** 
- Use of Design Patterns: can enhance code reusability and clarity
- Consistent Coding Standards: promotes uniformity across the codebase and improve readability and reduce confusion.
- Refactoring: regularly refactoring to improve its structure and clarity to reduce T. debt.
- Automated Testing: for quick verification of changes.
- CI/CD: to ensure changes are integrated and depleted frequently, w/c makes it easier to identify issues early.

**Challenges and Trade-offs** 
- Initial Development Time - investment in creating modular and maintainable architectures.
- New Features vs. Maintenance - prioritizing new features may lead to neglecting maintenance activities.
- Legacy Systems - maintaining older systems can be challenging due to outdated tech and practices.


###  Case Studies
**Successful Architecture Examples
1. **Netflix**:
	- **Architecture Type**: Microservices
	- **Overview**: Transitioned from a monolithic architecture to a microservices approach to enhance scalability and resilience.
	- **Benefits**:
		 - **Improved Fault Isolation**: Individual services can fail without affecting the entire platform.
		 - **Enhanced Scalability**: The platform can handle millions of concurrent users globally.
		 - **Faster Deployment Cycles**: Enables rapid deployment of new features with minimal downtime.

2. **Amazon**:
	- **Architecture Type**: Service-Oriented Architecture (SOA)
	- **Overview**: Supports the vast e-commerce platform through a service-oriented approach, allowing different teams to develop and deploy services independently.
	- **Benefits**:
		- **High Scalability and Flexibility**: Services can be reused across different applications and support rapid innovation.
		- **Continuous Innovation**: Teams can quickly adapt to market changes and develop new features.
		- **Resource Efficiency**: Reduces redundant work by reusing services.

3. **Spotify**:
	- **Architecture Type**: Microservices with Agile Practices
	- **Overview**: Combines microservices architecture with Agile methodologies to foster innovation and rapid feature development.
	- **Benefits**:
		- **High Availability and Resilience**: Independent service deployments ensure high availability.
		- **Empowered Teams**: Cross-functional teams (squads) take ownership of services, promoting accountability and faster iterations.
		- **Enhanced User Experience**: Continuous delivery of features and improvements provides better user experience.

**Lessons from Failed Architectures** 
1. **Healthcare.gov**:
	- **Overview**: The launch of the U.S. government's healthcare marketplace in 2013 faced numerous technical failures.
	- **Issues**:
		- **Monolithic Architecture**: The system was built as a monolithic application, making it difficult to scale and prone to single points of failure.
		- **Lack of Load Testing**: Insufficient load testing led to crashes during high traffic, as the system was not prepared for the number of users.
		- **Lessons Learned**:
			- Emphasize modular design to enhance scalability and resilience.
			- Conduct thorough load testing before deployment to ensure the system can handle expected traffic.

2. **Target’s Payment System Breach**:
	- **Overview**: In 2013, Target experienced a major data breach due to vulnerabilities in its payment processing architecture.
	- **Issues**:
		- **Inadequate Security Measures**: The architecture lacked robust security layers and monitoring, allowing sophisticated attacks to go undetected.
		- **Poor Integration of Systems**: The integration between various systems (e.g., point-of-sale and payment processing) was not secure, leading to data exposure.
		- **Lessons Learned**:
			- Prioritize security in architectural design, including encryption and secure communication between systems.
			- Implement comprehensive monitoring and alerting to detect anomalies and potential breaches early.

3. **Knight Capital Group**:
	- **Overview**: In 2012, a software glitch in Knight Capital's trading system led to a $440 million loss in just 45 minutes.
	- **Issues**:
		 - **Insufficient Testing**: The deployment of untested code into a live environment caused catastrophic failures.
		 - **Complexity of the Architecture**: The architecture was too complex, making it difficult to trace and understand the impact of changes.
		- **Lessons Learned**:
		 - Establish rigorous testing protocols before deploying changes to production environments.
		 - Simplify architecture where possible to enhance understanding and reduce the risk of errors.

### Tools and Techniques for Architectural Design
#### Modeling Tools
1. **UML** Tools: e.g. Lucid chart, Visual Paradigm, Start UML. provide class, sequence, use case diagrams, tor represent components, interactions and workflows.
2. **Enterprise Architect**: supports UML and other modeling standards. features for req. mgmt., project mgmt. & code generation.
3. `Archimate`: a modeling language designed for enterprise Architecture, to visualize relationships across business processes, ISs, and tech infra. provides a holistic view of Arch.
4. **C4 Model**: a framework for visualizing software Arch. at different levels of detail (context, container, component & code). Simplifies communication of Arch.
5. **Draw.io/ Diagrams.net**: to create flowcharts, net. diagrams, and others.

#### Documentation Tools
1. **Confluence**: a collaboration tool to create, share and organize docs. Supports rich text formatting, templates, VC, and integration with external tools.
2. **Markdown Editors**: (e.g. `Typora`, Dillinger), simple syntax & easy to export to HTML or PDF.
3. **Read the Docs**: a docs hosting platform that simplifies the creation and publishing of docs for software projects. Supports VC, search, and integration with git repos.
4. **Swagger/`OpenAPI`**: a framework for documenting API specs & allows for interactive API docs. provides tools for testing APIs directly from Docs.
5. **Google docs**: for real-time collaboration and sharing. comments, suggestions and Version history.

#### Evaluation Techniques
For assessing the quality and effectiveness of software architecture. help architects identify potential issues, validate design decisions, and ensure that the architecture meets FR and NFRs.

1. **Architectural Tradeoff Analysis Method (ATAM)**: for evaluating architectural decisions based on trade-offs between quality attributes.
	- involves defining scenarios and analyzing the impact of Arch. decisions on QAs.
2. **Architecture Review**: assessment of Arch. by a group of stakeholders. Involves presenting the Arch. design, discussing strengths and weaknesses and gathering feedback.
3. **Scenario-Based Evaluation**: evaluating the Arch. against specific usage scenarios.
	- we create use-cases and scenarios that represent typical user interactions and assess the architecture's performance in those contexts. (real-world usage)
4. **Prototyping**: to explore architectural ideas and validate design assumptions. allows for early identification of design flaws.
5. **Performance Testing**: under various loads to ensure it meets scalability and responsiveness requirements. Load, stress and scalability tests, to identify bottlenecks.
6. **Code Review and Static Analysis**: to assess code quality, adherence to Arch. guidelines & find potential vulnerabilities.

### Future Trends in Software Architecture
#### 1. Cloud-Native Architecture
An end-to-end design methodology built to exploit cloud platforms for maximum agility, resilience, and scale.
* **Core Mechanisms:** Encapsulates workloads using containers (Docker, Kubernetes), leverages serverless execution, and relies on provider-managed services for auxiliary systems (databases, identity).
* **Operational Impact:** Embeds DevOps and CI/CD pipelines directly into workflows, allowing autonomous services to auto-scale dynamically and self-heal from infrastructure failures.

#### 2. Microservices Architecture
An approach that breaks monolithic systems into small, independent, and loosely coupled services organized around specific business capabilities.
* **Core Characteristics:** Services communicate through standard APIs, maintain decentralized data ownership, and allow polyglot technology stacks tailored to individual requirements.
* **Operational Impact:** Prevents cascading system failures through fault isolation, enables continuous delivery with minimal downtime, and allows fine-grained scaling of individual bottlenecks rather than entire applications.

#### 3. Serverless Computing
A development model that abstracts server provisioning, maintenance, and capacity planning entirely to cloud providers.
* **Core Characteristics:** Relies on event-driven execution, running code only when triggered by incoming events (e.g., HTTP requests, database events).
* **Operational Impact:** Eliminates idle capacity costs through true pay-per-use pricing, scales workloads elastically to zero or peak instantly, and frees engineering teams to focus solely on business logic and rapid iteration.

**Challenges** 
- cold start latency
- limited execution time
- vendor lock in

#### 4. AI driven software Architecture 

#### 5. Edge computing
#### 6. Blockchain based Architecture
#### 7. Quantum computing impact
#### 8. Autonomous cloud infrastructure

