Software Technologies and Enterprise Architectures

# CH1: Introduction to Enterprise Architecture
An **Enterprise** is an organization or a business entity engaged in commercial, industrial, or professional activities. from small businesses to large Corporations.
- The key characteristics of an enterprise is its goal to generate profit, provide goods or services or achieve specific objectives.

**Architecture** in IT refers to the *conceptual structure* and *logical organization* of a system, including its components and their relationships.

**Enterprise Architecture** - is a blueprint of
- permitted structure
- configuration
- functional grouping
- Interface, data, protocol
- Logical functionality
- Integration, technology of IT resources.
to support a corporate or organizational business function or mission.

EA describes - information, process, application and technology and how they are used to help Es.

EA is unique in every organization but has common elements: *business*, *information*, *application* and *technology*. each is described by multiple artifacts.

EA artifacts are used to define target solutions, capabilities, etc.

**Key aspects of EA** 
- Strategic alignment
- Business-IT integration
- Resource Optimization
- Risk Management
- Interoperability and Integration
- Change management
- Decision Support

EA is one part of *Integrated governance* in an Enterprise.

#### Why is EA important?
EA reduces
- Redundancy, complexity and information silos
- business risk associated with IT investments
EA improves
- Business and technology alignment
- Interoperability and information sharing
- ROI
- Flexibility and agility

**Benefits of EA** 
- Strategic Alignment
- Improved Agility
- Cost Optimization
- Enhanced Interoperability and Integration
- Risk Mitigation
- Transparency and Communication
- Scalability and Flexibility
- Innovation and Transformation

#### Roles of an Enterprise Architect
He/ She is a:
**Strategist** - aligns IT strategy with business goals.
- Recommends and participates in activities related to design, dev. and maintenance of EA. 
**Advisor** - provides insights on technology trends and their implications.
**Designer** - Develops architecture models and blueprints. including lower level components.
**Governance** - ensures compliance with standards and best practices.


**EA Focus areas** 5:
1. SOA
2. Identity and Access Management
3. Application 
4. Security 
5. Data

#### Qualities of Good Architecture
- **Holistic View**: Integrates all organizational aspects into a unified, comprehensive architecture.
- **Security**: Emphasizes data protection and regulatory compliance to secure enterprise assets.
- **Scalability**: Designed to grow and evolve with organizational expansion.
- **Robust**: Resilient to minor changes without disrupting core functionality.
- **Feasible**: Ensures enterprise goals are met; tools like Capability Mapping and Element Discussion aid in feasibility.
- **Flexible**: Easily adapts to change with support from tools like Baseline and Kanban diagrams.
- **Verifiable**: Aligns with business goals and allows measurable performance validation.
- **Elegant**: Balances form and function with professional, template-driven visualizations.
- **Traceable**: Clearly links to business drivers using tools like Traceability Window and Relationship Matrix.


#### Domains of EA
**Business Architecture** defines the business strategy, governance organization and key business processes of an enterprise.

*Key Components* 
- Business Strategy
- Business Processes
- Organizational Structure
- Capabilities
- Stakeholders

*Importance* 
- Alignment
- Efficiency
- Agility

**Data Architecture** defines the structure of an organization's logical and physical data assets and data management resources.

*Key Components* 
- Data Models
- Data Flows
- Data Governance
- Data Storage
- Data Security
*Importance* 
- Data Quality
- Informed decision-making
- Compliance

**Technology Architecture** defines the hardware, software, and network infrastructure required to support the deployment and operation of applications and data management systems.

*Key Components* 
- Infrastructure Services
- Technology Standards
- Technical Platforms
- Network Architecture

*Importance* 
- Reliability
- Scalability
- Cost Management
- Security Infrastructure

## EA Frameworks
EA Frameworks provide a structured approach and set of guidelines for developing, implementing, and managing EA.
- Principles, practices, and models that guide the creation and evolution of the EA.

They are:
- The Open Group Architecture Framework (*TOGAF*) - process centric
- *Zachman* Framework - taxonomy/ framework centric
- Federal Enterprise Architecture Framework (*FEAF*) - implementation centric
- *Gartner* Enterprise Architecture Framework - practice/ outcome centric


