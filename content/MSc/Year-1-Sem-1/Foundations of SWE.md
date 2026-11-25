Foundations of Software Engineering 
# CH1: SDLC

### Intro to SDLC
Importance of SDLC
- Structured Approach
- Improved Quality
- Risk Management - early identification and management of risks(uncertainty)
- Enhanced Communication - b/n stakeholders by defining roles and responsibilities.
- Clear Documentation - for maintenance and future updates.
- Facilitates Project Management

**Overview of SDLC Phases** 
1. *Requirement Gathering*: stakeholders, users and clients collaborate to identify requirements. using d/t techniques (interview, survey & questionaries, workshop, use cases, prototyping).
2. *Design*: requirements are translated into a blueprint. incl. high level arch. and detailed design specs. we may use design patterns.
	- Architectural Design: sys. arch., component identification, tech. stack, interaction design, scalability and performance.
	- Detailed design: component specification, UI design, data design, design patterns, documentation.
3. *Implementation*: write code based on the design specs. includes setting up dev. env. and adhering to coding standards.
	- coding practices: standards, modular programming, code reviews, error handling, version control.
	- Env. setup: dev. tools, config management, dependency management, CI/CD.
4. *Testing*: identifying defects and ensuring we met the requirements. unit, integration, system, acceptance testing.
	- importance: QA, Risk mitigation, user satisfaction, cost efficiency, compliance and security
5. *Deployment*: production env., phased rollouts? complete launch...
	- strategies: full, phased, parallel, canary(small user), blue-green (2 env.)
	- release mgt.: release planning, user training, monitoring and feedback, rollback procedures
6. *Maintenance*: monitoring and updating, legacy systems and technical debt are problems here.
	- types: corrective, adaptive, perfective, preventive
	- challenges: legacy systems, technical debt, evolving user expectations, inadequate/ outdated documentation.


### Models of SDLC
##### Waterfall Model
Earliest and most straightforward model. linear and sequential approach. 
**Characteristics** 
- Linear Process
- Documentation - extensive from each phase
- Strict Requirements - R. gathered upfront and expected to remain stable throughout. changes can be challenging.
- Best suited for small projects
- Limited Flexibility
- Testing at the End

##### Agile Model
Emphasizes flexibility, collaboration and customer satisfaction. through iterative development and frequent reassessment of project direction.
**Principles**
- Iterative and Incremental
- Customer Collaboration
- Adaptability
- Cross-Functioning Teams - multiple disciplines collaboration
- Continuous Improvement - regular reflection and adaption

**Iterative Process** 
- *Sprints* - teams deliver specific features, enhancements and bug fixes.
- *Backlog Management* - maintain backlog - a list of prioritized features, enhancements and bug fixes.
- *Daily Stand-ups* 
- *Demonstrations* - at the end of each sprint for stakeholders for feedback.

##### Spiral Model
Risk-driven process that combines both iterative and waterfall models. effective for complex projects where risk management is critical. 
**Risk Assessment** 
- Iterative Cycles: each contain - planning, risk analysis, engineering, engineering and evaluation.
- Risk management: at end of each spiral potential risks are identified, analyzed, and mitigated.
- User Feedback: users provide feedback at the end of each iteration. 
- Prototyping
- Flexibility - accommodates changes in requirements at any stage of development.
- Documentation - Each phase of the spiral generates documentation.
**Applications** 
- Large and Complex projects - iterative allows to break down the development 
- High-Risk projects
- Long-Term projects - iterative cycles facilitate refinement and adaptation.

##### V-Model
AKA Verification and Validation model. is an extension of Waterfall model that emphasizes relationship between development and testing phases.
**Verification and Validation** 
- *Development phases*: left side. incl. req. analysis, sys, arch & module design, and coding.
- *Testing phases*: right side. 
	- unit testing - aligns with module design and coding
	- integration testing - for architecture design
	- system testing - for system design, complete system against req.
	- acceptance testing - with req. analysis, ensures it fulfills user needs.
**Key Characteristics** 
- Emphasis on testing
- Clear Structure
- Early Detection of defects
- Documentation

**Application** 
- Projects with Well-Defined Requirements - finance, healthcare, aerospace where compliance is critical.
- Short to Medium-Scale Projects - although can be applied to large projects too



# Notes
Unit Testing: Aligns with module design and coding
Integration Testing: Corresponds to architectural design
System Testing: Relates to system design. 
Acceptance Testing: Matches with requirements analysis


