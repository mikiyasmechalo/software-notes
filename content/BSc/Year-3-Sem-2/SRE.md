---
title: Software Requirements Engineering
---
# CH 1: Intro to SRE

Software Requirements: 3 levels

1. (Top) Business Requirements - Sponsor POV, scope of the project, B. objectives
2. User Requirements - User POV, User goals, User input and outputs
3. System Requirements - Functional { what the system does } and Non-Functional { how well it does }

## Overview of SR
**Software Requirements** are “what the system is required to do and the circumstances under which it is required to operate".
**Requirements** are “the services that the system should provide and they set out constraints on the system’s operation”. A system's capability, characteristics or quality factor, to have value and utility.

Requirements provide the basis for all of the development work that follows.

Example: **requirements** for a **library system**:
- The system shall maintain records of all library materials including books, serials, newspapers ….
- The system shall allow users to search for an item by title, author.
- The system’s user interface shall be implemented using a World-Wide-Web.
- The system shall support at least 20 transactions per second.
- The system facilities which are available to public users shall be demonstrable in 10 minutes or less.

**Types of  System Requirements** 
Very general requirements - (Objective, goal).

1. **Functional requirements**: define part of the system’s functionality ( what it must do )
	- May involve calculations, technical details, data manipulation and processing, and other specific functionality.
    
2. **Non-functional requirements**: System properties (e.g., safety, security, reliability ,maintainability, availability… );
	- Implementation requirements - implemented how?
	- Performance requirements - specify a minimum acceptable performance
	- Usability requirements - how easy it to use the system.
	- Compatibility requirements: with other applications and processes.

## Requirements Activities in the System Life Cycle
1. **Identifying the stakeholders** - anyone who has an interest in the system.
- **System stakeholders** are people or organizations who will be affected by the system and who have a direct or indirect influence on the system requirements.
	- Includes - end-users, managers and others in the organizational process, engineers, customers and external bodies such as regulators.
- E.g. stakeholders in health care include - patients, caregivers, doctors, nurses, employees, Gov’t, Insurance companies and pharmaceutical companies.

2. **Requirements elicitation:** Gaining an understanding of users’ needs for the planned system and their expectations of it.
- Steps:- Understanding the app. domain → Identifying the sources of requirements → Analyzing the stakeholders → selecting the techniques and tools, → Eliciting the requirements.

3. **Identifying and clarifying requirements:** using simple sentences, ensure that _they describe the customer’s real needs_ and _are in a form that can be understood and used by developers of the system._

4. **Analyzing the requirements:** to _ensure that they are well defined_ and that they conform to the criteria of a good requirement.

- **Sorting information**: to separate customers’ R, users’ R and standards information. etc.
- **Modeling information**: formalize in a Functional Analysis System Techniques (FAST) _through a Functional Analysis of the organization_, as Functional and Non functional requirements. here we can use UML.
- **Structuring requirements**: A reusable form implied considering an _implementation of the requirements through a database_. Class diagrams used.
- **Validating requirements**: A comparison between use cases and the last level of the FAST with a pivot table assured the _completeness and concordance_ of the information in the database.

5. **Defining the requirements:** spending considerable time and effort to achieve a common understanding of each stakeholders perspective of the system requirements.

6. **Specifying the requirements:** requires including all _of the precise detail of each requirement so that it can be included in a specification document_.

7. **Prioritizing the requirements:** we may not have enough _time or money_ to do everything. Prioritizing helps ensure that an appropriate amount of investment is made in meeting various customer needs.

8. **Deriving requirements:** some requirements _that come about because of the design of a system_, but do not provide _a direct benefit to the end user_. e.g. A requirement for _disc storage_ might result from the need _to store a lot of data._

9. **Partitioning requirements:** _that can be met by hardware, software, training, and documentation_.

10. **Allocating requirements:** _We allocate requirements to different subsystems and components of the system_.

11. **Tracking requirements:** _trace or track_ where in the system each requirement is satisfied, so as to verify each is addressed. usually by using an automated tool.

