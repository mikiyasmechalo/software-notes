---
title: Software Component Design
teacher: Gizate D.
---
# CH 1: Intro and Basic Concepts

**SWE** is a branch associated with the development of software product using well-defined scientific principles, methods and procedures.
Software engineering helps to reduce programming complexity by using two important techniques:  abstraction and decomposition
- **Abstraction** is simplifying the problem by omitting irrelevant details.
- **Decomposition** is dividing the problem into small & manageable sub problems.

Types of software
- *Purpose*: System or Application Software
- *Platform*: Native or Cross-Platform
- *Deployment*: Installed or Cloud-based
- *License*: Proprietary or Open-source
- *Size*: Small-scale or Enterprise
- *User* Interface: GUI or CLI

**Design** is a process to transform user requirements into some suitable form, which helps the programmer in software coding and implementation.
- transforming user requirements(problem domain) -> implementation(solution domain)

What to design?
- Data / Database design
- UI / Front end design
- Architecture design
- Component / Sub-divisions - functional modules with own tasks

**Component based design** 
It focuses on the decomposition of the design into individual functional or logical components that represent well-defined communication interfaces containing *methods*, *events*, and *properties*.
It provides a higher level of abstraction and divides the problem into sub-problems, each associated with component partitions.

**Why?** 
- To reduce the software crisis such as complexity, difficulty, quality…
- Different standalone components are being engineered to be used for own purpose
- to have reusable components for new projects. -> faster time to market.

**What is component?** 
A software component is a unit of composition with contractually specified interfaces, independently deployable/ deliverable/ configurable and subject to composition by third parties.

From “buy or build” to “buy and build”. - CBSE gives a chance to assemble the system from existing software components(BUY) or/and follow the design pattern to build our own system(BUILD).

**Benefits of CBSE** 
- Reuse of existing solutions than inventing new ones
- allows designers to focus on important issues
- Reduces development time and cost, Reduce time to market
- Easy to replace or maintain

**Characteristics of CBSE** 
- Reusable, - Replaceable
- Encapsulation & Abstraction
- Composable, Independent/ self-contained
- Deployable/configurable/deliverable
- Logically cohesive / High cohesion - Components should contain related and closely related functionalities.
- Loosely coupled  - Components should interact with each other through well-defined interfaces
- Scalable/ extensible
- Maintainable

**Types of CBSE** 
- *Class-Based Components* - often implemented as Classes in OOP and encapsulate data and behavior.
- *Service-Based Components* - provide specific services or functionalities and may be implemented as standalone modules or microservices.
- *Web Components* - designed to be used in web applications and are encapsulated HTML, CSS, and JavaScript.

**Processes in CBSE** 
Req. Analysis -> Component Identification -> Specification -> Design Composition -> Data Design -> Algorithm Design

- *Requirements Analysis*: Functional and non-functional requirements for the system as a whole, defining what the overall software must accomplish.
- *Component Identification*: Identify the specific functionality or feature that the component will provide within the overall system. Consider reusability.
- *Specification*: Define the component's interface, including methods, parameters, and data structures. - its purpose.
- *Design Decomposition*: Break down the component into smaller, manageable sub-components or modules, if necessary.
- *Data Design*: define data structures and data flows, including how data is processed and stored.
- *Algorithm Design*: Specify the algorithms and logic that the component will use to perform its functions.

#### Where CBSE is used? Application:
1. **Enterprise Application**: use modular components for HR, payroll, and customer management systems.
2. **Web Applications**: Modern web applications rely on reusable front-end and back-end components.
3. **Cloud-Based Systems**: Cloud services often use microservices, which are individual components that can scale independently.
4. **Embedded Systems**: Devices such as smart appliances use modular components to manage specific tasks like sensor monitoring or user input.


**Processes Involved During Component Design** 
1. *Requirement Analysis*: Identify the specific functionality the component needs to perform.
2. *Specification*: Define the component's interface, expected inputs, outputs, and how it will interact with other components.
3. *Design and Implementation*: Build the component while following the defined specifications.
4. *Testing*: Components are individually tested for functionality and performance before being integrated into the larger system.
5. *Integration*: Combine components with the larger system and ensure seamless interaction.