#### Zachman Framework
- its origins lie with the publication of "A framework for information systems architecture" by Zachman (1987).
- its main goal was to use logical constructs to address the management of ever-increasing complexity if Information systems within orgs.

- *Zachman framework* was a *two dimensional matrix* representing the *viewpoints* on the Y-axis and the *views* on the X-axis.
Viewpoints are represented by:
- different stakeholders and 
- clearly defined deliverables.


| Stakeholder View    | Motivation (Why) | Function (How) | Data (What) | People (Who) | Time (When) | Network (Where) |
| ------------------- | ---------------- | -------------- | ----------- | ------------ | ----------- | --------------- |
| **Scope View**      |                  |                |             |              |             |                 |
| **Owner’s View**    |                  |                |             |              |             |                 |
| **Designer’s View** |                  |                |             |              |             |                 |
| **Builder’s View**  |                  |                |             |              |             |                 |
| **Detailed View**   |                  |                |             |              |             |                 |
###### Aspects:
- **Data (What)**: Information required for the enterprise to function effectively.
- **Function (How)**: Operational processes and activities that drive the enterprise.
- **Network (Where)**: Geographic distribution of enterprise operations and infrastructure.
- **People (Who)**: Individuals involved, their roles, responsibilities, and relationships.
- **Time (When)**: Timing and sequencing of events to meet performance goals.
- **Motivation (Why)**: Strategic drivers including goals, objectives, and business rationale.

###### Layers or views (players):
- **Scope**:(planner) High-level overview of the final structure using diagrams (e.g., bubble charts) to show size, purpose, and relationships.
- **Enterprise/ Business Model**: (owner) Business design or blueprint representing organizational structure and strategy.
- **System Model**: (designer) Detailed specifications created by systems analysts based on the E. model.
- **Technology Model**: (builder) translation of the system model into infrastructure and platform designs.  
- **Detailed Representations**: (sub-contractor) Precise instructions for developers and programmers to implement.
- **Functional Enterprise**: Final working system integrated into the enterprise’s operations.

Zachman Matrix

| **Stage**           | **Viewpoint**     | **Modeling Layer**        | **Focus**                                                            |
| ------------------- | ----------------- | ------------------------- | -------------------------------------------------------------------- |
| ** Identification** | Planner’s View    | Scope Layer               | Defines purpose, scope, and relationships using high-level diagrams. |
| **Definition**      | Owner’s View      | Enterprise/Business Model | Captures business goals, processes, and organizational structure.    |
| ** Representation** | Designer’s View   | System Model              | Translates business needs into logical system specifications.        |
| **Specification**   | Builder’s View    | Technology Model          | Converts logical models into physical infrastructure and platforms.  |
| **Configuration**   | Integrator’s View | Detailed Representations  | Implements detailed technical specs for integration and deployment.  |
| **Instantiation**   | User’s View       | Functional Enterprise     | Final working system embedded into enterprise operations.            |

#### The Open Group Architecture Framework (TOGAF)
TOGAF is a comprehensive methodology including a set of tools to develop an EA.
- offers clear definitions of terms.
**Architecture Development Method** (ADM) is a generic method used to realize an EA in accordance with business requirement.
							![[adm.gif]]



### Comparison of EA Frameworks 