12. **Managing requirements:** _add, delete, and modify requirements during all of the phases_ of system.

- Requirements for a system always change to reflect
    - changing needs of system stakeholders
    - changes in the environment
    - changes in the business

13. **Testing and verifying requirements:** checking requirements, designs, code, test plans, and system products to ensure that the requirements are met.

14. **Validating requirements:** process for confirming that the real requirements are implemented in the delivered system. keeping priorities in mind.

## Common Requirements problems
- Requirements not reflecting the real needs of the customer for the system.
- inconsistent and incomplete.
- expensive to make changes to requirements after they have been agreed.
- misunderstandings between customers, persons developing the requirements and engineers developing and maintaining the system.

What happens when the requirements are wrong?
1. the system may be delivered late and cost more than expected.
2. customer and user are not satisfied with the system. may not use it or scrape it.
3. system may be unreliable in use, errors and crashes. &
4. If used maintenance cost is high.

### Requirements engineering process
**Process activities** include
- requirements elicitation
- requirements analysis and negotiation,
- specification and requirements validation.

A **complete process description** should include,
- The activities carried out and their structuring or schedule
- who is responsible for each, the inputs and outputs
- tools used to support RE.

Each organization must develop its own process appropriate for the type of systems it develops, its culture, and the level of experience and ability of the people involved in requirements engineering.

## Systems Engineering
**Computer-based systems**  fall into two broad categories:
- _**User-configured systems**_ where a purchaser(buyer) puts systems together from existing software products. Majority of PC.
    - E.g. word processor, a drawing package and a file exchange program are installed on Machines to create a ‘writing system.

- _**Custom systems**_ where a customer produces a set of requirements for hardware/software system and a contractor develops and delivers that system.    
    - E.g.: very small size of embedded systems like, microwave ovens, military messaging systems.

**Classes of custom systems** 
**Information systems**:
- concerned with processing information which is held in some kind of database.
- Usually implemented using standard computer hardware and built on top of commercial O.S.

**Embedded systems:**
- Systems where software is used as a controller in some broader hardware system.
- from simple systems(e.g. in a CD player) to very complex control systems(e.g. in a chemical plant).

**Command and control systems:**
- combination of information systems and embedded systems where special purpose computers provide information which is collected and stored in a data base.
- involve a mix of different types of computer which are networked in same way.
- Within the whole system, there may be several embedded systems and information systems.

e.g. air traffic control systems, railway signaling systems, military comms, etc.
- Requirements engineering for these systems includes _hardware and software specification and a specification of the operational procedures and processes_.


# CH - 2 : Requirement Elicitation
- It is the process of understanding and deriving the system requirements through observation of existing systems, discussions with potential users and customers and task analysis.
- To find out about
	- the application domain
	- services the system should provide
	- the required performance
	- hardware constraints, etc..

### Components of requirements elicitation
A loop between the 4:
**Application domain understanding** 
- knowledge of the general area where the system is applied.
	- e.g. knowledge about libraries for developing a cataloguing system. or about railways and trains for a railway signaling system.

**Problem Understanding** 
- details of the specific customer problem where the system will be applied.
	- e.g. understanding how a particular library categorizes its collection for a cataloguing system, or knowing about speed limits on track segments for RSS.
- here we are specializing and extending general domain knowledge.

**Business Understanding** 
- how the systems interact and contribute to overall business goals.

**Understanding the needs of stakeholders and constraints of the system**
in detail the specific need of people who require system support in their work and constraints of systems.


### Requirement Elicitation Stages
1. **Objective Setting**: overall org. objectives: why the system is necessary in the environment.
	- Business Goals
	- Problem to be solved
	- System constraints
2. **Background knowledge acquisition**: understanding background info about the system.
	- Organizational structure
	- Application domain
	- Existing systems
3. **Organize Knowledge**: prioritize and collate the large data collected in the previous phases.
	- Stakeholder Identification
	- Goal Prioritization
	- Domain knowledge filtering
4. **Collect requirement**: involve stakeholders to discover their requirements
	- Stakeholder requirement
	- Domain Requirement
	- Organizational Requirement


