---
title: Software Design and Architecture
---
# CH-1: Intro
**SDLC**: 
Ideation -> Requirements -> Design -> Development -> Testing -> Deployment -> Maintenance

### Software Design
Design - Work in deriving and specifying a solution to a problem.
- b/c there might be multiple solutions, correctness/ appropriateness is used to measure the fitness.
- *The solution* is a description of how the requirements(*problem*) are met.

The design process consists of 4 activities
1. Postulate a solution
2. Build a model of the solution
3. Evaluate the model against original requirement.
4. Elaborate the model to produce a detailed specification of the solution

The design process is iterative in nature and contains an extensive backtracking.

The design describes the system well enough that coders can build and deploy it without problems. It contains a set of documents (diagrams and text).

### Design Concepts
Design concepts provide software designers with basic ideas from which more sophisticated design methods can be applied.
The fundamental concepts in software design are:
- Abstraction
- Modularity
- Refinement
- Architecture

##### Abstraction
allows designers to focus on solving a problem without being concerned about irrelevant low level details. (only essentials and no implementation details)
- Each step in the software design process is a refinement in the level of abstraction of the solution.

Abstraction Methods in OOP:
- Encapsulation
- Information Hiding 
- Inheritance
- Polymorphism and dynamic binding

##### Modularity
the degree to w/c a software can be understood by examining its components independently from one another.
A module is a named entity that:
- contains instructions, logic and data structures
- can be compiled and stored in a library
- segments of it can be used by invoking a name and some parameters
- they can use other modules

Module - an independent software unit, has various physical units (files).

Quality Attributes of a Module:
- well defined
- separation of concerns
- loosely coupled - measure if relative interdependence among modules
- cohesive - a measure of relative functional strength of a module

**Coupling Range** - low to high, loose in the middle
- Uncoupled -> Data(only primitive types) -> Stamp -> control -> common -> content

| Coupling Type  | Strength        | Key Characteristic                           | example          |
| :------------- | :-------------- | :------------------------------------------- | ---------------- |
| **Uncoupled** | None (Best)     | No dependency                                | NA               |
| **Data**      | Lowest          | Simple parameters passed                     | int              |
| **Stamp**     | Low             | Complex structure passed, only part used     | Cust.id,         |
| **Control**   | Medium          | One module dictates logic flow of another    | flags            |
| **Common**    | High            | Shared global data structure                 | common object,DB |
| **Content**   | Highest (worst) | One module modifies internal data of another | local variable   |