| **#** | **Criteria**             | **Description**                                                                       | **Preferred Framework** |
| ----- | ------------------------ | ------------------------------------------------------------------------------------- | ----------------------- |
| 1     | Taxonomy Completeness    | Ability to classify architectural artifacts effectively.                              | Zachman                 |
| 2     | Process Completeness     | Extent of step-by-step guidance for creating EA.                                      | TOGAF                   |
| 3     | Reference-model Guidance | Helpfulness in building relevant reference models.                                    | FEA, TOGAF              |
| 4     | Practice Guidance        | Support for embedding EA mindset and culture in the organization.                     | Gartner                 |
| 5     | Maturity Model           | Guidance for assessing EA maturity across the enterprise.                             | FEA                     |
| 6     | Business Focus           | Emphasis on using technology to drive measurable business value.                      | Gartner                 |
| 7     | Governance Guidance      | Assistance in creating effective EA governance models.                                | FEA, Gartner            |
| 8     | Partitioning Guidance    | Support for dividing the enterprise into manageable, autonomous partitions.           | FEA                     |
| 9     | Prescriptive Catalog     | Help in setting up reusable architectural asset catalogs.                             | TOGAF                   |
| 10    | Vendor Neutrality        | Likelihood of avoiding lock-in to specific consulting vendors.                        | TOGAF                   |
| 11    | Information Availability | Access to free or low-cost resources and documentation.                               | TOGAF                   |
| 12    | Time to Value            | Speed at which the methodology delivers business value through implemented solutions. | Gartner                 |


**EA Tools** help enterprise architects and other stakeholders plan, model, develop and monitor architectures. They offer
- EA planning
- EA modelling
- EA simulation and Improvement
- EA monitoring and reporting
- Shared artefact repository
- Reusability support


#### Required Steps To Develop EA
1. **Analyze Requirements**: Understand enterprise or segment needs.  
2. **Document Current State**: Record existing business services and IT resources. 
3. **Develop Solutions**: Create business and technology scenarios to meet requirements.  
4. **Set Strategic Goals**: Align goals with enterprise needs.  
5. **Conduct Risk Analysis** 
6. **Choose a Methodology**: Select a suitable EA framework (e.g., TOGAF, Zachman).  
7. **Plan Future Operations**: Define future scenarios and planning assumptions based on current views.

#### Life Cycle of Enterprise Architecture (CYCLE)

1. **Obtain Executive Buy-in and Support**  
   Secure leadership commitment to ensure strategic alignment and resource backing.
2. **Establish Management Structure and Control**  
   Set up governance mechanisms and oversight roles for architecture development.
3. **Define Architecture Process and Approach**  
   Choose the methodology and outline the steps for building the architecture.
4. **Develop Baseline Enterprise Architecture**  
   Document the current state of business processes, systems, and technologies.
5. **Develop Target Enterprise Architecture**  
   Design the desired future state aligned with strategic goals.
6. **Develop the Sequencing Plan**  
   Create a roadmap to transition from the baseline to the target architecture.
7. **Use the Enterprise Architecture**  
   Apply the architecture to guide projects, investments, and decision-making.
8. **Maintain the Enterprise Architecture**  
   Continuously update and refine the architecture to reflect changes and improvements.

#### Levels of Enterprise Architecture
1. **Strategic Architecture**  
   High-level, long-term view of the entire enterprise. Used by senior stakeholders for strategic planning and unified oversight.
2. **Tactical Architecture**  
   Mid-level view focused on specific segments or divisions. Supports operational changes and aligns with programs and portfolios.
3. **Solution Architecture**  
   Detailed view of capabilities and implementation. Guides project-level execution, describing baseline, target states, and capability increments.


#### Enterprise Architecture Habitual Method
EA places significant emphasis on **reuse**, **interoperability** and **service orientation**.
- **Reuse** - leverage existing data, technology and process assets as services.
	- minimize expense, - improve quality, consistency and time to delivery.
	- Increasing security and management opportunities
	- Improved augmentation potential
- **Interoperability** - facilitates reuse and access to information.
	- service is discoverable, reliably available and accessible.
	- high degree of standardization - protocols, definitions and structures etc.
- **Service Orientation** - promotes delivery of services rather than tactical point systems/ apps.

**EA - a collaboration Force** 
![[Pasted image 20251226105305.png]]


**Risks associated with Enterprise Architecture**
- Inability to rapidly respond to new requirements  
- Lack of focus on enterprise requirements  
- Lack of common direction and synergies  
- Incomplete visibility of the current and future vision  
- Inability to predict impacts of future changes  
- Increased gaps and architecture conflicts  
- Lack of commonality and consistency  
- Rigidity, redundancy and lack of scalability and flexibility in the deployed solutions  
- Lack of integration, compatibility and interoperability between applications  
- Piece-meal and ad hoc software development driven by a tactical and reactive approach