### Elicitation Techniques
#### 1. Interviews
- Conducted by the business analyst from an individual or group of stakeholders to build up an understanding of their requirements.

Two Types of interview:
- **Closed interviews**: The requirements engineer looks for answers to a pre-defined set of questions.
	- e.g. do you currently use any other software? - Any issues with the existing product?
- **Open interviews**: no predefined agenda just discussing, in an open-ended way, what stakeholders want from the system.
	- e.g. can you elaborate on your daily workflow? - what specifications do you look forward in the software? - what could we improve in the new system?

**Interview Essentials** 
- being open-minded, should have no preconceived designs about what is required.
- Stakeholders must be given a starting point for discussion. e.g. a question, req. proposal or an existing system.
- Interviewers must be aware of organizational politics. many real requirements may not be discussed because of their political suggestions.
**Interviews** 
- Require preparation and good communication
- Interview as many stakeholders as possible
- Ask problem-oriented questions. about specific details.
	- Detailed and solution-specific questions may miss the stakeholder’s real requirements.

**Interviews – Objectives and Process**
Three main objectives:
- **Record** information to be used as input to requirements analysis and modeling.
- **Discover** information  from interviewee accurately and efficiently.
- **Reassure** interviewee that his/her understanding of the topic has been explored, listened to, and valued.

**Process consists of four important steps:**
- Planning and preparation
	- goals for interview, background knowledge, prepare questions in advance, organize the environment for an interview. e.g. how to take notes:- manually, audio, by whom...
- Interview session
	- make the interviewee comfortable and confident, 
	- be polit and respectful, be persistent but flexible about your goals.
	- Interview several people at once to create synergy
	- Try to detect political aspects as they may influence, the said and the unsaid.
- Consolidation of information(from different stakeholder)
- Follow-up to find out more information , or to clarify things.

**Interview - Elicitation Notes**
- quickly finalize the elicitation notes right after the interview to not forget the details.
- identify inconsistencies and address them in follow-ups. 
- identify terminologies and make glossary if necessary.

**Common Interview Mistakes**
- not interviewing all the right people.
- asking direct questions too early.
- interviewing one at a time instead of in small groups, creates synergy: group > sum of individuals.
- take every opportunity to show you think the stake holder is smart.


#### 2. Scenarios
A scenario is a scene or story that depicts user interaction with a proposed system.
- (according to the UML) it is an instance of a use case
	- A specific actor ...
	- At a specific time ...
	- With specific data …
- Many scenarios may be generated from a single use case description

A use case includes primary and secondary scenarios
- Primary scenario - Normal course of events
- Secondary scenario - alternate/ exceptional course of events.

Example with consensus(general agreement) as a goal
- Primary scenario: vote in a session
- Alternative scenario: voting in several sessions
- Exceptional scenario: what to do with a non-registrant who wishes to vote

**Representation of Scenarios**
Text (informal, formal), diagrams (state, sequence ...), video, animation, comics , storyboard….

#### 3. Observation and social analysis
- People sometimes find it hard to describe what they do. the best way to understand such environment is to observe them at work.
- **Ethnography** is a technique from the social sciences which has proved to be valuable in understanding actual work processes.
Guidelines
- Assume that people are good at doing their job and look for non-standard ways of working.
- Spend time getting to know the people for good trust and relationship.
- Keep detailed notes of all work practices.
- Combine observation with open-ended interviewing or other techniques.

#### 4. Requirement Reuse
Taking the requirements which have been developed for one system and using them in a different system.
Saves time and effort b/c they've already been analyzed and validated in other systems.

**Reuse possibilities**
- Where the requirement is concerned with providing *application domain information*.
- Concerned with the style of *information presentation*. Useful for consistency across apps.
- Where the requirement reflects *company policies* such as security policies.

### Elicitation problems
- Not enough time for elicitation.
- Insufficient preparation by engineers.
- Stakeholders are unconvinced of the need for a new system.