Objectives of Requirements Analysis
Clarity
Completeness
Feasibility

Techniques for conflict resolution:
Prioritization
Negotiation
Traceability

Formal Methods for Documenting Requirements
Requirements Specification Document (RSD):typically organized by functional and non-functional requirements.
Business Requirements Document (BRD): Focuses on the high-level business 
Functional Requirements Document (FRD): Details the specific functionalities that the system must provide, often including use cases or user stories.

Each use case typically includes:
    Title
    Actors 
    Pre-conditions
    Main flow of events (the steps taken by the actor and the system)
    Post-conditions (the state of the system after the use case is completed)

Popular Requirements Management Tools
	JIRA: 
	IBM Engineering Requirements Management DOORS:
	Helix RM: 

Key Components in a Software System
    Modules: 
    Services: 
    Databases:
    User Interfaces: 
    APIs:


Interactions Between Components
    Data Flow: 
    Control Flow:
    Event-Driven Interactions: 
    Synchronous vs. Asynchronous Communication: 
    Error Handling:


Microservices - independent services, decentralized data mgt., independent deployment
- scalable, flexible, fault isolation, faster time to market
- complex, data mgt. challenges, Network latency


Event Driven - loose coupling, async comms., event sourcing(storing)-to reconstruct its state by replaying events.
- event producer, consumer and channel, maybe a store


Key Elements of Component Specifications
	Functionality:
	Interfaces: 
	Data Structures:
	Error Handling: 
	Performance Requirements:
	Security Considerations: 
	Testing Criteria: 

Key Components of Design Documents
	Overview and Purpose
	UML Diagrams - class and sequence
	Component Specifications - FR, interfaces, DS
	Architecture Diagrams
	Data Flow Diagrams
	Design Rationale
	Non-Functional Requirements
	Testing Strategies


Components of Sequence Diagrams:
    Actors: 
    Lifelines: 
    Messages:

CXs of *Singleton* Pattern - private constructor, static instance variable, static method for access
	Single Instance
	Global Access Point
	Lazy Initialization 
use cases - config mgt., logging, resource mgt.

*Observer* - loose coupling, dynamic r/n, event driven
- flexible, decoupled
- memory leaks, complex notification logic

Key Characteristics of the *Factory* Pattern - loose coupling, SRP, complex
	Encapsulation of Object Creation: 
	Flexibility in Object Creation: 
	Substitution of Concrete Classes:

Key Characteristics of the *Strategy* Pattern - flexible, separation of concerns, easy maintenance, complex, client awareness
	Encapsulation of Algorithms: 
	Interchangeable Strategies: 
	Open/Closed Principle: 
use case - sorting algo, payments, compression algo.

*Command* pattern - encapsulates a request as an object, decouples sender (invoker) from receiver.
CHRXS & advantage
	Encapsulation of requests
	Decoupling
	Support for Undo
	Flexible
DIS - complex, overhead of command creation



Procedural - modularity, state mgt with variables, control structures (loops, if)
- C, pascal - low level programming, performance, scripting for automation

OOP - PIE, C++, java, python - large-scale apps, game dev, GUI

Functional - (mathematical functions) - functions as first class citizen, immutability and statelessness. - Haskell, Scala, Erlang
- `chrxs`: first class functions, Immutability, pure functions
- use: data analysis, parallel programming, domain specific languages..

Scripting languages - Interpreted, dynamic typing, ease of use - python, JS, Ruby
- use: client and server side scripting, automation, data manipulation 

Programming Paradigms
- OOP
- Functional
- Procedural
- Declarative - high level abstraction, what not how
- Event driven - responding to events. - event handlers and callbacks.

Importance of Coding Standards
	Readability
	Maintainability
	Collaboration
	Error Reduction
	Documentation
	Professionalism

Coding Standards
	Naming Conventions
	Indentation and Spacing
	Commenting
	Code Structure and Organization
	Error Handling
	Formatting

Best Practices
	DRY
	KISS
	YAGNI
	Code reviews
	Automated testing
	Version control
	CI/CD
	Documentation


Version Control
	Tracking Changes
	Collaboration
	Backup and Recovery
	Branching and Merging
	Auditing and Accountability

CVCS - Single Point of Failure, simple, real-time collaboration, e.g. SVN, CVS
DVCS - offline work, enhanced collaboration, backup. e.g. git, mercurial

Benefits of Using IDEs:
	Increased Productivity:
	Enhanced Code Quality:
	Easier Collaboration:
	Learning Curve: 