# CH2: Introduction to TOGAF

**What is TOGAF** 
TOGAF  is described in a set of documentation w/c may be used freely by any organization wishing to develop an enterprise architecture for use within that organization.
TOGAF is a tool for assisting in the acceptance, production, use, and maintenance of enterprise architectures.
It is based on an iterative process model supported by best practices and a re-usable set of existing architectural assets.

TOGAF KEY CONCEPTS:
- ADM
- Architectural content framework
- Reference Models
- ADM Guidelines and Techniques
- Enterprise Continuum
- Architecture capability Framework


### Architectural Development Model (ADM)
- provides a tested and repeatable process for developing EA.
![[99806f_149c913f640741efb7aaa9a59e50eeb0~mv2.webp]]
! Architecture Delivery might be from B-F. from teachers PPT

#### Phase: Preliminary
Goal: prepare the Organization for the EA project.
- Define and scope the Enterprise
- Define the architecture Principle
- Setup Architecture Repository

**Activities: 1. Develop Organizational Model for EA** 
- Scope the enterprise (with levels of impact: Core, Soft, Extended, and Community)
- Identify the participants who take part in the architecture development
- Identify the participant's responsibility
- Perform maturity analysis

**Activities: 2. Develop Architectural Principles** 
Types of principles:
- Business Principles
- Data Principles
- Application Principles
- Technology Principles

e.g.
BP - comply with all relevant laws
DP - data is protected from unauthorized use
AP - ease of use
TP - able to support changes

*Principle Template* 

| **Field**         | **Details**                                                                                                                                                                                                    |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**          | Compliance with Law                                                                                                                                                                                            |
| **Statement**     | Enterprise information management processes comply with all relevant laws, policies, and regulations.                                                                                                          |
| **Rationale**     | Enterprise policy is to abide by laws, policies, and regulations. This does not preclude process improvements that may lead to policy changes.                                                                 |
| **Implications**  | - Must comply with laws and regulations on data collection, retention, and management. <br> - Staff need education and access to rules. <br> - Legal changes may require updates to processes or applications. |
| **Mandatory**     | Mandatory                                                                                                                                                                                                      |
| **Review Reason** | N/A                                                                                                                                                                                                            |
| **Review Date**   | 08/08/2016                                                                                                                                                                                                     |
![[Pasted image 20251226112905.png]]


**Activities: 3. Develop Business Principles, Goals, Drivers** 
- Define Business Goals
- Define Business Drivers

| **Reference ID** | **Title**    | **Business Goal**                                                                              |
| ---------------- | ------------ | ---------------------------------------------------------------------------------------------- |
| R-01             | ArchiSurance | - Become top ten insurance institute in Europe  <br>- Enhance the popularity of the brand name |

| **Reference ID** | **Title**    | **Business Strategy Statement**                                                                                                                                                                                |
| ---------------- | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R-01             | ArchiSurance | - Unify the three existing platforms into a one-stop-shop service-oriented insurance platform  <br> - Eliminate duplication of IT applications and better utilize IT support aligned with business initiatives |

| **Reference ID** | **Title**    | **Business Driver**                                                   |
| ---------------- | ------------ | --------------------------------------------------------------------- |
| R-01             | ArchiSurance | - increase profit<br>- reduce cost<br>- enhance customer satisfaction |

**Activities: 4. Develop Architecture Repository** 
An architecture repository is a structured storage system used to manage all the assets, models, standards, and documentation related to enterprise architecture. It acts as a central hub for organizing and maintaining architectural information throughout its lifecycle.
1. **Architecture Metamodel**  
	 - Architecture Method
	 - Content Metamodel
2. **Architecture Landscape**  
	- Strategic Architectures
	- Segment Architectures
	- Capability Architectures
3. **Reference Library**  
	- Foundation Architectures
	- Common Systems Architectures
	- Industry Architectures
	- Organization-Specific Architectures