# CH - 3: Requirements Analysis
The goal is analysis is to discover problems like _incompleteness_, *ambiguity* and _inconsistencies_ in the elicited requirements.
Analysis can be performed at elicitation time or after requirements are gathered.
We use  problem checklist or guidelines to support analysis.
##### Analysis checklists
- **Premature Design**: Does the requirement include premature design or implementation details?
- **Combined Requirements**: Can the requirement be broken down into several different requirements?
- **Unnecessary Requirements**: Is the requirement a non-essential cosmetic addition?
- **Non-standard Hardware/Software**: Does the requirement necessitate non-standard hardware or software?
- **Conformance with Business Goals**: Is the requirement aligned with the defined business goals?
- **Requirements Ambiguity**: Is the requirement ambiguous? What are the possible interpretations?
- **Requirements Realism**: Is the requirement realistic given the implementation technology?
- **Requirements Testability**: Is the requirement testable by engineers?

There are different types of requirement quality.

1. **Testable**: *Example*: "The system shall allow users to log in within 2 seconds.
2. **Atomic**: Each requirement should not be possible to separated out into components.
   - *Example*: "The system shall send an email notification when an order is shipped."
3. **Uniquely Identified**: for easy reference and tracking.
   - *Example*: "REQ-001: The system shall support password recovery."
4. **Complete**: should fully describe the functionality without leaving out necessary details.
   - *Example*: "The system shall validate user input and display an error message if the input is invalid."
5. **Traceable**: should be traceable to business objectives and other related artifacts.
   - *Example*: "The system shall comply with GDPR regulations to ensure user data privacy (linked to business objective OBJ-003)."
6. **Consistent and Unambiguous**: should be clear and not contradict other requirements or system goals.
   - *Example*: "The system shall display the user's name on the dashboard after login, using the name stored in the user profile."
7. **Prioritized**:  should have a defined priority to guide development and resource allocation.
   - *Example*: "High Priority: The system shall encrypt all sensitive user data during transmission."


**Requirement interactions**
Refer to the relationships and dependencies between different requirements in a system or project.
Important objective of requirements analysis is to discover the interactions between requirements and to highlight requirements conflicts and overlaps.

A requirements interaction matrix shows how requirements interact with each other.
- For conflicts we put 1
- For overlap 1000
- For independent fill with 0

**Requirements negotiation** is the process of discussing requirements conflicts and reaching a compromise that all stakeholders can agree to.
Stages:
- Information Stage: Problems with a requirement are clearly explained.
- Discussion Stage: Stakeholders discuss potential resolutions and can assign priorities. All interested parties should have a chance to comment.
- Resolution Stage: Actions are agreed upon for the requirement, such as deleting it, modifying it

# CH - 4: Requirement Specification
A **Requirements Document (RD)**, also known as a functional specification or system requirement specification, is a formal document that provides a detailed description of a software development project. 
It's the blueprint for how software should function, how users will interact with it, and the constraints it must adhere to.
It has d/t names in different organizations such as the *requirements document*, the *functional specification*, the *system requirements specification*, etc.
### What an RD Describes and Includes
The RD serves as a crucial communication tool, detailing:
* **Services and Functions:** What the system should provide.
* **Constraints:** Conditions under which the system must operate, including emergent properties.
* **Overall System Properties:** Characteristics like performance, usability, and reliability.
* **Integration:** Definitions of other systems it must integrate with.
* **Application Domain Information:** Contextual details relevant to the software's environment.
* **Development Process Constraints:** Limitations on how the software is built.
* **External Interfaces and Interactions:** How the system connects with external entities.
* **Design Constraints and Environmental Limitations:** Specific restrictions on the system's design and operational environment.

### Stakeholder Engagement
Different system stakeholders, each with unique backgrounds and needs, will read and utilize the requirements document in various ways:
* **System Customers:** Review and specify requirements, ensuring they meet their needs, and request changes.
* **Project Managers:** Use it for planning bids and managing the development process.
* **System Engineers:** Understand the system being developed.
* **System Test Engineers:** Develop validation tests.
* **System Maintenance Engineers:** Comprehend the system and its component relationships for ongoing support.