**Cohesion** - all elements of a component toward a single task and those elements are contained in a single component.
Range of cohesion: low to high
- Coincidental - logical(share logic) - temporal(same time) - procedural(order) - communicational(data) - sequential(one's output to another input) - functional info (parts of the same function)

| Type of Cohesion         | Example                                                                                                                              |
| :----------------------- | :----------------------------------------------------------------------------------------------------------------------------------- |
| **Coincidental** (Worst) | A `Utility` class containing unrelated methods like `Validate_Email()`, `Calculate_Loan()`, and `Print_Report()`.                    |
| **Logical**              | A single `Handle_IO(type)` function that reads data from a **disk, network, or keyboard** based on the `type` flag.                  |
| **Temporal**             | An `Initialization()` module that calls: `reset_counters()`, `open_log_files()`, and `connect_to_database()`.                        |
| **Procedural**           | A module that first `check_user_credentials()`, and then `log_session_start()`.                                                      |
| **Communicational**      | A module with functions `get_name(Customer)` and `get_address(Customer)`, both operating on the `Customer` record.                   |
| **Sequential**           | A function where `Read_Raw_Data()` feeds its output into `Validate_Data()`, which feeds its output into `Format_Data()`.             |
| **Functional** (Best)    | A module with a single function, `Calculate_Square_Root(number)`, which contains all the necessary internal logic for that one task. |

A Good Architecture:
- minimizes coupling - easier future changes
- maximizes cohesion of each module (inter-related) - easier to understand

**Advantages of modularity**:
- understandability
- parallel development of modules is possible
- higher design quality b/c of easy: testing, validation, measuring reliability, maintainability, reusability

#### Refinement
The designer provides more detail for each design component.
- Start with a high-level function, then use top-down, stepwise refinement to decompose it.
- Incrementally add details while isolating dependencies and postponing low-level representation decisions. 
- Ensure each step is a correct expansion of the previous.

Abstraction and refinement are complementary concepts.
- One hides low-level details, enabling high-level specification, while the other progressively reveals those details.

#### Architecture
- Provides overall structure and ways in w/c that structure provides conceptual integrity for the system. It is a framework for more detailed design activities.


### Common Design Principles
- when applied properly, the software engineer creates a design that shows both external and internal quality factors.

*External Quality Factors* - can be observed by the user, e.g. speed, usability
*Internal Quality Factors* - seen from technical perspective (operations of the app), e.g. maintainable, testable, reusability

1. Considerations of *alternative approaches* - decisions must be made based on requirements, resources and design concepts.
2. The design should be *traceable* to the analysis model
3. The design should not *reinvent the wheel* 
4. Reduced *intellectual gap* between software and the problem (structure of the design should reflect the structure of the problem domain)
5. The design should exhibit uniformity and integration
6. design should be able to be restructured to accommodate change (maintainability)
7. Quality assessment must be done to the design during development
8. A well-designed system should not fail completely when it encounters a problem; instead, it should degrade its performance or functionality in a controlled, non-catastrophic way, allowing it to remain partially operational.
9. Design is not coding and vice versa, abstraction is higher in design
10. The design should be reviewed to minimize conceptual(semantic) errors, (ambiguity, ...)



### Goals of Software design
**Correctness** - satisfies the requirements and performs its intended purpose
**Robustness** - be able to handle miscellaneous and unusual conditions, e.g. bad data, user error ...
**Flexibility** - to accommodate changes to the requirement
**Reusability** - easily modified and reused
**Efficiency** - in machine cycles and memory, this goal may conflict with other goals.
**Reliability** - relatively defect free.
**Usability** - easy to use for the user.


## Software Architecture
Structure of a system, defined by its software elements, their externally visible properties, and the relationships between them.
A software architecture is an abstraction of a system.
- Architecture suppresses purely local information about elements; private details are not architectural.

An element's externally-visible properties are the assumptions other elements can make about it, including its provided and required services, performance characteristics, fault handling, and resource usage.

In the simplest case, a system is composed of a single elements, related only to itself.

In all apps architecture exists, but it only becomes truly useful, manageable, and maintainable when it is formally specified.

An architecture must be represented by multiple structures (views), which are chosen based on what is most useful for analysis, communication, or managing complexity.

#### Architecture as Communication Vehicle
Architecture serves as the central framework for managing and communicating complex project trade-offs.
- Negotiate Interests - users and stakeholders
- Keeps customers informed regarding project progress and costs.
- Foundation for implementing managerial decisions and resource allocations.

#### Architecture Constrains Implementation 
Architectures are descriptive and prescriptive
- descriptive for communication
- prescriptive for design and implementation

System tradeoffs regarding quality attributes are in the architectural realm.

#### Architecture Organizes the Development Project 
Architecture influences the organizational structure for development/maintenance efforts.
e.g. division into teams, budgeting/planning, documentation organization, integration, test plans ...

#### Architecture Permits/Precludes Achievement of Quality Attributes
e.g.

| If you desire (Architectural Goal) | Examine (Architectural Aspect)                                        |
| :--------------------------------- | :-------------------------------------------------------------------- |
| **Performance**                   | Inter-component communication                                         |
| **Modifiability**                 | Component responsibilities                                            |
| **Security**                      | Inter-component communication, Specialized components (e.g., kernels) |
| **Scalability**                   | Localization of resources                                             |
| **Ability to Subset**             | Inter-component usage                                                 |
| **Reusability**                   | Inter-component coupling                                              |

#### Architecture is Key to Managing Change 
Architecture divides all changes into three classes:
*local*: modifying a single component
*non-local*: modifying several components
*architectural*: modifying the gross system topology, communication, and coordination mechanisms
- A “good” architecture is one in which the most likely changes are also the easiest to make.

#### Architecture is Basis for Incremental Development  
Architecture helps with evolutionary prototyping and incremental delivery.
- architecture serves as a framework for components to be plugged in.
- by componentizing, experimentation is easier
- risks can be identified via arch. and mitigated with targeted prototypes

#### Architecture is a Reusable Model
- Since an Architecture is an abstraction it enables one architecture to be used for many systems.
- Architecture is the basis for product commonality.


#### Architecture vs Design
- All architecture is design
- Not all design is architecture
- Architects draw the boundary between architectural and non-architectural designs.

Architecture
- includes principles behind the design and evolution of the software
- characteristics:
	- High level view
	- Realize all the use case scenarios
	- Presents a systematic view to all stakeholders




# CH2: Developing Software Architecture

## Software Architectural Design
The overall structure of a software system. (high level model)
- describes critical aspect of the system
- understandable to many stakeholders
- allows evolution of the system properties before it is built.
- provides tools and techniques for building the system.

Questions during architectural design -
- w/c aspects are architecturally relevant?
- how to represent them most effectively for the stakeholders to understand, reason & communicate about the system before it is built?
- what tools and techniques for implementing an architecture while preserving its properties?

Architecture is about:-
- communication
- "parts" of the system
- how the "parts" fit together?

Architecture is not:- 
- about development
- algorithm
- data structures

### Architectural-Central Design
A shift from focusing only on code-level details (algorithms) to prioritizing the high-level structure and system qualities required by all stakeholders.
It includes critical system-wide concerns:
- Stakeholder issues
- Defining the overarching style and structure
- Determining package/class organization.
- Addressing deployment and post-implementation issues.

**Key Architectural Concepts** 
Three Canonical building blocks:
- Components
- Connectors
- Configurations

A **Component** is an architectural entity that:
- encapsulates a subset of the system's data or function.
- restricts access to an interface.
- has explicitly defined dependencies 

Types of components:
- Computational
- Memory
- Manager
- Controller

A **Connector** a building block tasked with affecting and regulating interactions among components.
It models - interactions among components & rules that govern those interactions.

Simple interactions like procedure calls and shared variable access
Complex and semantically rich interactions like client-server protocols, DB access protocols ...

A **Configuration/Topology** is a connected graph of components and connectors that describes architectural structure.
it controls several essential system properties:
- Proper Connectivity - authorization, logical ...
- Concurrent and Distributed Properties - w/c run simultaneously & spread over multiple systems.
- Adherence to Design Heuristics and Styles - comply with chosen architectural style.


#### Architectural Drivers
Are the small, influential set of requirements that architects identify early on to guide the most crucial, high-impact design decisions.

System requirements:
- Functional needs (what the system should do)
- Quality needs (properties such as availability, performance, security,…)

Design constraints
- Development process
- Technical constraints
- Business constraints
- Contractual requirements
- Legal obligations
- Economic factors

The `MoSCoW` Method is a prioritization technique for requirements:
* **M - MUST:** Essential for success.
* **S - SHOULD:** High priority; critical but can be worked around if necessary.
* **C - COULD:** Desirable, included if time/resources permit.
* **W - WON'T:** Agreed not to be in this release, but may be considered later.


#### Architecture Structures
A structure is the set of elements itself, and their organization.
Architectural structures can be divided into 3 groups depending on the broad nature of the elements they show.
1. **Module Structures** (Code /Static View) - code-based way of considering the system.
	- Elements - Code units like Modules, classes, files or components
	- They are assigned areas of functional responsibility.
	- Relationships: Based on static dependencies like "is part of" (decomposition), "depends on" (uses), or "is a subtype of" (generalization).
	- Primary Concerns: Modifiability, Reusability, and Maintainability.
2. **Component-and-Connector (C&C) Structures** (Run-time/Dynamic View) - executing set of interacting elements.
	- Elements: Components (principal units of computation or data) and Connectors (communication mechanisms like protocols, APIs, or data streams).
	- Relationships: "Attaches to" (communication link between a component and a connector).
	- Primary Concerns: Performance, Security, Reliability, and Functionality. They represent the system's topology and architectural style (e.g., Client-Server, Pipe-and-Filter).
3. **Allocation Structures** (Mapping/Deployment View) - relates the system to the non-software environment.
	- Elements: Software elements (from module or C&C views) and Environmental elements (hardware, file system, network locations, teams).
	- Relationships: "Is allocated to" or "is implemented by."
	- Primary Concerns: Deployment, Scalability, Availability, and Development/Team Structure. They show where the code resides (hardware, file structure) and who is responsible for it (team structure).

#### Views
View is a representation of a coherent set of architectural elements, as written by and read by system stakeholders.
- A representation of elements and their relationship.

View is a representation of a whole system from the perspective of a related set of concerns.

**4+1 View Model** 
Created by `Philippe Kruchten`, it uses multiple views to separate stakeholders concerns.
The 4 Views and the Central +1 :-

| View                                               | Focus (The System's Structure)                                                                         | Stakeholder Concern                                                                      |
| :------------------------------------------------- | :----------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------- |
| **1. Logical View** (module)                       | The system's **functional structure**—the object model, classes, and their relationships. (OOP)        | **End-users** and **Functional Designers** (What the system does).                       |
| **2. Development View** (implementation)           | The **static organization** of the code in the development environment. (packages)                     | **Programmers** and **Software Managers** (How the system is built and maintained).      |
| **3. Process View** (component and connector view) | The **dynamic structure**—processes, threads, and their interactions at run-time.                      | **Integrators** and **System Engineers** (Concurrency, performance, and communication).  |
| **4. Physical View** (Deployment)                  | The mapping of software processes onto **hardware** and network infrastructure.                        | **System Engineers** and **Deployment Managers** (Topology, installation, and capacity). |
| **+1. Scenarios View**                             | A small set of **key use cases** or **scenarios** that drive the design and validate the architecture. | **All Stakeholders** (Acts as the glue to ensure the four views are consistent).         |
Logical View: Using Class Diagram
Process View: Using Activity Diagram - (do this then that...)
Development View: Using Layer Diagram - (presentation - business logic - data ..)
Physical View: Using Deployment Diagram - (browser - server-  database)
Scenario: Using Use case Diagram


### The Role of an Architect
1. Software Engineering Lead Role:
	- Technical Excellence: Possess excellent engineering skills to solve hard problems.
	- Architectural Authority: Define, defend, and ensure adherence to architectural decisions.
	- Team Leadership: Lead development, promote good practices, and manage releases.
2. Facilitate Communication
	- in the middle between customers, PMs, marketing, Devs and Modeler
3. Technology Expert
	- Know and understand relevant technology.
	- evaluate and influence the choice of 3rd party frameworks and platforms.
4. Risk Management
	- evaluate risks associated with design options and choices. 
	- Prevent disasters from happening.

#### Architecture in the Life Cycle
Iteration on both functional and quality requirements with many stakeholders.
*Steps to Design an Architecture* - Iterative 
**Step 1**: Define architecture requirements.
- Creating a model of the requirement to drive architecture design.

**Step 2**: Architecture Design.
- Defining the structure and responsibilities of the components of the architecture,

**Step 3**: Validation
- "testing" the architecture, typically by walking through the design against existing requirements and possible future requirements.

##### 1. Identifying Architectural Requirements
- comes mainly from functional requirements & other documents.
- Some architectural requirements are really **constraints**. e.g. performance (<4 sec response time for 90% of requests) ... , (business - system must run as a plug-in for MS BizTalk), Java only ...
- **Prioritizing Requirements**, it is initially sufficient to allocate each to three categories> high, med and low.

##### 2. Architectural Design
has two steps -
1. Choosing architectural styles, and
2. Specifying individual components & allocating them responsibilities.

Input is architectural requirements and Outputs architecture views that capture the design & a design document.
The design document explains the design, key reasons for some major decisions and identifies risks involved.

**Choosing Architectural Style**
- Depending on the size of the application one or more architectural styles may be used.
- but we must first understand how each of the main architecture styles address certain quality attributes.

**Allocate Components**
- next we define the major components that will comprise the design.
- The selected architecture style/framework defines the overall communication patterns for the components.

Activities that follow the selection of framework:-
- Identification: Defining the major application components and how they fit into the selected framework.
- Interfaces: Specifying the services and interfaces each component provides.
- Definition: Clarifying the responsibilities and dependencies between components.
- Distribution: Identifying parts of the architecture that can be separated and distributed across a network of servers.


##### 3. Architecture Validation
To increase the confidence of the design team that the architecture is fit for purpose.
The main challenge in validating an architectural design is that you are trying to confirm the fitness of a theoretical blueprint before the system is built.

There are two main non-executable techniques for validating architecture:
1.  **Scenario Testing:** Manually checking the design against **test scenarios**.
2.  **Prototyping:** Building a **simple, executable prototype** to assess core requirements.



#### Quality Attributes in Software Architecture
A **quality attribute** is a measurable or testable property of a system that is used to indicate how well the system satisfies the needs of its stakeholders.
Quality attributes should be:
- Not subjective
- In sufficient detail
- Of a value and context


#### Architecture and Requirements
System requirements can be categorized as:
- **Functional Requirements** - what it does and how it behaves or react to run-time stimuli.
- **Quality attribute requirements** - annotate (qualify) functional requirements.
- **Constraints** - design decision with 0 degrees of freedom.

**Quality Attribute Considerations**
FR - when this button is pressed show a dialog
- performance - how fast to show
- availability - how often it will fail and how quickly repaired (99% uptime, 5 second recover)
- usability - how easy

The discussion of software quality attributes faces three main problems:
1.  **Untestable Definitions:** Vague Attributes  (e.g., "modifiable"), impossible to verify or test.
2.  **Boundary Disputes:** (e.g., is a DDOS failure a matter of security, availability, or performance?).
3.  **Inconsistent Vocabulary:** Different communities have developed their own, incompatible terms.

1 & 2 - solution is to use quality attribute scenarios as a means of characterizing quality attributes.
3 - solution is provide a discussion of each attribute. - focusing on underlying concerns


**Specifying Quality Attribute Requirements**
- Source of stimulus - e.g. people, HW, SW ..
- Stimulus - e.g. Fault, Crash, 
- Environment - 
- Artifact - e.g. processors, comms channels, storage, processes
- Response - e.g. prevent fault from becoming failure, detect fault and log
- Response measure - e.g. availability percentage, repair time

#### Availability
This is a broad perspective and encompasses *reliability*. and adds the notion of recovery to it.
Fundamentally, it is about minimizing service outage time by mitigating faults.

**Goal of Availability Tactics**
A failure occurs when the system no longer delivers a service consistent with its specification.
- A fault (flaw, or mistake in the system's design, code, or documentation) has the potential to cause a failure.

Availability tactics enable a system to endure faults so that services remain compliant with their specifications. to prevent them from becoming a failure or bound the effects for easy repair.

e.g. for availability quality attribute

| Portion of Scenario | Possible Values                                                                                                                                                                                                                                                                                                                                                                                                         |
| ------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Source of stimulus  | Internal/external: people, hardware, software, physical infrastructure, physical environment                                                                                                                                                                                                                                                                                                                            |
| Stimulus            | Fault: omission, crash, incorrect timing, incorrect response                                                                                                                                                                                                                                                                                                                                                            |
| Environment         | System’s processors, communication channels, persistent storage, processes                                                                                                                                                                                                                                                                                                                                              |
| Artifact            | Normal operation, startup, shutdown, repair mode, degraded operation, overloaded operation                                                                                                                                                                                                                                                                                                                              |
| Response            | Prevent the fault from becoming a failure<br>Detect the fault:<br> - log the fault<br> - notify appropriate entities (people or systems)<br>Recover from the fault<br> - disable source of events causing the fault<br> - be temporarily unavailable while repair is being effected<br> - fix or mask the fault/failure or contain the damage it causes<br> - operate in a degraded mode while repair is being effected |
| Response measure    | Time or time interval when the system must be available<br>Availability percentage (e.g. 99.999%)<br>Time to detect the fault<br>Time to repair the fault<br>Time or time interval in which system can be in degraded mode<br>Proportion (e.g., 99%) or rate (e.g., up to 100 per second) of a certain class of faults that the system prevents, or handles without failing                                             |


#### Interoperability
Is about the degree to which two or more systems can usefully exchange meaningful information.
Like the others it  is not a yes-or-no proposition but has shades of meaning.

**Goal of Interoperability Tactics**
The goal is to ensure two or more systems can **usefully exchange information** by addressing three core needs:
1.  Systems must **know about each other**.
2.  Information must be exchanged in a **meaningful fashion**, which requires:
	* **Sequencing:** Providing services in the **correct order**.
	* **Translation:** Modifying information from one system into a form **acceptable to the other**.

e.g. on ppt
#### Modifiability
Is about change and our interest in it is in the cost and risk of making changes.
an architect has to consider three questions:
- What can change?
- What is the likelihood of the change?
- When is the change made and who makes it?

**Goal of Modifiability Tactics**
The goal is to control the complexity of making changes as well as the time and cost to make changes.
e.g. on ppt

#### Performance
Is about time and the system's ability to meet timing requirements.
Performance is characterizing events and measuring the system's time-based response to those events.

**Goal of Performance Tactics**
The goal is to generate a response to an event arriving at the system within some time-based constraint.
e.g. on ppt

#### Security
Is a measure of the system’s ability to protect data and information from unauthorized access.
A harm against a computer is an **Attack**, and it can be an unauthorized attempt to access data or it may be an attempt to deny services to legitimate. users.

Security has 3 main characteristics: CIA
- Confidentiality - property that data or service is being protected from unauthorized access.
- Integrity - property that data is not subject to unauthorized manipulation.
- Availability - data is available to legitimate use.

Other characteristics that support CIA:
- Authentication - verify identity
- Nonrepudiation - guarantees that the sender of a message cannot later deny sending that message and the recipient can not deny receiving the message.
- Authorization - grants a user the privileges to perform a task.

**Goals of Security Tactics**
- one way of thinking about security is physical security. 
- This leads to our four categories of tactics: detect, resist, react, and recover.
e.g. on ppt

#### Testability
 refers to the ease with which software can be made to demonstrate its faults through testing.
If a fault is present in a system, then we want it to fail during testing as quickly as possible.

**Goal of Testability Tactics**
The goal is to allow for easier testing when an increment of software development has completed.

There are two categories of tactics for testability:
- adding controllability and observability to the system.
- limiting complexity in the system’s design.
e.g. on ppt

#### Usability
Concerned with how easy it is for the user to accomplish a desired task and the kind of user support the system provides.
- it is one of the cheapest & easiest ways to improve a system's quality (perception of quality).

It Compromises of -
- learning its features and using it efficiently
- minimizing the impact of errors
- adapting to user's needs
- increasing confidence and satisfaction

**Goals of Usability Tactics**
Terms "user initiative," "system initiative," and "mixed initiative" are used to describe w/c human-computer pair takes the initiative in performing certain actions and how the interaction proceeds.
e.g. on ppt


### Guiding Quality Design Decisions

| Category                                    | Short Explanation                                                                                                                                                                                             |
| :------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1. Allocation of Responsibilities**       | Deciding **which component does what**—how functional requirements and quality attribute requirements (like security checks) are distributed among the system's major elements (modules, ...).                |
| **2. Coordination Model**                   | Defining **how components communicate** and interact (and who are not allowed to), including choices for protocols (e.g., REST, message queues) and synchronization mechanisms. stateless?, synchronous? ...  |
| **3. Data Model**                           | Defining the **structure, organization, and semantics of the persistent data** used by the system (e.g., database schemas, data formats, and data storage technology). how created, accessed, manipulated ... |
| **4. Management of Resources**              | Specifying **how shared resources** (like memory, threads, connections, or I/O devices) are controlled, allocated, and released to prevent conflicts and ensure efficiency.                                   |
| **5. Mapping Among Architectural Elements** | Deciding **how elements in one view relate to elements in another**, such as how run-time components map to the static code structure or to physical hardware (deployment).                                   |
| **6. Binding Time Decisions**               | Determining **when a relationship or property is fixed**—at run-time, compile-time, build-time, or design-time. Earlier binding (e.g., at compile-time) usually improves performance but reduces flexibility. |
| **7. Choice of Technology**                 | Selecting the **specific technologies, frameworks, and products** (e.g., Java vs. Python, MySQL vs. MongoDB) to implement the various components and connectors.                                              |


# CH3 - Architectural Patterns and Tactics
## Patterns
An architectural pattern - is a package of design decisions that is found repeatedly in practice, has known properties that permit reuse, and describes a class of architectures.
It defines the fundamental, *high-level structure* and organization of a system by specifying its components, their responsibilities, and the rules for their interaction.

**Tactics** are simpler than patterns. (more specific)
An Architectural Tactic is a design decision that influences a *single quality attribute* response.

The relationship is hierarchical:
- The Pattern sets the overall structural constraints. (insufficient to create a working system)
- The Tactics are the specific mechanisms used within that pattern to achieve the desired quality properties.

| Feature         | Architectural Pattern                                | Architectural Tactic                                                              |
| :-------------- | :--------------------------------------------------- | :-------------------------------------------------------------------------------- |
| **Scope**       | Global (entire system)                               | Local (component/connector)                                                       |
| **Abstraction** | High (Overall structure/rules)                       | Low (Specific mechanism/technique)                                                |
| **Why Use It?** | To establish the system's **fundamental structure**. | To **implement** or **improve** a specific quality goal.                          |
| **Example**     | **Client-Server** or **Microservices**.              | **Active Replication** (for Availability) or **Input Validation** (for Security). |

 An **architectural pattern** establishes a relationship between:
 - A **context**: A recurring, common situation in the world that gives rise to a problem.
 - A **Problem**: appropriately generalized, that arises in the given context.
 -  A **solution**: A successful architectural resolution to the problem, appropriately abstracted.

The solution is defined by its:
- *Element Types* (e.g., data repositories, processes).
- *Interaction Mechanisms* (connectors like method calls, message bus).
- *Topological Layout* of components.
- *Semantic Constraints* governing behavior and topology.

### 1. Layer Pattern

| Element      | Description                                                                                                                                                                                                                                               |
| :----------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | Complex systems require the ability to develop and evolve different parts of the system independently.                                                                                                                                                    |
| **Problem**  | The software must be segmented to support **portability, modifiability, and reuse** with minimal interaction between parts.                                                                                                                               |
| **Solution** | The system is divided into **layers**, where each layer is a cohesive unit of services. Usage must be **unidirectional** (a layer only depends on the layers directly beneath it), which enforces clear **separation of concerns** via public interfaces. |
Elements - *Layer* a kind of module.
Relations - *Allowed to use* - usage rules and exceptions.
Constraints - 
- one software only allocated to only one layer, 
- there are at least 2 layers
- the allowed to use relation should not be circular.

Weakness - addition of layers means up-front cost and complexity. and a *Performance penalty*.

### 2. Broker Pattern

| Element      | Description                                                                                                                                                                                           |
| :----------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | Systems consist of services distributed across multiple servers, creating complexity in management, interoperation, and availability.                                                                 |
| **Problem**  | How to structure the distributed software so that **clients (users)** don't need to know the **nature or location of servers (providers)**, allowing dynamic changes in their connections.            |
| **Solution** | An intermediary, called a **broker**, is introduced to separate clients and servers. Clients request services from the broker, which then locates and forwards the request to the appropriate server. |
Elements:
- *Client*, a requester of services.
- *Server*, a provider of services.
- *Broker*, an intermediary that locates an appropriate server to fulfill a client’s request, forwards the request to the server, and returns the results to the client.
- *Client-side proxy*, an intermediary that manages the actual communication with the broker, including marshaling, sending, and un-marshaling of messages.
- *Server-side proxy*, an intermediary that manages the actual communication with the broker, including marshaling, sending, and un-marshaling of messages.

### 3. Model-View-Controller Pattern

| Element      | Description                                                                                                                                                                                                                                                                         |
| :----------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | User interface (UI) code is the most frequently modified part of an application, and users often need multiple, coordinated views of the same underlying data.                                                                                                                      |
| **Problem**  | How to separate UI functionality from application logic while keeping the UI responsive to both user input and changes in the core application data.                                                                                                                                |
| **Solution** | Application functionality is separated into three components: **Model** (holds the application data), **View** (displays data and handles user interaction), and **Controller** (mediates between the Model and View, managing user input and notifying the View of state changes). |
Elements:
- The *model* is a representation of the application data or state, and it contains (or provides an interface to) application logic.
- The *view* is a user interface component that either produces a representation of the model for the user or allows for some form of user input, or both.
- The *controller* manages the interaction between the model and the view, translating user actions into changes to the model or changes to the view.


### 4. Pipe and Filter Pattern

| Element | Description |
| :--- | :--- |
| **Context** | Systems often need to process a continuous stream of data through multiple, discrete **transformations**. It's desirable to make these transformation steps **independent and reusable**. |
| **Problem** | How to structure a system into **loosely coupled, reusable components** that can be flexibly combined and executed in **parallel** to process a data stream efficiently. |
| **Solution** | Processing is achieved through a chain of **Filters** (independent transformation units) connected by **Pipes** (data channels). Data arrives at a filter, is transformed, and is passed via the pipe to the next filter in the sequence. |
Elements:
- *Filter*, a component that transforms data read from input port(s) to data written on its output port(s).
- *Pipe*, a connector that conveys data from a filter’s output port(s) to another filter’s input port(s).
	- A pipe has a single source for its input and a single target for its output.
	- A pipe preserves the sequence of data items, and it does not alter the  data passing through.

Relations - The output of filters is an input of pipes.
Constraints - pipes connect filter outputs to filter inputs
- Connected filters must agree on the type of data being passed along the connecting pipe.

### 5. Client-Server Pattern 

| Element      | Description                                                                                                                                                                                                                                                        |
| :----------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | A large number of **distributed clients** need to access **shared resources and services**, requiring control over access and quality of service.                                                                                                                  |
| **Problem**  | How to improve **modifiability** (by centralizing services for single-point change) and increase **scalability/availability** (by centralizing control while potentially distributing the resources).                                                              |
| **Solution** | The system separates users of services (**Clients**) from providers of services (**Servers**). Clients **request** services, and Servers **provide** them. A component may act as both, and the servers can be either centralized or distributed across a network. |

Elements:
 *Client*, a component that invokes services of a server component.
 - Clients have ports that describe the services they require.

*Server*: a component that provides services to clients.
- Servers have ports that describe the services they provide.

*Request/reply connector*: a data connector employing a request/reply protocol, used by a client to invoke services on a server.

### 6. Peer-to-Peer (P2P) Pattern 

| Element      | Description                                                                                                                                                                                                                                                |
| :----------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | Distributed computing entities, all considered **equally important**, need to cooperate and share their individual resources to provide a service to a community of users.                                                                                 |
| **Problem**  | How to connect a set of "equal" distributed entities using a common protocol to enable resource sharing, ensure **high availability**, and achieve **scalability** without relying on a central authority.                                                 |
| **Solution** | Components directly interact as **peers**. All peers are **equal**, meaning no single peer is critical to the system's health. Communication is typically a request/reply mechanism without the master/slave asymmetry found in the Client-Server pattern. |

Elements:
- *Peer*, an independent component running on a network node. *Special peer* components can provide routing, indexing, and peer search capability.
- *Request/reply connector*, which is used to connect to the peer network, search for other peers, and invoke services from other peers. In some cases, the need for a reply is done away with.

Relations: The relation associates peers with their connectors. Attachments may change at runtime.

### 7. Service-Oriented Architecture (SOA) Pattern 

| Element      | Description                                                                                                                                                                                                                                                             |
| :----------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | Services are offered by **providers** and consumed by **consumers**. Consumers must be able to use these services without knowing the internal implementation details.                                                                                                  |
| **Problem**  | How to enable **interoperability** between components that are distributed, run on **different platforms**, are written in different languages, and are often provided by different organizations across a network (like the Internet).                                 |
| **Solution** | The SOA pattern structures the system as a collection of distributed components that either **provide or consume services**. Services are defined by explicit, technology-agnostic interfaces, allowing clients to interact with them without implementation knowledge. |
SOA is an architecture where computation is achieved by a set of **cooperating components** providing and consuming services over a network.
* **Elements:** Includes **Service Providers** (offer services via published interfaces) and **Consumers** (invoke services). The architecture may also use intermediary components like an **ESB** (Enterprise Service Bus) for routing/transforming, a **Registry** for service discovery, and an **Orchestration Server** for coordinating complex workflows.
* **Connectors:** Services typically communicate using standards like **SOAP** (synchronous communication), **REST** (using HTTP request/reply), or **Asynchronous Messaging** (point-to-point or publish/subscribe).
* **Weaknesses:** SOA-based systems are often **complex** to build, control over the **evolution of independent services** is difficult, and there is a **performance overhead** associated with the middleware and the lack of performance guarantees.

### 8. Publish-Subscribe (Pub-Sub) Pattern 

| Element      | Description                                                                                                                                                                                                                                                                                          |
| :----------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | A number of **independent producers and consumers of data** must interact, where the precise identity and number of these actors are **not fixed or predetermined**.                                                                                                                                 |
| **Problem**  | How to create an integration mechanism that allows producers and consumers to transmit messages while remaining **unaware of each other's identity** or even existence (achieving extreme **decoupling**).                                                                                           |
| **Solution** | Components interact via announced messages, or **events**. **Publisher** components place events onto a communication bus. The connector (the bus/broker) then **delivers** those events only to the **Subscriber** components that have previously registered an interest in those specific events. |
Elements:
- *Any C&C component* with at least one publish or subscribe port.
- The *publish-subscribe connector*, which will have announce and listen roles for components that wish to publish and subscribe to events.

Constraints: all components are connected to an event distributor that may be viewed as either a bus, connector or a component.

Weakness: increased latency & a negative effect on scalability and predictability of message delivery time. Less control over ordering of messages and delivery is nor guaranteed.

### 9. Shared-Data Pattern 

| Element      | Description                                                                                                                                                                                                                                                                                                |
| :----------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | Multiple computational components need to **share and manipulate large amounts of persistent data** that isn't owned by any single component.                                                                                                                                                              |
| **Problem**  | How can a system effectively store and manage persistent data that must be **concurrently accessed and manipulated** by multiple, independent components?                                                                                                                                                  |
| **Solution** | Interaction revolves around the exchange of persistent data between multiple **Data Accessors** (components) and at least one **Shared-Data Store** (the central repository). Data exchange involves simple **reading and writing** and can be initiated by either the accessors or the data store itself. |
Constraints: Data accessors interact only with the data store(s).
Weaknesses: 
- The shared-data store may be a performance bottleneck.
- The shared-data store may be a single point of failure.
- Producers and consumers of data may be tightly coupled.
  

### 10. Map-Reduce Pattern 

| Element      | Description                                                                                                                                                                  |
| :----------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | Businesses need to quickly and efficiently analyze **enormous, petabyte-scale volumes of data** they generate or access.                                                     |
| **Problem**  | How to efficiently perform a **distributed and parallel sort** and analysis of ultra-large datasets while providing a simple programming model for the data analysis itself. |
| **Solution** | The system uses a specialized **infrastructure** to manage parallel execution and data sorting across many hardware nodes. The programmer supplies two specific components:  |
|              | **Map:** Filters the raw data to extract(E) and transform(T) the items to be combined.                                                                                       |
|              | **Reduce:** Combines and aggregates(Loads, L) the results produced by the Map functions.                                                                                     |
Elements: Map, Reduce and the infrastructure responsible for deployment.
Overview/Benefits - Provides a framework for parallel analysis on distributed data, allowing for **low latency** and **high availability** by delegating complexity to the infrastructure.

### 11. Multi-Tier Pattern

| Element      | Description                                                                                                                                                                                                 |
| :----------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Context**  | In a **distributed deployment**, the system's infrastructure needs to be divided into distinct, manageable subsets.                                                                                         |
| **Problem**  | How to split the system into computationally **independent execution structures**—groups of software and hardware connected by communication media—for better management and scaling.                       |
| **Solution** | The system's execution structures are organized into logical groupings of components, with each grouping being called a **tier**. This creates clear separation of concerns in the distributed environment. |
Elements:
- *Tier*, which is a logical grouping of software components.

Relations:
- *Is part of*, to group components into tiers.
- *Communicates with*, to show how tiers and the components they contain interact.
- *Allocated to*, in the case that tiers map to computing platforms.

Constraints: A software component belongs to exactly one tier.
Weaknesses: Substantial up-front cost and complexity.


## Tactics and Interactions
Each tactic has pluses (its reason for being) and minuses side effects.
Use of tactics can help alleviate the minuses. But nothing is Free...

e.g. The Design Cascade: Tactics and Side Effects
This scenario demonstrates how the selection of a single **Architectural Tactic** to achieve one goal inevitably introduces **side effects** that require the application of *other* tactics, leading to a complex, cascading series of design decisions. This is why architecture design is about **trade-offs**.

The process begins with an initial goal and unfolds as a recursive cycle:
1.  **Initial Goal (Availability):** Detect faults.
    * **Tactic:** **Ping/Echo** (Pros: Detects crashes quickly).
    * **Side Effects:** Performance overhead, security risk, modifiability challenge (adding it).
2.  **Addressing Side Effect (Performance):** Reduce overhead.
    * **Tactic:** **Increase Available Resources** (Pros: More capacity for Pings).
    * **Side Effects:** Increased Cost, challenge of efficiently using the new resources.
3.  **Addressing Side Effect (Resource Use):** Use resources efficiently.
    * **Tactic:** **Scheduling Policy** (Pros: Optimizes resource allocation).
    * **Side Effects:** Modifiability challenge (adding and changing the policy).
4.  **Addressing Side Effect (Adding Scheduler):** Integrate the new policy without disrupting existing components.
    * **Tactic:** **Use an Intermediary** (Pros: Decouples the policy from components).
    * **Side Effects:** Modifiability challenge (ensuring *all* communication goes through the intermediary).
5.  **Addressing Side Effect (Communication Flow):** Enforce mandatory use of the intermediary.
    * **Tactic:** **Restrict Communication Paths** (Pros: Guarantees traffic control).
    * **Side Effects:** Performance challenge (ensuring the intermediary doesn't become a bottleneck).

**Key Takeaway**:
The design problem becomes recursive because solving one problem (detecting a fault) by applying a tactic introduces a new problem (performance overhead), which requires a new tactic, which introduces another problem, and so on.



# CH4: Design Patterns :LiAudioLines: 
Pattern is a (proven) solution to a problem in a context. 
- *Context*: the situation in which the pattern apply 
- *Problem*: goal you are trying to achieve in this context (including constraints) 
- *Solution*: general design that anyone can apply which resolves the goal and set of constraints.

Examples of patterns: blueprint for a house, manufacturing

A design pattern is *not a finished design* that can be transformed directly into code.
- it is a description or template for how to solve the problem
- they help designers choose design alternatives that make the system reusable.
- they can also improve the documentation of an existing system by defining explicit specification of class and object interactions and their underlying intent.

#### History of Design Patterns
Christopher Alexander (1977) wrote about patterns.
1995, the principles that alexander established were applied to software engineering and resulted in the book: "Design patterns: Elements of Reusable Object-Oriented Software” by *Erich Gamma*, *Richard Helm*, *Ralph Johnson*, and *`John Vlissides`*. The Gang of Four (GOF).

Based on the book, design patterns are based primarily based on the following principles of object oriented design,
- program to an interface not an implementation
- favor object composition over inheritance

3 types of design patterns
1. **Creational** - "creating objects in a suitable manner for the situation".
	- they hide the creation logic and just deliver the object. "new" operator is not directly used.
	- provides flexibility for each use case. e.g. buttons on d/t platforms
	- e.g. abstract factory, builder, factory method, prototype, singleton
2. **Structural** - “identifying a simple way to realize relationships between entities”.
	- about class and object composition. using interfaces, inheritance ...
	- e.g. adapter, bridge, composite, decorator, facade, flyweight, proxy
3. **Behavioral** - "common communication patterns between objects"
	- e.g. chain of responsibility, command, interpreter, iterator, mediator, observer, state, strategy..


**Characteristics of Design Patterns** 
- **Viewpoints** - way to describe patterns.
	- static: class model (building block)
	- dynamic: sequence or state diagram
- **Levels** - decomposition of patterns
	- abstract level: describes the core of the pattern
	- concrete: describes the particulars of the this case
- **Roles** - the "players" in the pattern usage.
	- the application itself, clients of the design pattern application and the setup code initializes ...


#### Design Pattern Forms
1. **Delegation**  a mechanism in which an object forwards (delegates) a request to another object.
2. **Recursion** - when part of a pattern essentially uses itself.


**Class Association UML/OMT Notations** 
![[Pasted image 20261124183818.png]]

**Basic UML/OMT notations in the GOF patterns** 
![[Pasted image 20261124183757.png]]

#### Design Pattern Goals
- to support reuse of designs
- to facilitate software evolution (new features w/out breaking existing)
- we want to design **for change**.

principles to achieve the goals: Reduce implementation dependencies between elements of a software system
- program to an interface
- favor composition over inheritance
- use delegation


#### Elements of Design Patterns
4 basic elements:
- **patter name** - to describe a design problem, its solutions and consequences in a word or two.
- **problem** - when to apply the pattern, the problem and its context
- **solution** - elements of the pattern, their relationship, responsibilities and collaborations.
- **consequences** - results and trade-offs of applying the pattern.


### Types of Design Patterns
1. *Creational patterns*: patterns provide instantiation mechanisms, making it easier to create objects in a way that suits the situation.
 2. *Structural design patterns*: generally deal with relationships between entities, making it easier for these entities to work together.
 3. *Behavioral design patterns*: patterns are used in communications between entities and make it easier and more flexible for these entities to communicate.

Scope - what the pattern applies to: 
- Class Patterns - Focus on the relationships between classes and their subclasses Involve class inheritance reuse.
- Object Patterns - Focus on the relationships between objects  - Involve object composition reuse.


#### 1. Creational Pattens
- all about class instantiation.
- we want clients to not contain large and complex code to instantiate an object.
- these patterns create the object for you instead of using the *new* keyword, for more flexibility in deciding w/c object gets created for the use case.

**Factory Method Patterns** 
These pattern allow for the creation of objects without specifying the type of object that is to be created in code.
A factory class contains a method that allows determination of the created type at run-time.

e.g. a method `orderPizza(string type)` w/c takes the type of the pizza and creates that type of pizza object and prepares it.
- we have `SimplePizzaFactory` class w/c creates the pizza with `createPizza(type)` and `orderPizza()` uses this to get the pizza object and prepares and orders the pizza.
- we say that `orderPizza()` is a client of the `SimplePizzaFactory`.
- this method of creating a pizza is good because we have to change it in one place to make modifications if it has multiple clients.

#### 2. Structural Pattern
- all about class and object composition.
- class-creation patterns use inheritance to compose interface.

**Adapter Pattern** 
Convert the interface of a class into another interface that the client expects. or make compatible.

- *Intent*: Match an existing object beyond your control to a particular interface.
- *Problem*: A system has the right data and behavior but the wrong interface.
- *Solution*: Define an adapter class which acts as an intermediary. The adapter does little work itself but merely translates commands from one form to another.
- *Implementation*: Contain the existing class in another class.

*when to use?* 
especially useful for off-the-shelf code, toolkits and libraries.

```
interface Shape { ​
 void drawRec(int x1, int y1, int x2, int y2); ​
}​
 ​
class LegacyRectangle { ​
	public void drawRec(int x, int y, int w, int h) {   ​
		println("rectangle" + x + ',' + y)​
		println("with width " + w + " and height " + h); ​
	} ​
}
class RectangleAdapter implements Shape { ​​
	private LegacyRectangle adaptee = ​new LegacyRectangle(); ​
​
	public void drawRec(int x1, int y1, int x2, int y2) {​
		adaptee.drawRec(x1,y1,Math.abs(x2-x1), Math.abs(y2-y1)); 
	}
}
```

**Composition Vs Inheritance** 
both for reuse: inheritance (white box) and composition (black box).

Reuse by Inheritance makes the subclass dependent on the parent class, this makes the system complex, less testable and hard to change the functionality at run time.

Composition means that *one class uses another*, further promoting decoupling by defining the interfaces clearly. also means the implementation can easily be changed.


#### 3. Behavioral Design Pattern
- all about class's object communication.

**Observer Pattern**
- defines a "one-to-many" dependency between objects, one object change applies to all.
- AKA dependency mechanism/ publish-subscribe / broadcast / change-update

*Subject* - the object which will frequently change its state and upon which other objects depend.
*Observer* - the object which depends on a subject and updates according to its subject's state.

e.g. data is the subject and multiple charts are observers that change when the data does.
- observers are not aware of each others existence.
- when a change happens all observers are notified.

key-players
- *`subject`* - has a list of observers and an interface for attaching/detaching an observer.
- *`observer`* - an updating interface for objects that get notified of change.
- *`ConcreteSubject`* - stores 'state of interest' to observers and sends notification when it changes.
- *`ConcreteObserver`* - implements updating interface.

```
 interface Observer {
	 void update (Observable sub, Object arg)
	 // repaint the pi-chart
 }
class Observable {
	 public void addObserver(Observer o) {}
	 public void deleteObserver (Observer o)  {}
	 public void notifyObservers(Object arg) {}
	 …
	 public boolean hasChanged() {}
}
```


**Memento Pattern**
- used to restore the state of an object to a previous state.

has 3 actor classes:
- *Memento* - contains state of an object to be restored.
- *Originator* - creates and stores states in Memento objects
- *Caretaker* - object responsible to restore object state from memento.

*Intent*
Capture and externalize an object’s state without violating encapsulation.
- Useful when implementing checkpoints and undo mechanisms that let users back out of tentative operations or recover from errors.

*Forces* 
Application needs to capture states at certain times or at user discretion.
- undo/redo
- log errors or events
- backtracking

*Participants*
**Memento** - stores internal state of the originator object.
- protects access by other than the originator.
- mementos have two interfaces
	- narrow interface for caretakers and 
	- wide interface for the originator

**Originator** - creates a memento with snapshot of its current internal state.
**Caretaker** - responsible for the memento's safekeeping.
- Never operates on or examines the contents of a memento.

Example
```
public class Originator {
  private int number; private File file = null;
  public Originator(){}
  public Memento getMemento() { return new Memento(this);}
  public void setMemento(Memento m){number = m.number; file = m.file;}
 }
private class Memento implements java.io.Serializable{
  private int number;
  private File file = null;
  public Memento( Originator o){ number = o.number; file = o.file;}
 }
```

#### Benefits of Design Patterns
- Capture expertise and make it accessible to non-experts in a standard form
 - Facilitate communication among developers by providing a common language
 - Make it easier to reuse successful designs and avoid alternatives that diminish reusability
 - Facilitate design modifications
 - Improve design documentation
 - Improve design understandability


# CH5: SOLID Principles
The SOLID principles tell us how to arrange our functions and data structures into classes, and how those classes should be interconnected. 

The goal of the principles is the creation of mid-level software structures that:
- Tolerate change,
- Are easy to understand, and
- Are the basis of components that can be used in many software systems.	

SOLID
- S – The Single Responsibility Principle
- O – The Open-Closed Principle
- L – The `Liskov` Substitution Principle
- I – The Interface Segregation Principle
- D – The Dependency Inversion Principle

### SRP: The Single Responsibility Principle
“Every class should have a single responsibility, and that responsibility should be entirely encapsulated by that class”
In other words: do something once & Don’t Repeat Yourself (DRY).

**Signs**: difficulty in naming classes., multiple unit tests for 1 method.
**Do One Thing**: methods that only do one thing are usually very short: 3-5 lines.

**When violated**: fragile design that breaks in unexpected ways when changed.

### OCP: The Open-Closed Principle
“Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.”
- Open for extension - you can extend an object’s behavior.
- Closed for modification - without the need to modify any existing code. 

Can be accomplished by partitioning the system into components, and arranging those components into a dependency hierarchy that protects higher-level components from changes in lower-level components.

How we change behavior without changing code? - Rely on abstractions, not implementations.

**Violations** 
- Each change requires re-testing (possible bugs)
- Cascading changes through modules
- Logic depends on conditional statements

**Solution** - Using new classes

Approaches to **achieve OCP** 
- Using parameters (pass delegates)
- Inheritance (Template method pattern)
- Compositions (Strategy pattern)

OCP adds complexity to a design

### LSP: The `Liskov` Substitution Principle
“If S is a subtype of T, then objects of type T may be replaced with objects of type S without altering any of the desirable properties of that program.”

A subclass should only override the parent class's methods in a way that does not break functionality from a client's point of view. 
- Favor Interfaces over inheritance 
- Use inheritance sparingly.
- Keep inheritance hierarchies from getting to big - aim for no more than two or three deep.

### ISP: The Interface Segregation Principle
“No client should be forced to depend on methods it does not use.”
Keep interfaces as small as possible, to avoid unnecessary dependencies.

Each interface should only be concerned with one responsibility (SRP – only has one reason to change).

```java
public interface IVehicle {
    void Accelerate();
    void Break();
    void ChangeGear(int newGear);
    void TurnOnRadio();
    void TurnOffRadio();
    void TurnOnHeatedSeats();
    void TurnOffHeatedSeats();
}
```

We should break this down to `IVehicle`, `IAudioControl`, `IHeatedSeats`.

### DIP: The Dependency Inversion Principle
A. High-level modules should not depend on low-level modules. Both should depend on abstractions.
B. Abstractions should not depend on details. Details should depend on abstractions.

High level modules should:
- depend upon abstraction of low level modules
- force low level modules to change

When violated: lower level module changes can force high level modules to change.

Instead of having concrete implementations communicate directly (and depend on each other), decouple them by formalizing their communication interface as an abstract interface based on the needs of the higher-level class.



# CH6: Documenting and Evaluating Software Architecture

### Documenting Software Architecture
Architecture - is the conceptual glue that holds every phase of the project together for all of its many stakeholders.
It must be described in sufficient detail, without ambiguity, and organized so that all stakeholders can quickly find the information they need.

Architecture documentation must 
- be sufficiently transparent and accessible to be quickly understood by new employees.
- be sufficiently concrete to serve as a blueprint for construction.
- have enough information to serve as a basis for analysis. 

Architecture documentation is both prescriptive (what should be) and descriptive (what is).


**Three Uses for Architecture Documentation** 
1. Education - Introducing people to the system 
2. Primary vehicle for communication among stakeholders - mainly architect to developers.
3. Basis for system analysis and construction - each module has interfaces, is used for evaluation.

#### Notations
**Informal Notations** - depicted using general-purpose diagramming tools. - semantics of the description are characterized using natural language. and they can not be formally analyzed.
**Semiformal Notations** - Standardized notation that prescribes graphical elements and rules of construction. Lacks a complete semantic meaning of those elements. Rudimentary analysis can be used. e.g. UML
**Formal Notation** - has a precise (usually mathematical) semantics. Formal analysis of both syntax and semantics is possible. e.g. Architectural description Languages(ADLs). support automation

###### Choosing Notations
Tradeoffs - more formal notations take more time and effort to create and understand, but offer reduced ambiguity and more opportunities for analysis. 

D/t notations have d/t uses, e.g.
- UML won't help us reason about schedules nor will a sequence diagram tell us about a system's likelihood to be delivered on time.

#### “Views and Beyond” Approach to Documentation
Views let us divide a software architecture into a number of interesting and manageable representations of the system.
Views give us our first principle of architecture documentation:
- Document the relevant views, and then add information that applies to more than one view.

###### Which Views are Relevant?
It depends on:
- Who the stakeholders are
- How they will use the documentation.

**`Kruchten’s` 4+1 views** 
- *Logical view*: supports behavioral requirements. Key abstractions are objects or object classes.
- *Process view*: addresses concurrency and distribution. Maps threads to objects. 
- *Development view*: organization of modules, libraries, subsystems, units of development.
- *Physical view*: maps other elements onto processing and communication nodes.
- *“Plus one” view*:  Maps the other views onto important *use cases* to show how they work.

**Siemens Four-Views (Hofmeister, Nord, `Soni`, Applied Software Architecture, 2000):**
- Conceptual view
- Module interconnection view
- Execution view
- Code view

**`Herzum` & Sims (Business Component Factory, 1999):**
- Technical architecture
- Application architecture
- Project management architecture
- Functional architecture

**Software Cost Reduction method  (`Parnas`, et al., 1980s)**
- *Module view*: shows modules as units of encapsulation; used to isolate changes and achieve modifiability.
- *Process view*: shows processes and how they synchronize and communicate at run-time; used to achieve performance.
- *Uses view*: shows programs and how they depend on each other; used to achieve incremental development and the ability to quickly field subsets.


An architect must consider the system in three ways:
How is it structured as a set of code units?
- e.g. Module views (module view-type)

How is it structured as a set of elements that have run-time behavior and interactions?
- e.g. Component-and-connector views (C&C view-type)

How does it relate to non-software structures in its environment?
- e.g. Allocation views (allocation view-type)

How many views do we need in our documentation package?
- Each view comes with a cost and benefit.
- Planning a view set requires understanding the needs of the stakeholders, and the resources available

You can determine which views are required, when to create them, and how much detail to include if you know the following:
- What people, and with what skills, are available
- Which standards you have to comply with
- What budget is on hand
- What the schedule is
- What the information needs of the important stakeholders are
- What the driving quality attribute requirements are
- What the approximate size of the system is?

**At a minimum, expect to have** 
- at least one module view, 
- at least one C&C view, and 
- for larger systems, at least one allocation view in your architecture document. 

###### Method for Choosing the Views
**Step 1. Build a stakeholder/view table.**
1.  **Define Rows:** List all stakeholders for your project's software architecture documentation.
2.  **Define Columns:** Enumerate relevant architectural views, drawing from:
	* Structures from Chapter 1.
	* Views discussed in the current chapter (Kruchten's, Siemens, Herzum & Sims, Parnas's SCR).
	* Views identified during your Architecture Design Document (ADD) work, including any existing view sketches.
	* Consider common views like decomposition, uses, and work assignment (applicable to most systems), and specific C&C or layered views as needed.
3.  **Populate Cells:** For each stakeholder-view intersection, specify the required level of detail: "none," "overview only," "moderate detail," or "high detail."

**Step 2. Combine views to reduce their number** 
1.  **Identify Marginal Views:** Look for views in your stakeholder/view table that require only an "overview" level of detail or serve very few stakeholders.
2.  **Combine Views:** Merge these marginal views with other, more strongly supported views. Common combinations include:
	* **Various C&C Views:** Combine due to their shared focus on runtime C/C relations.
	* **Deployment View:** Merge with SOA or communicating-processes views.
	* **Decomposition View:** Combine with work assignment, implementation, uses, or layered views, as decomposed modules often form the units for these other aspects.

**Step 3. Prioritize and Stage** 
1.  **Prioritize Decomposition View:** Release early as its high-level nature allows PMs to quickly begin staffing, training, outsourcing decisions, budgeting, and scheduling.
2.  **Aim for "Good Enough":** Providing 80% of the information is often sufficient for stakeholders to perform their tasks. Confirm with stakeholders if a subset of information meets their needs.
3.  **Breadth-First Approach:** You don't need to fully complete one view before starting another. Providing overview-level information across multiple views allows for broader progress.

### Documenting a View
**Section 1: The Primary Presentation** 
- Shows the elements and relations of the view. should contain the information you wish to convey about the system
- The primary presentation is most often **graphical**. - if so we should include a key section.
- can also be **textual** as a table or list. if rules are used they should be stated or referenced.

**Section 2: The Element Catalog** 
The element catalog provides details for all elements shown in the primary presentation, as well as any relevant omitted elements or relations. It includes:
- *Elements and their properties*: Names each element and lists its associated properties.
- *Relations and their properties:* Describes the types of relations depicted between elements in the view.
- *Element interfaces:* Documents the interfaces of each element.
- *Element behavior:* Explains any element behavior not evident from the primary presentation.

**Section 3: Context Diagram** 
Shows how the system or portion of the system depicted in this view relates to its environment. 
- its purpose is to depict the scope of a view.

Entities in the environment may be humans, other computer systems, or physical objects, such as sensors or controlled devices. 

**Section 4: Variability Guide** 
A variability guide shows how to exercise any variation points that are a part of the architecture shown in this view. 

**Section 5: Rationale** 
Explains why the design reflected in the view came to be.
Why the design is as it is and to provide a convincing argument that it is sound. 

```
VIEW TEMPLATE
S1. Primary presentation - charts and graphs
S2. Element catalog
	2.A Elements and their properties
	2.B Relations and their properties
	2.C Element Interfaces
	2.D Element Behavior
S3. Context diagram - diagram, duh
S4. Variability Guide
S5. Rationale
```

#### Document Information Beyond Views
*Document control information.* 
- List the *issuing organization*, the current *version number*, *date of issue* and status, a *change history*, and the *procedure for submitting change requests* to the document.

**Section 1**: Documentation Roadmap. - tells the reader what information is in the documentation and where to find it. (A MAP!)
- *Scope and Summary*
- *Documentation Organization*
- *View Overview:* Describes each architectural view included in the package, detailing:
	* The view's name and any instantiated patterns.
	* Its element, relation, and property types.
	* The languages, modeling techniques, or analytical methods used.
* *How Stakeholders Can Use the Documentation:* often through short scenarios.

**Section 2**: How a View is Documented (organized) - either the one described in this chapter or one of your own. 

**Section 3**: System Overview. 
Description of the system’s function, its users, and any important background or constraints. 
This might be a pointer to the project’s concept-of-operations document for the system.

**Section 4**: Mapping Between Views - explains how to associate different architectural views to understand their unity.
- Associations between elements across views are generally many-to-many.
- These connections can be documented in tables, naming the correspondence.
- **Examples:** "is implemented by" (component to module view), "implements" (module to component view), "included in" (decomposition to layered view).

**Section 5**: Rationale. - Documents the architectural decisions that apply to more than one view. 
- Documentation of background or organizational constraints or major requirements that led to decisions of system-wide import.
- Decisions about which fundamental architecture patterns are used.

**Section 6**: Directory. 
- Index of terms
- Glossary
- Acronym list.


### Documenting Behavior
This documentation complements each views by describing how architecture elements in that view interact with each other. 
It enables reasoning about 
- a system’s potential to deadlock
- a system’s ability to complete a task in the desired amount of time
- maximum memory consumption 
- and more ...


##### Notations for Documenting Behavior
**Trace-oriented languages**
- Traces are activities/interactions that describe the system's response to a stimuli while in a specific state.
- Trace describe a particular sequence of activities/interactions b/n structural elements.
- Examples:
	- Use cases
	- sequence diagrams
	- communication diagrams ....

**Comprehensive Languages** 
These models show the complete behavior of structural elements.
Given this type of documentation, we can infer all possible paths from initial to final state. (state machines)
*State machine languages* allow you to complement a structural description of the elements of the system with constraints on interactions and timed reactions to both internal and environmental stimuli.
- a state is an abstraction of all possible histories that could lead to that state.

### Documenting Quality Attributes
Where do quality attributes show up in the documentation? There are five major ways:
- Design Rationale: Justifies architectural decisions by discussing quality attribute requirements and trade-offs.
- Interface Documentation: Specifies quality attribute constraints or properties for architectural elements providing services.
- Attribute “Language”: Quality attributes shape recognizable architectural patterns that experts can identify.
- Requirements Mapping: Shows how architectural elements fulfill both functional and quality attribute requirements.
- Stakeholder Roadmap: Guides stakeholders to where their quality concerns are addressed in the documentation.


**Documenting Architectures That Change Faster Than You Can Document Them** 
In this case:
- Document what is true about all versions of your system - this makes the documented arch. more a description of constraints or guidelines for every version.
- Document the ways the architecture is allowed to change - adding and replacing components.

*Seven Rules for Sound Documentation*
1. Write Documentation from the Reader’s Point of View
2. Avoid Unnecessary Repetition
3. Avoid Ambiguity
	- 3a: Explain Your Notation
4. Use a Standard Organization (template)
5. Record Rationale
6. Keep Documentation Current but Not Too Current
7. Review Documentation for Fitness of Purpose


### Architecture Evaluation
Determines the properties, strengths and weaknesses of software architecture.

It provides assurance to developers that their chosen architecture will meet both functional and non-functional quality requirements. 

The goal is to determine the degree in which a software architecture or an architectural style satisfy the quality requirements.

*Who's Involved?* Evaluation Team and Stakeholders.

Three forms of Evaluation:
- Eval. by the designer within the design process
- Eval. by peers within the design process
- Analysis by outsiders after design.

*Why To Evaluate an Architecture?* 
- Forces Preparation for Review - Docs/Specs., prepare for standard questions...
- Early detection of problems - unreasonable requirements, performance problems, problems for future modification
- Validating requirements - uncovers conflicts and tradeoffs, provides a forum for negotiation
- Improved architecture - design arch with evaluation questions in mind.


*Planned vs. Unplanned Evals.* 
Planned
- part of the SDLC
- built into plans, budget and schedule.
- scheduled after SA completion.
- are "proactive" and "team building"
Unplanned
- a result of some problem
- "mid course correction"
- are "reactive" and "tension-filled"


#### SA Evaluation Methods
Scenario-based Software Architecture Evaluation Methods
- SAAM, ATAM, ALPSM and ALMA, SBAR, SALUTA, SAAMCS, ESAAMI, etc.
Mathematical Model-based Software Architecture Evaluation
- Software Architecture-based Reliability Analysis (e.g., Cheung [30])
- Software Architecture-based Performance Analysis (e.g., BIM, CM, ABI)
Metrics-based Software Architecture Evaluation Methods
- Early evaluation: `QuADAI` 
- Late evaluation: TLC, FA, MNS, SSC

After extensive research, the Carnegie Mellon Software Engineering Institute (SEI) has come up with three architecture evaluation methods:
- Architecture Tradeoff Analysis Method (ATAM) 
- Software Architecture Analysis Method (SAAM) 
- Architecture Review For Intermediate Design (ARID)

In many expert opinions, ATAM is the best method of the three.

##### The Architecture Tradeoff Analysis (ATAM) Method
ATAM is designed so that evaluators need not be familiar with the architecture or its business goals, the system need not yet be constructed, and there may be a large number of stakeholders. 

ATAM Overview
 Purpose: Evaluates software architecture with a focus on quality attributes and tradeoffs.
 Timing: Can be applied before system construction.
 Scalability: Supports large stakeholder groups.

**Participants** 
 - Evaluation Team: 3-5 external, unbiased experts.
 - Project Decision Makers: Includes project manager, customer, and architect (mandatory).
 - Architecture Stakeholders: Developers, testers, users, etc., who define quality goals (12–15 for large systems).

**Key Outputs** 
- Architecture Presentation: 1-hour overview.
- Business Goals: Clearly articulated and documented.
- Quality Attribute Scenarios: Prioritized and structured.
- Risks & Non-risks: Identified architectural decisions with potential consequences.
- Risk Themes: Systemic issues that may threaten business goals.
- Decision Mapping: Links architecture choices to quality requirements.
- Sensitivity & Tradeoff Points: Decisions impacting multiple quality attributes.

**Intangible Benefits**
- Stronger stakeholder collaboration.
- Improved communication and shared understanding of the architecture.

**Phases of ATAM** 
Phase 1: Present the ATAM
Goal: Introduce the method, clarify expectations, and outline the process and outputs.

Phase 2: Present Business Drivers
- Project decision maker presents the system’s purpose and context.
- Covers key functions, constraints, business goals, stakeholders, and architecturally significant requirements.

Phase 3: Present the Architecture
- Lead architect explains the system’s structure and key design decisions.
- Includes technical constraints, architectural patterns/tactics, and views that address quality concerns.

Phase 4: Identify Architectural Approaches
- Evaluation team identifies and lists architectural patterns and tactics used.
- Based on documentation and the architect’s presentation.

Phase 5: Generate Utility Tree
- Team and stakeholders define and prioritize quality attribute goals.
- Goals are turned into detailed scenarios and ranked (High, Medium, Low) in a utility tree.

Phase 6: Analyze Architectural Approaches
- Evaluation team examines how well identified architectural approaches support the quality attribute scenarios.
- They assess strengths, weaknesses, and potential risks of each approach.

Phase 7: Brainstorm and Prioritize Scenarios
- Stakeholders suggest additional quality attribute scenarios based on their concerns.
- Scenarios are prioritized by importance and difficulty, enriching the utility tree.

Phase 8: Analyze the Architectural Approaches (for the New Scenarios)
- The team analyzes how the architecture supports the newly added scenarios.
- This helps uncover more risks, sensitivities, and tradeoffs.

Phase 9: Present Results
- Evaluation team presents findings: architecture summary, business goals, prioritized scenarios, risks, nonrisks, sensitivity/tradeoff points, and risk themes.
- Stakeholders receive both tangible and intangible outcomes, including improved understanding and communication.


##### Lightweight Architecture Evaluation (LAE)

- A simplified version of ATAM, suited for smaller or lower-risk projects.
- Requires less time and fewer resources, can be done in half to one day.
- Conducted by internal team members, reducing cost and coordination effort.
- Less rigorous than ATAM, so may not uncover deeper architectural issues.
- Enables faster consensus and shared understanding due to fewer participants and streamlined steps.