4. **Standards Information Base**  
	- Business Standards
	- Application Standards
	- Data Standards
	- Technology Standards
5. **Governance Log**  
	- Decision Log  
	- Calendar  
	- Compliance Assessments  
	- Project Portfolio  
	- Capability Assessments  
	- Performance Measurement  
6. **Architecture Capability**  
	- Skills Repository  
	- Organization Structure  
	- Architecture Charter


###### Phase: Preliminary - Results
Both the sponsoring organization and architecture development team are prepared for architecture development

Production of deliverables:
- Organization Model for EA
- Business Principle, Goal, Drivers
- Architecture Repository 
- Request for Architecture Work


#### Phase A: Architecture Vision
Goal: Set and confirm the expectations for an enterprise architecture project
- Develop architecture vision
- Define stakeholders
- Create communication plan
- Perform capability assessment
- Create the statement of architecture work and object approval from sponsors

**Activity 1 - Develop Architecture vision** 
- Identify the stakeholders in the architecture development. CIO, E. architect, B.Arch., Sys. Arch. , Tech. Arch., Domain Representatives.
- State their concerns. E.g. 

| Stakeholder | Key concerns                           | Class         | Deliverables  |
| ----------- | -------------------------------------- | ------------- | ------------- |
| CIO         | high level business drivers and goals, | Keep informed | A. principles |
| E. Arch.    | ..                                     |               |               |
- List and describe issues/ scenarios to be addressed.
- Discover the drivers of changes by deriving them from stakeholders. (Page 37. pics)

	![[ArchiMate-Solution-Concept-Diagram-1.png]]


**Activity 2 - Develop Communication Plan** 
- Identify stakeholders, grouped by communication requirement - PM, P. lead, P. team, Stakeholders, P. sponsors.
- Describe each type of the communication type

| Type of comm.   | Purpose                           | Presenter         | Audience | Time/Frequency     | Documentation   |
| --------------- | --------------------------------- | ----------------- | -------- | ------------------ | --------------- |
| Kickoff Meeting | intro to P. team and P. review... | - PM<br>- T. Lead | P. Team  | start of iteration | Meeting minutes |
| ...             |                                   |                   |          |                    |                 |

- Identify the responsibilities of stakeholders (R-responsible, A-accountable, C-consulted, I-informed)

**Activity 3 - Confirm Business Principles, Goals and Drivers** 
- BP, G and D all defined in the preliminary phase.

**Activity 4 - Develop Capability Assessment** 
Business capabilities, IT capabilities ..
For each capability, evaluate business risk, IT & infrastructure risk, migration risk, maturity, and mitigation activities.

**Activity 5 - Develop Statement of Architecture Work** 
Statement of Architecture work - Content:
*Architecture project request and background* → Explains why the architecture project is needed and its context. 
*Architecture project description and scope* → Defines what the project will cover and its boundaries. 
*Stakeholders and their concern* → Identifies stakeholders and documents their interests and issues. 
*Communication plan* → Outlines how and when stakeholders will be informed.  
*Acceptance criteria and procedures* → Specifies how success and deliverables will be validated.  
*Project plan and schedule* → Provides timeline, milestones, and resource allocation.  
*Approvals* → Formal sign‑off authorizing the project to proceed.  

###### Phase: Architecture Vision - Results
- Formal approval of the Statement of Architecture Work  
- Sponsor’s sign-off to proceed  
Deliverables:
- Architecture Vision  
- Communication Plan  
- Updated and confirmed Business Principles, Goals, and Drivers 
- Capability Assessment  
- Statement of Architecture Work  


#### Phase B, C D:
**Goals (B - Business Architecture)** 
- Develop Baseline business architecture
- Develop Target Business architecture

**Goals (C – Information System Architectures)** 
- Develop baseline data architecture
- Develop target data architecture
- Develop baseline application architecture
- Develop target application architecture

**Goals (D – Technology architecture)** 
- Development of technology
- Baseline technology architecture
- Target technology architecture
- Perform gap analysis
- Rationale and justification for architectural approach
- Produce architecture definition
- Produce architecture requirement specification