### Standard Structure: IEEE/ANSI 830-1993
The IEEE/ANSI 830-1993 standard proposes a widely recognized structure for RDs, typically including:
1.  **Introduction:** Purpose, scope, definitions, references, and document overview.
2.  **General Description:** Product perspective, functions, user characteristics, general constraints, assumptions, and dependencies.
3.  **Specific Requirements:** Detailed functional, non-functional, and interface requirements (e.g., performance, database, design constraints, quality attributes).
4.  **Appendices.**
5.  **Index.**

Organizations can **adapt this standard** based on the specific systems they develop. 
For instance, a company like XYZ, specializing in scientific instruments, might tailor the structure to include new sections like "Hardware Specification" or detailed chapters on "System Architecture" and "Detailed Software Specification," along with a comprehensive glossary and multiple indexes.

### Effective Requirements Writing
Requirements are often written in natural language, supplemented by diagrams and equations. However, common pitfalls can hinder clarity and understanding.

**Common Problems**:
* **Complex Conditional Clauses:** Overly convoluted "if-then" statements.
* **Inconsistent Terminology:** Disordered and varied use of terms.
* **Assumed Knowledge:** Omitting essential information by assuming reader familiarity with the domain or system.

**Key Writing Guidelines**:
To ensure clarity and effectiveness, consider these essential points:
1.  **Readability is Paramount:** Requirements are read more often than written; invest time in making them understandable.
2.  **Diverse Audience:** Don't assume all readers share your background or terminology.
3.  **Allow Time for Iteration:** Budget time for review, revision, and redrafting.

**Practical Guidelines for Writing**:
* **Standard Templates:** Use predefined formats for different requirement types to ensure completeness and consistency.
* **Simple, Consistent, Brief Language:** Employ short sentences and paragraphs, lists, and tables. Avoid jargon where possible.
* **Appropriate Diagrams:** Use diagrams for broad overviews and to illustrate relationships, avoiding excessive complexity.
* **Diverse Notations:** Supplement natural language with other familiar notations, such as equations, when appropriate.
* **Quantitative Specification:** Whenever possible, specify requirements quantitatively, especially for attributes like reliability, usability, and performance.

---
# CH - 5: Requirement Validation
### Analysis and Validation
Validation is the final stage of requirements engineering.
**Analysis**: works with raw req. as elicited. 
- “Have we got the right requirements” is the key question to be answered at this stage.
**Validation**: works with a final draft of the requirements document. i.e. agreed. final stage.
- “Have we got the requirements right” is the key question to be answered at this stage.

**Requirements Validation: inputs and outputs**
*Inputs* : Requirements Document, Organizational knowledge, Organizational standards
*Outputs* : List of problems, Agreed actions: in response to problems.

#### Requirements reviews
A group of people read and analyze the requirements, look for problems, meet and discuss the problems and agree on actions to address these problems.

**Review Process** 
Plan review -> Distribute documents -> Prepare for review -> Hold review meeting -> Follow-up actions -> Revise document.

**Problem actions** 
- **Clarify Requirements**: Address poorly expressed or incomplete requirements by revisiting collected information.
- **Fill Missing Information**: Identify and obtain any missing information from system stakeholders.
- **Resolve Conflicts**: Negotiate with stakeholders to resolve significant conflicts between requirements.
- **Adjust Unrealistic Requirements**: Consult stakeholders to modify requirements that are not feasible with current technology or constraints.

**Pre-review checking** - one person checks the document and looks for straightforward problems such as missing requirements, lack of conformance to standards, typographical errors, etc. before the review to minimize costs.

**Review checklists**
- **Understandability**: Are the requirements clear to all readers?
- **Redundancy**: Is there any unnecessary repetition of information?
- **Completeness**: Are there any missing requirements or information in individual descriptions?
- **Ambiguity**: Are the terms clearly defined, and could different readers interpret the requirements differently?
- **Consistency**: Are there any contradictions between different requirements or between individual and overall system requirements?
- **Organization**: Is the document well-structured, with related requirements grouped together?
- **Conformance to Standards**: Does the document conform to defined standards, with justified departures?
- **Traceability**: Are requirements uniquely identified and linked to related requirements and their inclusion reasons?