# CH 2: Software Component Specification And Repositories
Software components can be:
- Off the Shelf components - ready-made, purchased from vendors, minimal to no customization.
- Third-party components - developed by external companies, used to add specialized features.
- Full-experience components - Existing component from another app, used as-is.
- Partial-experience components - Existing component that needs customization before use.
- New components - built from scratch for unique project needs.

**Software Component Specification** 
- is a blueprint for a particular software component.
- outlines things necessary to understand, build and integrate a component.
- depicts the specific set of hardware and software components that make up the system.
- it should focus on what the software is to do (functionality) rather than how (implementation mechanisms).
- Can range from high-level overviews to intricate/complicated low-level details, depending on the project's scope and the development phase.

**What does a Software components Specification contain?** 
- **Functionalities**: the actions the component performs.
- **Interfaces**: How other components or systems interact with it.
- **Dependencies**: external systems, libraries or components
- **Interactions**: Communication rules
- **Responsibilities**: the scope of the tasks the component handles.

#### Provides and requires interfaces
A component specification describes the component only through its interfaces. `Sommerville`
distinguishes two kinds:
1. **Provides Interface**: services the component offers to other components.
2. **Requires Interface**: services the component needs from other components.

`Szyperski`: a component is “a unit of composition with contractually specified interfaces and explicit context dependencies only” – the requires interface makes those dependencies explicit.

**A specification is a contract: four levels of contractual detail** 
1. *Syntactic* - Interface definitions – operation names, parameters and types – so components can be assembled.
2. *Behavioral* - Pre-conditions and post-conditions (and invariant) that state what each operation requires and guarantees.
3. *Synchronization* - (when/how to call it) Rules for the order and concurrency of calls – how operations may be coordinated.  Prevents race conditions and invalid call sequences.
4. *Quality of Service* - Measurable properties such as response time, availability and quality of results. Non-functional guarantees

### Software Component Repository
A repository, or repo, is a centralized digital storage that developers use to make and manage changes to an application’s source code.
- has features that allow developers to easily track code changes, simultaneously edit files, and efficiently collaborate on the same project from any location.
- Anyone of the stakeholders can pull from the repo for new features or bug fixes.

**Why use a Repository?** 
- It allows software development teams to implement multiple changes to a software’s program code without compromising the main source code. - (branches, Merge conflicts)
- To introduce new features or bug fixes without affecting the production version of the application.

**Types Of Repositories** 
- Local Repository - Hosted within an org. secure and private.
- Public Repository - open to all, promotes sharing and open-source collaboration.
- Hybrid Repository - combines both to achieve selective sharing. e.g. enterprise GitHub setups.

*Package registries: repositories of reusable components* 
- `npm` registry
- `maven` central
- `pip`, `PyPI`
- `NuGet` Gallery
- `Docker Hub`

*Advantages of Repositories* 
- Contribution
- Documentation - using repo tools to develop robust documentation
- Portfolio - acts as a portfolio for developers
- Integration with Other Tools
- Track Changes for Multiple Versions and Blame

*Popular example Repositories* 
- **GitHub** - based on git, enables team collaboration and review workflows.
	- Has GitHub actions for CI/CD automation
	- Integrates with tools like VS code, slack and docker
	- Ideal for OSS, academic and professional projects

- **Bitbucket** - by `Attlasian`. fully integrates with `Jira`.
	- supports git
	- Provides Bitbucket Pipelines for CI/CD automation.
	- has branch-level permissions.
	- pull requests and peer code reviews.
	- best for enterprise and Agile development teams.

#### Constructs of Repository
1. **Version Control System (VCS)**: a software that helps manage changes to files over time.
	 - Tracks modification, maintains a historical record of changes and enables collaboration among multiple contributors.