Debugging
	Print debugging
	Interactive debugging
	Automated testing
	Code reviews
	Logging
	Static code analysis
	Memory and performance profiling


Techniques for Integration Testing:
    Top-Down Integration Testing: lower-levels are simulated using stubs.
    Bottom-Up Integration Testing: Drivers are used to simulate higher-level 
    Sandwich (Hybrid) Integration Testing:
    Big Bang Integration Testing:
    Incremental Integration Testing:

System testing: end-to-end testing, Functional & NF testing
Types: Functional, performance, usability, security, compatibility, regression, acceptance(UAT & operational acceptance).

Test techniques
Manual Testing
- Plan, Test case design, Execution, Defect report, retest
Automated Testing - efficient, consistent and accurate, more coverage, cost effective in the long run, facilitates CI/CD
Black box testing - testing based on requirements. simulates real world.
- functional testing, system and acceptance testing, regression testing.
- inefficient for complex apps, limited coverage of code paths
White box testing - high coverage & path testing, control flow & data flow testing

Coverage - statement, branch, function, condition coverages.

Q. metrics - Defect density, code coverage, cyclomatic complexity (number of linearly independent paths through the code), Mean time to failure (MTTF), customer reported defects, test pass rate, response time

Testing Challenges
Identifying Test Cases
- Ambiguous Requirements
- Complexity of the Application
- Changing Requirements
- Limited Resources
Managing Test Environments
- Environment Configuration
- Availability of Resources
- Data Management
- Integration Issues


Software Maintenance Lifecycle
	Identification of Maintenance Needs
	Impact Analysis
	Planning
	Implementation
	Testing
	Deployment
	Documentation
	Review and Feedback

Legacy Systems
	Outdated Technology
	Integration challenges
	High maintenance cost
	lack of documentation

- Increased Complexity
- vulnerabilities
- Resource availability
- performance issues
- compliance
- Resistance to change


Challenges in maintenance - Technical debt, Legacy systems, Resource allocation 

Maintenance strategies - VCS, documentation, Testing in Maintenance

PM - resource optimization, risk mitigation, quality assurance, stakeholder engagement, flexibility, documentation, 


*Lean methodology* focuses on maximizing value by minimizing waste. It emphasizes efficiency, continuous improvement, and delivering value to customers.
Principles:
    Eliminate waste, build quality in, and empower the team.
Advantages:
    Streamlined processes and increased efficiency.
    Continuous feedback leads to improved quality.
Disadvantages:
    Requires a cultural shift in organizations.
    May not provide enough structure for larger projects.

Importance of Planning in Software Projects
- Clarifies Objectives
- Resource Allocation
- Risk Management
- Time Management
- Stakeholder Communication
- Performance Measurement
- Facilitates Change Management
- Documentation and Accountability

Estimating Resources, Time, and Costs

specific, measurable, achievable, relevant, and time-bound (SMART).

Key Components of a Project Scope Statement
    Project Objectives:
    Project Deliverables
    Project Requirements:
    Project Boundaries:
    Assumptions and Constraints:
    Stakeholders:
    Acceptance Criteria:
    Change Management Process:

Importance of Developing a Project Scope Statement?

Techniques for Creating Project Timelines
	Work Breakdown Structure (WBS)
	Gantt Charts
	Critical Path Method (CPM) -> float/slack time
	Program Evaluation and Review Technique (PERT)
	Milestone Charts
	Dependency Diagramming
	Agile Iteration Planning

Time Tracking Tools: Toggl, Harvest, or `Clockify` 

SWOT (Strengths, Weaknesses, Opportunities, Threats) 

Analyzing and Prioritizing Risks
	Qualitative Risk Analysis:
	Quantitative Risk Analysis:
	Risk Prioritization
	Regular reviews and update

Risk Response Strategies
	Avoidance
	Mitigation
	Transfer
	Acceptance
	Contingency Planning

Agile Principles 
	Individuals and Interactions Over Processes and Tools
	Working Software Over Comprehensive Documentation
	Customer Collaboration Over Contract Negotiation
	Responding to Change Over Following a Plan

Key Principles of Agile Methodologies
    Iterative Development: 
    Continuous Improvement:
    Customer Feedback: 
    Cross-Functional Teams: 
    Simplicity: 
Key Components of the Scrum Framework
    Roles:
        Product Owner:
        Scrum Master:
        Development Team:
    Artifacts:
        Product Backlog:
        Sprint Backlog:
        Increment:
    Ceremonies:
        Sprint Planning:
        Daily Scrum:
        Sprint Review:
        Sprint Retrospective:


Kanban
Key Principles of Kanban
    Visualize Work:
    Limit Work in Progress (WIP):
    Manage Flow:
    Make Process Policies Explicit:
    Feedback Loops:
    Continuous Improvement:

Advantages of Kanban
    Flexibility: 
    Improved Visibility: 
    Reduced Lead Time: 
    Empowered Teams:

Tracking Project Progress and Performance
	Establishing Baselines
	Using Key Performance Indicators (KPIs)
	Regular Status Meetings
	Project Management Software
	Change Management Process
	Risk Monitoring

Common KPIs
	Schedule Variance SV = Earned Value (EV) - Planned Value (PV)
	Cost Variance CV = Earned Value (EV) - Actual Cost (AC)
	Burn Rate   Burn Rate = Actual Cost (AC) / Time Period
	Cost Performance Index  CPI = Earned Value (EV) / Actual Cost (AC)
	Schedule Performance Index (SPI) SPI = Earned Value (EV) / Planned Value (PV)
	Quality Metrics
	Customer Satisfaction

Steps for Closing a Project 
	Confirm Project Deliverables
	Conduct Final Project Review
	Obtain Formal Acceptance
	Release Project Resources
	Document Lessons Learned
	Finalize Project Documentation
	Conduct a Post-Mortem Analysis
	Celebrate Success

Documentation and Knowledge Transfer
    Types of Documentation:
        Project Closure Report: 
        Lessons Learned Repository:
        Final Project Documentation:
    Knowledge Transfer Techniques:
        Workshops and Training Sessions:
        Mentorship Programs: 
        Internal Communication Channels: 

Key Impacts of DevOps on PM
	Enhanced Collaboration - Cross-Functional Teams & enhanced comms.
	Continuous Integration and Continuous Delivery (CI/CD):
	Focus on Customer Value
	Improved Risk Management
	Cultural Shift
	Integration of Agile Practices

Integration of Artificial Intelligence 
	Automated Task Management
	Predictive Analytics:
	Enhanced Resource Management
	Improved Communication and Collaboration:
	Sentiment Analysis:
	Intelligent Reporting:
	Continuous Learning and Improvement:
	Facilitating Agile Practices:

Challenges and Considerations with AI
    Data Quality and Integration:
    Change Management:
    Ethical Considerations:
    Cost of Implementation:

Key Impacts of Remote Work on Project Management
    Changing Communication Dynamics:
    Increased Focus on Collaboration Tools:
    Flexibility and Work-Life Balance:
    Performance Monitoring and Accountability:
    Cultural Considerations:
    Challenges in Project Coordination:
    Adaptation of Agile Practices:


Future Directions in Project Management Methodologies
	Increased Adoption of Hybrid Methodologies
	Greater Emphasis on Data-Driven Decision Making
	Focus on Sustainability and Social Responsibility
	Enhanced Collaboration Through Technology
	Evolving Role of Project Managers
	Integration of Artificial Intelligence and Automation
	Continuous Learning and Adaptation


Key Ethical Principles:
	Honesty: 
	Integrity: 
	Fairness: 
	Respect for Privacy: 
	Professional Competence: 

GDPR Key Provisions
    Right to Access
    Right to Rectification:
    Right to Erasure (Right to be Forgotten):
    Data Portability:
    Consent Requirements: 


CCPA Key Provisions:
    Right to Know: 
    Right to Delete: 
    Opt-Out Option: of the sale 
    Non-Discrimination: against consumers who exercise their rights under the CCPA.


Best Practices for Safeguarding Sensitive Information
	Data Encryption
	Access Control
	Secure Coding Practices
	Data Minimization
	Regular Security Testing
	Data Backup and Recovery
	User Education and Awareness

Importance of Intellectual Property Rights 
	Encouraging Innovation
	Protecting Competitive Advantage
	Facilitating Collaboration
	Legal Compliance

Permissive Licenses (e.g., MIT, Apache)
Copyleft Licenses (e.g., GNU GPL)

Trends in Software Development Tools
	AI and Machine Learning Applications
	Low-Code and No-Code Development
	DevOps and Continuous Everything
	Cloud-Native Development
	Enhanced Collaboration Tools
	
Common IaC Tools:
    Terraform: 
    Ansible: 
    CloudFormation: 

Monitoring and Logging Tools
    Prometheus: 
    Grafana: 
    ELK Stack (Elasticsearch, Logstash, Kibana):