##### Requirements problem example
e.g.
•“4. EDDIS will be configurable so that it will comply with the requirements of all UK and (where relevant) international copyright legislation. Minimally, this means that EDDIS must provide a form for the user to sign the Copyright Declaration statement. It also means that EDDIS must keep track of Copyright Declaration statements which have been signed/not-signed. Under no circumstances must an order be sent to the supplier if the copyright statement has not been signed.”

**Problems:**
Incompleteness: 
- What international copyright legislation is relevant?
- What happens if the copyright declaration is not signed?
- If a signature is a digital signature, how is it assigned?

Ambiguity:
- What does signing an electronic form mean? Is this a physical signature or a digital signature?

Standards:
- More than 1 requirement. Maintenance of copyright is one requirement; issue of documents is another.

### Prototyping
Prototypes for requirements validation demonstrate the requirements and help stakeholders discover problems.
Validation prototypes should be complete, reasonably efficient and robust. It should be possible to use them in the same way as the required system.


**Prototyping for requirements validation activities**
- **Choose Prototype Testers**: Select experienced, open-minded users from diverse roles to cover different system functionalities.
- **Develop Test Scenarios**: Plan test scenarios to broadly cover requirements; avoid unstructured exploration.
- **Execute Scenarios**: Users independently test the system using the planned scenarios.
- **Document Problems**: Use electronic or paper forms for users to report encountered issues.

**User manual development**
- **Purpose**: Writing a user manual from requirements helps in detailed analysis and reveals document issues.
- **Information in the User Manual**:
  - Description of functionality and implementation.
  - Unimplemented parts of the system.
  - Troubleshooting guidance.
  - Installation and getting started instructions.

#### Model validation
A **model** refers to a structured representation of a system's requirements, design, or behavior. e.g. DFD, ERD ...
- **Objectives**:
  - Ensure each model is self-consistent.
  - Ensure multiple models are internally and externally consistent.
  - Ensure models accurately reflect stakeholder requirements.
- **Methods**:
  - Use automated tools for some checks.
  - Use paraphrasing as an effective checking technique.

#### Requirements testing
- Ensure each requirement is testable.
- Inventing tests helps identify missing or ambiguous information.
- Each functional requirement should have an associated test.

**Test Case Definition**
- Identify usage scenarios for testing.
- Ensure the requirement has enough information for test definition.
- Determine if a single test suffices or if multiple test cases are needed.
- Restate the requirement if necessary to clarify test cases.

**Test Record Form**
- **Requirement’s Identifier**: Unique identifier for each requirement.
- **Related Requirements**: Reference related requirements.
- **Test Description**: Brief description of the test, including inputs and outputs.
- **Requirements Problems**: Document issues that made test definition difficult.
- **Comments and Recommendations**: Provide advice on resolving identified problems.

**Hard-to-Test Requirements**
- **System Requirements**: Apply to the entire system and are difficult to validate due to their broad scope and influence by functional requirements. Non-functional, system-wide characteristics like usability are challenging to test.
- **Exclusive Requirements**: Exclude specific behaviors and are difficult to test exhaustively. For example, ensuring system failures never corrupt the database.
- **Some Non-Functional Requirements**: Require large test sets for validation, such as reliability requirements, making them difficult to validate during requirements validation.



# CH - 6: Requirements Management

Is the process of managing change to the requirements for a system.
- Managing changes to agreed requirements.
- Managing the relationships between requirements.
- Managing the dependencies between the requirements document and other documents produced in the systems engineering process.

Requirements cannot be managed effectively without requirements traceability.
A requirement is traceable if you can discover:
- who suggested the requirement
- why the requirement exists
- what requirements are related to it and
- how that requirement relates to other information such as systems designs, implementations and user documentation.

#### CASE tools for requirements management
- Management involves the collection, storage and maintenance of large amounts of information.
- CASE tools are available which are specifically designed to support requirements management.
- And Other CASE tools such as configuration management systems may be adapted for requirements engineering.
	- E.g. Word Processor, Spreadsheet, Internal tools, Industrial length, commercial RM tools ...