2. **Local Repository** -  resides on a developer's machine.
3. **Remote Repository** - central storage location where the project is shared among multiple developers. e.g. GitHub, GitLab, ...
4. **Branch** - a parallel version of the code. allows developers to work on different features or bug fixes independently. they stay independent until merge.
5. **Merge** - the process of combining changes from one branch to another.
6. **Commit** - a commit is a snapshot of changes made to the files in a repository. has a unique identifier and usually accompanied by a message.
7. **Clone** - process of creating a local copy of a remote repository.
8. **Pull** - process of fetching changes from a remote repository and merging into the local.
9. **Push** - sending committed changes from local to remote repository.
10. **Fork** - allows developers to create their own copy, which they can make changes to their fork and propose the changes to the original repository through a pull request.
11. **Tag** - a specific point in the version history marked for reference. often used to label releases or important milestones.
12. **Issues** - a way to track tasks such as enhancements, bugs or other questions.
13. **README** - a document that provides info about a project. How to install, use or contribute.
14. **Collaborators and Teams** - manages who can access and modify the repository.

**Three Generations of Version Control** 
1. **Local VCS** - a simple DB on one developer's machine to keep history of file changes. e.g. RCS (Revision Control System)
2. **Centralized VCS** - one central server holds all versioned files, clients check out files. e.g. CVS(Concurrent Versions System), SVN(Subversion)
3. **Distributed VCS** - every client fully mirrors the repository including complete history, any copy can restore the server. e.g. Git, Mercurial

**A typical GitHub workflow** 
Fork/Clone -> Branch -> Commit -> Push -> Pull request -> Merge -> Tag release

# CH 3: Component Interface, Qualification and Adaptation

### Attributes of Components
- Effective software component design involves defining the structure, behavior, and interactions of each component to ensure the overall system meets its requirements.]

**Key Attributes and Considerations in Component Design** 

- **Modularity**: components should be self contained and can easily be understood, developed, tested and maintained independently.
- **Encapsulation**: hiding the internal details of a component and exposing only the necessary interfaces. Enhances security, reusability and maintainability.
- **Abstraction**: simplifying complex systems by modeling class based on their essential characteristics.
- **Reusability**: allowing them to be easily integrated into different parts of the system or even in other projects.
- **Scalability**: able to handle increased loads or additional features without significant redesign.
- **Flexibility**: enable modifications and adaptations without affecting the entire system.
- **Interoperability**: able to interact seamlessly with other components and external systems. 
- **Maintainability**: component designs should make it easy to locate, fix and update components. Clear documentation, adhering to standards and use of design patterns help here.
- **Low Coupling**: dependencies between components should be minimized, reduced impact of changes on other components.
- **High Cohesion**: implies that elements in within a component are closely related, focusing on a specific set of responsibilities. Enhances it's effectiveness and ease of maintenance.
- **Consistency**: design patterns, naming schemes, and coding styles should be maintained throughout development for better readability and understanding.
- **Performance**: use of optimization techniques and efficient algorithms should be a part of the component design to ensure the system meets performance requirements.
- **Security**: access control, encryption, and secure communication should be included in design.
- **Testability**: designed to facilitate testing, including being able to isolate and test components independently for easier debugging and maintenance.
- **Documentation**: design specs, APIs and usage guides, are essential for future development, maintenance and collaboration among team members.

These attributes allow us to develop robust, maintainable and adaptable components.

### Component Interface
- the boundary or set of methods through which a component interacts with the rest of the system or with other components.
	- defines how other components or modules can use the functionality of a component.
	- serves as a contract that specifies what the component can do and how it can be used.

**Key aspects of a component interface**:
- *Methods and signature*: defines methods that a component that a component exposes.
	- Includes names of methods, parameters, return types and any exceptions it may throw.
- *Access Control*: w/c methods are public and private.
- *Data Structures*: if it deals with complex data structures, a components' interface may define the structure of these data elements and how they can be manipulated.
- *Contracts and Preconditions/Postconditions*: contracts specify the expected behavior of the component's methods.
- *Dependencies*: interfaces often express dependencies on other components or services.
	- dependencies may be in the forms of method parameters, return types or other.
- *Versioning*: in systems where components evolve independently, interfaces may include version information to manage compatibility.
- *Documentation*: crucial for developers who want to use or implement components. it may include details about each method, expected and examples of usage.

In OOP interfaces are a formal way of defining methods in a component.
- an interface in OOP, is a collection of method signatures without implementations.
- classes w/c implement an interface provide concrete implementations for all the methods declared.