**Activities of Phase B, C, and D**
- Develop architecture definition
- Develop Architecture Requirements Specification

KPI - key performance indicator

| KPI                     | measurement of compliance |
| ----------------------- | ------------------------- |
| profit in 6 months      | >1.5 mil                  |
| expenditure of hardware | <1.3 mil                  |
| customer complaints     | > 30 new cases per week   |


#### Phase E: Opportunities and Solutions
**Goals**
Identify the delivery vehicles to effectively deliver the target Architecture.
- Work Package - "what are the changes required to realize the target Arch.?"
- Transition Architecture (if required) - "Will there be any intermediate states throughout?"
- Implementation and Migration plan - "What is the schedule of the delivery of changes?"

**Activities** 
- Develop Architecture Roadmap
	- Implementation factor assessment
	- Consolidated gaps, solution and dependency matrix
- Develop Implementation and Migration Plan

###### Result
- Produced a detailed architecture roadmap and migration plan
- Deliverables
- Architecture Roadmap
- Implementation and Migration Plan
- Architecture Requirements Specification (updated)



EA is the organizing logic for business processes and IT infrastructure reflecting the integration and standardization requirements of the company's operations.

Domains of EA - business, information, application and technology

Levels of Arch. -> high(strategic), mid(tactical), low(solution)

EA focus areas - SOA, identity and access management, application, security, data

EA puts emphasis on -> Reuse, interoperability, and service orientation

SOA components -> registry, service broker, workflow engine, supervisor

SOA design principles -> standardized service contract, s. loose coupling, s. abstraction, s. reusability, s. autonomy, s. statelessness, s. discoverability, s. composability.

SOA benefits - agility, speed, efficiency, services, revenue, accountability, less costs, less risks

SOA downsides -> extra overload (e.g. all inputs must be validated), high cost, high bandwidth


SPL: Benefits - Reduced Cost, Flexible Staffing and Productivity, Increased Predictability, Higher Quality, fast delivary


Drivers of success - business drivers, people and Technology.

XP tenet - "find elements of creating good software and do the all the time"
XP principles - feedback, communication, simplicity, courage
XP roles - customers, developers, coaches/managers

CMM - expensive, extensive documentation, bureaucratically complex, high overhead until level 5 (optimization)

Zachman F. - doc. heavy, can lead to a methodology biased approach. process heavy, not well accepted, seems to promotes just top-down approach.  biased to data community

Model driven arch - separates the specification of system functionality from specification of its implementation on a specific tech. platform.

MDA shortcomings - generating platform specific models from platform-independent models will only really work in niche technical environments, b/c tech. changes fast., is complicated(needs modeling knowledge). bias towards object and component based technologies b/c we use UML.

Rational unified process (RUP) phases: Inception, Elaboration, Construction, Transition, [Evolution(not included on graph)]

RUP benefits-> uses UML (accepted), scalable, provides tools, accepts changes, reduce cost, increased productivity, iterative and incremental
RUP shortcomings -> biased to support object and component-based software, can be complex, expensive purchasing tools, challenging for small size, too much result-oriented over team, too much integration over testing

Enterprise Unified Process - EUP is a software development framework that enables software to be developed through a modular and structured approach.

EUP is an extension to the previous RUP in the Rational Rose UML
application by IBM Corporation.

EUP why over RUP? it addresses the full IT lifecycle, to manage multiple concurrent projects, to operate and support in-production systems.

EUP adds 4 additions to RUP: production phase, retirement phase, operation and support discipline, enterprise management discipline. 2 phases & 2 disciplines

The major activities of enterprise management
- Program/Portfolio Management
- Enterprise Modeling
- Enterprise Architecture
- Enterprise Asset Management
- People Management
- Strategic Reuse Management
- Standards and Guidelines Management and support
- Software Process Management

The primary advantage of the EUP is that it explicitly includes enterprise-scope efforts in the project life cycle, making it clear to developers that they need to think beyond the confines of their current project and to take enterprise issues into account.