#### A Requirement Management System
Requirements management tools collect together the system requirements in a database or repository and provide a range of facilities to access the information about the requirements. These facilities may include:
![[Pasted image 20250521082401.png]]


### Stable and volatile requirements
Requirements changes occur while the requirements are being elicited, analyzed and validated and after the system has gone into service.

**Stable requirements** are concerned with the essence of a system and its application domain.
- Derived from the client’s principal business activities or the domain model, (change slowly).
- E.g., a hospital will always have doctors, nurses, patients…

**Volatile requirements** are specific to the instantiation of the system in a particular environment for a particular customer at a particular time
- E.g., in a hospital, we can think of requirements related to the policies of the government health system

#### Requirements change factors
1. **Errors/Inconsistencies**: Mistakes or conflicts in requirements discovered during analysis or development.  
2. **Evolving User Knowledge**: Users better understand their needs as the system develops.  
3. **Technical/Schedule/Cost Issues**: Implementation challenges make some requirements impractical.  
4. **Changing Priorities**: Business shifts alter customer focus and requirements.  
5. **Environmental Changes**: External factors force system adjustments for compatibility.  
6. **Organizational Changes**: Internal restructuring leads to new system demands.

#### Types of volatile requirement
1. **Mutable Requirements**: Change due to shifts in the system's operating environment.
2. **Emergent Requirements**: Unforeseen needs that arise during design/implementation.
3. **Consequential Requirements**: Based on initial assumptions that may later prove incorrect.
4. **Compatibility Requirements**: Depend on external systems, tech, or processes.

#### Requirements identification Techniques
1. **Dynamic Renumbering**: Automatic updates to requirement numbers when the document is reorganized (supported by some word processors).  
2. **Database Record ID**: Requirements stored in a database with unique IDs for easy tracking and referencing.  
3. **Symbolic Identification**: Assigning meaningful names (e.g., **EFF-1**, **EFF-2** for efficiency-related requirements).  

### Storing requirements
In such a way that they can be accessed easily and related to other system requirements.

**Word processor**
*Advantages:*  
1. Centralized storage in one file.  
2. Accessible via common word processors.  
3. Easy to compile into a final document.  

*Disadvantages:*
1. Manual tracking of dependencies.  
2. Limited search functionality.  
3. No direct links to proposed changes.  
4. No version control per requirement.  
5. No automated cross-referencing.  

**Database Storage**  
*Advantages:*
1. Advanced querying and navigation.  
2. Built-in change and version management.  

*Disadvantages:*
1. Requires specific software/skills to access.
2. Must sync database updates with the requirements document.

**Summary**: Documents are simple but lack traceability, while databases offer better management but require more infrastructure.

#### Object classes for requirements Database
![[Pasted image 20250521093819.png]]


  
### Factors influencing the choice -Requirements DB
**1. Statement of Requirements**
- If requirements include **multimedia** (images, diagrams) or complex data, the DB must support rich formats.  

**2. Number of Requirements**  
- **Large-scale systems** need high-performance databases (e.g., SQL servers) to handle thousands of requirements.  

**3. Team Distribution & Collaboration**
- **Distributed teams** require cloud/network-accessible DBs (e.g., JIRA, DOORS Next) with role-based access.  

**4. Integration with CASE Tools**
- The DB should **integrate with CASE tools** (e.g., Enterprise Architect), though proprietary formats may limit compatibility.  

**5. Existing Database Infrastructure**
- Reuse **current engineering databases** (e.g., PLM systems) to avoid redundancy and ensure consistency.  


### Change management
The procedures, processes and standards which are used to manage changes to system requirements.
Change management policies may cover:
- The change request process and info required to process each request.
- The process used to analyze the impact and cost of change and the associated traceability information.
- The membership of the body which formally considers change requests.
- The software support (if any) for the change control process.