Component interfaces play a crucial role in promoting modularity, reusability, and maintainability in software systems.

#### Characteristics of Component Interface
- *Abstraction*: by defining what a component does without specifying how it achieves its functionality.
- *Encapsulation*: hiding internal details of a class or component. clients are only concerned with the methods declared in the interface.
- *Polymorphism*: interfaces facilitate polymorphism by allowing different classes to be treated as instance of the same interface.
- *Method Signatures*: names, parameters. return types and exceptions a class implementing it must adhere to.
- *No Implementations*: typically* interfaces don't contain any implementations. only declare.
- *Multiple Inheritance*: on many programming languages a class is allowed to implement multiple interfaces.
- *Enforcement of Contracts*: interfaces act as contract, a set of rules the implementing classes must follow. good for consistency and reliability.
- *Interoperability*: interfaces enable different components or modules to interact with each other as long as they adhere to the same interface.
- *Versioning*: interfaces can help manage versioning in a system. When an interface is updated all implementing classes may need to be updated, but other components relying on the old interface can remain unaffected until they are ready to adapt. usually helped by Adapters/ wrappers that let a new provider also satisfy the old interface during transition.
- *Documentation*: interfaces serve as a form of documentation, providing clear and concise specifications of methods and functionalities a component offers.
- *Testing*: interfaces simplify testing by allowing for the creation of mock or stub implementations that adhere to the same interface. stubs help us isolate the logic of an interface rather than external dependencies.
- *Ease of Maintenance*: interfaces provide clear separation between the contract and the implementation.

### Selecting criteria of Component
- How to select the right component for a particular purpose? 
	- our choice can significantly impact system's performance, maintainability and overall success.

*Key Criteria to consider when selecting Software Components*:
- **Functionality**: a component should provide the required functionality specified in the requirements.
- **Compatibility**: Ensure that the software component is compatible with the existing system architecture, programming languages and other dependencies.
- **Reliability**: consider its track record, user reviews, and any available reliability metrics.
- **Performance**: speed, efficiency and resource consumption. to meet system requirements.
- **Scalability**: whether the component can scale to accommodate the future growth.
- **Ease of Integration**: to the existing system. well defined interfaces and documentation helps.
- **Maintainability**: ease of maintaining and updating the component. documentation, modular design and proper versioning help.
- **Community Support**: active community around it. Open source benefit from timely updates and bug fixes from diverse group of developers.
- **Licensing**: ensure the license aligns with the project's goals and constraints.
- **Security**: security features, reputation and its track record.
- **Documentation**
- **Cost**: licensing fees, maintenance cost and potential training expenses.
- **Vendor Support**: the level of support and responsiveness the vendor offers.
- **Interoperability**: if components can seamlessly interact with other components and systems in the environment.

### Adaptation Strategies
Modifying components to ensure their effectiveness, compatibility and performance within a given system.
- Adaptations can be necessary when components need to interact with different environment, handling varying data formats and meet changing requirements.

*Common Adaptation Strategies* 
- **Interface Adapters**: to bridge the gap between different interfaces and communication protocols. Can involve creating wrappers or adapters to translate method calls or messages.
- **Data Format Conversion**: to transform data between formats ensuring compatibility with other components with varying data representations.
- **Middleware Integration**: to facilitate communication and integration between components. Middleware can abstract the underlying complexities of inter-component communications.
- **Aspect-Oriented Programming**: used to modularize cross-cutting concerns, such as logging, security, or error handling. This allows for the dynamic adaptation of these concerns without directly modifying the core component logic.
- **Caching and Performance Optimizations**: caching can be adapted to changing access patterns and reduce load on external services.
- **Proxy or Wrapper Components**: to add an additional layer of control or functionality around existing components.
- **Adaptive Algorithm**: designing algorithms to be adaptive to adjust their behavior based on changing input conditions or system states.
- **Cross-Cutting Concern Modules**: identify and modularize cross-cutting concerns, such as logging, authentication, or error handling, into separate modules that can be dynamically adapted or replaced.



# CH 4: 