#### The change management process
{Problem Identification} -> Problem analysis and change specification -> change analysis and costing -> change implementation -> {Revised requirement}
1. Some requirements problem is identified.
	- From Analysis, new customer needs or operational problems within the system. using this requirement changes are proposed.
2. The prop changes are analyzed.
	- Checks how many requirements are affected by the change and how much it would cost, in both time and money, to make the change.
3. The change is implemented.
	- A set of amendments to the requirements document or a new document (w/c is validated) version is produced.

#### Change analysis and costing process
1. **Change Request Validation**  
    - Check if the request is valid.  
	- If valid, identify directly affected and dependent requirements.  
	- Outcome: Either a **requirement change list** (proceeds) or **rejected request** (stops).  
2. **Propose Requirements Changes**  
	- Assess costs (time/resources) of the change.  
	- Determine cost acceptability.  
	- Outcome: **Accepted change** (proceeds) or **rejected request** (stops).  
3. **Customer Information**  
	- Involves customer input%%, but the depicted path leads to **rejected request** in both branches%%. 

**Change processing**
Proposed changes are usually recorded on a change request form which is then passed to all of the people involved in the analysis of the change.
Change request forms may include:
- fields to document the change analysis.
- data fields.
- responsibility fields.
- status field.
- comments field.

#### Change Management Tools
Can be delivered via **requirements management tools** or **configuration management tools**. 
Key features include:  
- **Electronic change request forms** for stakeholders to submit changes.  
- **A centralized database** to store and manage change requests.  
- **A customizable change model** to track responsibilities and workflow stages.  
- **Automated form routing & email notifications** to alert responsible parties when tasks are completed.  
- **Integration with requirements databases** (in some cases) for direct updates.  


### Traceability
Traceability helps assess the **impact of changes** by establishing **links between requirements and related system artifacts** (e.g., design, implementation, source documents).  
Types of Traceability information:
1. **Backward-from traceability** – Connects requirements back to their **sources** (e.g., stakeholder inputs, regulations, earlier documents).  
2. **Forward-from traceability** – Tracks how requirements **flow into design and implementation** (e.g., code, test cases).  
3. **Backward-to traceability** – Maps **design/implementation components back to requirements** (ensures coverage).
4. **Forward-to traceability** – Links **pre-existing documents** (e.g., business goals) to later **requirements** (shows derivation).
![[Pasted image 20250521102952.png]]

#### Types of Traceability
1. **Requirement-Sources traceability** – Connects requirements to stakeholders/docs.
2. **R-Rationale T** – Explains *why* a requirement exists.
3. **R-Requirements - T** – Shows dependencies between requirements.
4. **R-Architecture - T** – Maps requirements to subsystems.
5. **R-Design - T** – Tracks implementation in components.
6. **R-Interface - T** – Links to external systems/APIs.

#### Traceability Management
1. **Traceability Tables**
	- Show relationships between requirements or requirements and design components.
	- Rows/columns list requirements; cells mark dependencies.
	- Best for small-scale tracking (e.g., using spreadsheets).
2. **Traceability Lists**
	- Simplified alternative for large requirement sets.  
	- Lists related requirement IDs alongside each requirement.  
	- Avoids sparse, unmanageable matrices.  
3. **Traceability Policies**
	Define rules for maintaining traceability, including:  
	- **What info to track** (e.g., sources, dependencies).  
	- **Methods** (matrices, lists).  
	- **When to collect data** (phases in development).  
	- **Roles** (e.g., traceability manager).  
	- **Handling exceptions.**  

#### Factors Influencing Traceability Policy
1. **Number of Requirements**  - More requirements → Need for stricter traceability policies.  
2. **System Lifetime**  - Longer lifespan → More detailed traceability required.  
3. **Team Size & Composition**  
	- Small teams → Informal tracking may suffice.  
	- Large/multi-team projects → Formal policies essential.  
4. **System Type**  - Safety-critical/real-time systems → Rigorous traceability mandatory.  
5. **Customer Requirements**  - Contractual obligations may dictate specific traceability deliverables.  
**Summary:** Tailor traceability policies based on project scale, complexity, and risk.












