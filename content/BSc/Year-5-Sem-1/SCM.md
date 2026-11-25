---
title: Software Configuration Management
teacher: Yimer Amedie (MSc.)
---
# CH 1-L1: Introduction to SCM
As software plays a big role in critical systems, development is becoming increasingly complex.
- in-terms of size, sophistication & technology used.

Modern software must be reliable, scalable and support diverse users, languages and platforms.
- Even minor errors can have serious consequences.

**The Evolution of CM** 
- has its origins in manufacturing.
- used to manage design change and productions, when:
	- development spanned for many years
	- handled by more than one person
	- when control is transferred between people associated information gets lost.

**The core CM principles** 
1. *Configuration Identification*: what are the parts? naming and numbering
2. *Configuration Control*: how do make manage changes to the parts? formal change request, boards.
3. *Configuration Status Accounting*: what is the state of the parts? Tracking, Reporting
4. *Configuration Audits*: does the built product match the design? Functional and Physical audits

These principles are directly transferable to software.

**Timeline of the Evolution of CM in Software** 
1950s (HW CM) -> 70s (advent of CVS) -> 80s (SCM) -> 2000s (VCS gets popular) -> 2010's - present (SCM is integral to Agile and DevOps)

1. **The software crisis** (1960s -1970s)
	- software grew in size and complexity. - the shift
	- projects were chronically overbudget, late and buggy. - the problem
	- we realized - building software was like building a complex machine, so the principles of Hardware CM were applied to software.
	
2. **The birth of SCM** (1970s-80s) 
	- the term SCM emerges.
	- adapting traditional CM to the unique challenges of software.
	- Software "parts" are digital and so much easier to change, making control both harder and more critical.

**Definitions and Components** 
**SCM** - is the discipline of identifying, controlling, tracking and auditing the evolution of software artifacts through the development lifecycle to ensure integrity and traceability.

SCM doesn't just manage source code.
- it manages all software objects (configuration items - CIs) that comprises software system.
- e.g. documentation, source code, config files.

**Components of SCM** 
- Source code and Executables
	- all programming files and compiled application

- Documentation and design models
	- specification, architectural diagrams, manuals and technical guides

- Data files and test suits
	- config files, databases and comprehensive set of tests to validate functionality.

**Challenges Without SCM** 
- Code overwrites and conflicts
- Loss of earlier versions
- Difficult bug tracking
- Unclear ownership of changes
- Chaos in large teams

**The Cost of Not Having SCM** 
- Integration hell
- Lost work - accidental deletions and overwrites with no backup
- Endless debugging - no isolation.
- Team conflict - breaking each other's code.
- Business Risk - unstable software -> losing customer trust

**SCM's Solution** 
Maximizes productivity by minimizing mistakes, fostering a streamlined workflow.
- Manages complexity of modern systems.
- Protection from accidental loss
- Enables controlled evolution
- Helps meet compliance and standards

**Benefits of SCM** 
- Improved organizational competitiveness;
- Better customer service and improved customer goodwill
- Improved security; Higher software reuse.
- Low maintenance cost, better quality assurance
- project stability and control, audit trails

**Goals and Objectives of SCM** 
 - Version control
- Change control
- Configuration identification
- Auditing
- Status accounting

**Scope of SCM in the Software Lifecycle** 
- Requirements management
- Source code control
- Documentation control
- Build and release management
- Maintenance and support

**The SCM Process Overview** 
The SCM Process is implemented through interconnected activities.
Two of the most fundamental are:
- *Version Control*: The foundation. The practice of tracking and managing changes to Software Objects over time.
	- The "What" and "When".

- *Change Control*: The governance layer. The formal process for requesting, reviewing, approving, and implementing changes to Software Objects.
	- The "Why" and "Who approved it".

 *SCM Process*: Identification -> Control -> Status Accounting <--> Audits and Reviews

- Identification - artifacts we want to control
- Control - ensure that any change request is analyzed, approved and implemented correctly.
- status accounting - records what has changed
- Audits and Reviews - Verify compliance

**Key roles in CSM** 
- *Product Manager* - oversees progress, monitors status and ensures deadlines are met.
- *Configuration manager* - enforces SCM policies, manages change requests and meticulously control code versions.
- *Developers/Software Engineers* - collaborate efficiently, merge changes and diligently maintain documentation.
- *User/Customers* - formally request changes and report bugs/issues through channels.

# CH 1-L2: Core SCM Process Activities
SCM is the set of activities that are performed throughout the project life cycle. from requirement analysis to maintenance.
SCM is important because software is subject to constant change.
Uncontrolled or unmanaged change can create
- confusion
- communication breakdowns
- shared data problems
- simultaneous update problems
- multiple maintenance problems

SCM helps to ensure that
- SW components are properly controlled tracked and stored
- Changes are properly coordinated
- The system is always in a known and stable state

### Core Concepts in SCM
The SCM process is a structured set of activities designed to manage and control the evolution of software systems.
- these activities are interconnected and form the backbone of any robust SE practice.

**Configuration Item** 
A configuration item is any identifiable component of a software project that needs to be managed and controlled.
Each configuration item is treated as a distinct entity with its own version history.

e.g. Source code files, Design documents, User manuals, Test cases, Build scripts

A functional baseline is established for each CI which can breakdown to allocated baselines for subsystems.

#### Baselines
- are the foundation of control.

A baseline is a milestone that marks a known, good, and stable state of the project.
They are
- *Formally Approved* - agreed upon
- *Frozen State* - placed under formal change control, not to be modified arbitrarily.
- *Reference Point*: serves as a stable foundation for all future development.

**Importance** 
- *Stability* - it provides a solid foundation for developers.
- *Reproducibility* - Allows rebuilding past versions for testing.
- *Change Management* - shows the impact of changes clearly
- *Progress measurement* - Defines major project milestones.

**Types of Baselines** 
1. *Functional Baselines*: approved system requirements (what it does).
2. *Allocated/ Design Baselines*: Approved system architecture (how it is done).
3. *Product Baselines*: final released software documentation + product.
4. Others: Development baseline, Alpha/Beta, Release baselines

**The Process** 
1. *Identify and Select* - the correct version of all components
2. *Build and Test* - the integrated suit to ensure it works.
3. *Formal Review* - by the team and the Change Control Board (CCB)
4. *Approve and Tag* - using the version control system
5. *Communicate* - the new baseline for the entire team

**Example** 
Imagine a team is building a new Learning Management System with multiple key modules: ...
- **Baseline = frozen reference point**: After all modules pass unit/integration testing, the stable build is formally tagged (e.g., `git tag v1.0-baseline`) to become the official V1.0 product baseline.
- **Post-baseline changes are new features**: A change request like "Add Due Date Reminder" wasn't part of V1.0, so it must be handled without altering the frozen baseline.
- **Branch from the baseline**: Create a new branch off the tagged baseline (`git checkout -b hotfix/add-reminders`), develop and test the feature in isolation.
- **Merge back via formal review**: Integrate the change back into the main line only after rigorous testing and review, preserving the baseline's stability.

**Baselines Summary** 
- A baseline is a formally approved, frozen snapshot.
- It provides stability, reproducibility and control.
- It is created at key milestones (functional, design, product)
- The process: Selecting -> Testing -> Approval -> and Tagging
- It is enabled by version control tools like `git` 
- "without baselines, we just have 'history', but with them we have a managed project."

#### Change Control
The formal process for managing changes to the software's components.
It's purpose is to prevent chaos and ensure that every change is justified, reviewed and documented.

`Request -> Reject / Approve -> Implement -> Verify -> Integrate` 

#### Versioning
Refers to the systematic process of assigning unique identifiers to different states or revisions of software artifacts to track changes overtime.
It ensure that developers can:
- manage multiple iterations of a software item
- compare changes over versions
- retrieve previous versions
- coordinate work among team members

**Key points** 
1. *Unique ID* - each version has a distinct identifier
2. *Change Tracking* - Monitor document modifications
3. *Parallel Development* - Enables simultaneous work on features.
4. *Rollback Capability* - Revert to previous versions if needed.

#### Variants
Are versions of a software that are developed in parallel.
Why? They allow us to work on multiple lines of development without interfering with each other.

**Common Types** 
1. Main/Master
2. Feature Branch
3. Release Branches
4. Hotfix Branches

The power of variants comes from the ability to *merge* changes from one branch to another.

#### Core SCM Process Activities
**The Core Four and Their Enablers** 
*Configuration Planning* - not part of the 4 core
- The Input, foundation 
- Defines the rules for how you will perform each of the core activities. 
- It answers: 
	- What tools will we use for Identification? 
	- What is the process for Control?

*The 4 core activities* 
- ***Configuration Identification***: What to control?
- ***Configuration Control***: How to change it?
- ***Configuration Status Accounting***: How to track it?
- ***Configuration Auditing***: Is it Correct?

*The Enablers* 
- ***Version Control*** - the toolbox that enables the cycle.
	- helps us manage d/t versions of Code, Docs, configs
- ***Build and Release Management*** - the output. and managing its delivery to software users.
- ***Configuration Planning*** 

#### The SCM Framework: A unified View
![[Pasted image 20261030141628.png]]

**Summary** 
- *Configuration Item* (CI): Any important artifact
- *Baseline*: A frozen *snapshot* of CIs at a point in time;
- *Version*: An *iteration* in time.
- *Variant*: A parallel fork for a different purpose.
- CSM core activities: C. Identification, Control, Status accounting and Auditing
- CSM enablers: Config. planning, Release management, and VCS

# CH 1-L3: Audit and Status Reporting
In SCM, *maintaining control* over the project's assets and *providing clear communication* about their status are two critical, complementary functions.
- *Configuration Audit* - The mechanism for control and verification. 
- *Status Reporting* - The mechanism for communication and visibility.

**Key Concepts** 
- *Configuration Audit* - verifies conformity.
- *Status Reporting* - communicates the current state of the project.
- *Configuration Status Accounting* - Records CI (configuration item) data.
- *Reviews and Tasks* - Support daily practices.

#### Configuration Audit
- Formal review of configuration Items (CIs).
- Ensures conformance to requirements and standards.
- Provides objective evidence of integrity.

**Audit Focus** 
- ***Completeness***: are all required items present?
- ***Correctness***: Does the item match requirements?
- ***Consistency***: Are items aligned with each other?

**Audit Process** 
1. *Plan* - define scope and criteria
2. *Execute* - review items and records
3. *Document findings* - record issues, gaps
4. *Report results* - communicate conclusions

**Difference from Quality Assurance (QA)** 
QA - sees the process quality -> How work is done
Audit - sees the product integrity -> What is delivered
- they complement each other

**Audit Deliverables** 
1. ***Audit Report*** - Summarize audit findings and insights
2. ***Non-Conformance list*** - Outlines issues needing corrections
3. ***Corrective Actions*** - Details tasks for issue resolution

**Types of Audits** - preview (more on chapter 10)
1. *Functional Audit* - Does it meet requirements?
2. *Physical Audit* - Does it match documentation?
3. *Baseline Audit* - Is the baseline complete and consistent?

#### Status Reporting
- Structured communication of project state.
- Provides information on CIs, changes and baselines.
- Keeps all stakeholders aligned.

**Its Purpose** 
- Ensure visibility of process
- Track bottlenecks and delays
- Support management decisions
- Provide evidence for audits

##### Key Contents of Status Reports
- **CI status** - versions, approvals, locations
- **Change request status** - open, approved, implemented
- **Baseline state** - current baseline, pending changes
- **Outstanding issues** - unresolved risks or actions.

**Status Report Format Example** 

| CI ID | Version | Status | Approver | Baseline |
| ----- | ------- | ------ | -------- | -------- |
|       |         |        |          |          |
|       |         |        |          |          |
- clear and consise
- easy to update regularly

**Benefits of Status Reporting** 
- Promotes *transparency* 
- Enables early *risk detection* 
- Improves *decision making* 
- Builds stakeholder *confidence* 

**Tools to support status reporting** 
- Automated tools - JIRA, Git, CMDB systems
- Manual tools - Spreadsheets, documents
- Dashboards for real-time visibility

**Frequency of Reporting** 
- Daily - for agile/fast projects
- Weekly - standard interval for many teams
- Milestone-based - tied to releases or phases

**Challenges in Reporting** 
- Incomplete data - missing updates or records
- Overload - too much irrelevant data
- Engagement - lack of interest from stakeholders
- Consistency - irregular reporting

#### The role of Audits and Reporting in SCM
- Provide visibility to stakeholders
- Offer assurance of compliance
- Support decision-making 
- Strengthen overall control

**Why are audits and reporting needed?** 
- Prevent chaos and rework
- Maintain accuracy of versions and baselines
- Reduce frustration and wasted time
- Avoid broken or non-compliant products

#### Configuration Status Accounting (CSA)
Audit =  CSA(Tracking) + Verification
- Process of recording and reporting configuration data
- Tracks the history and current state of CIs
- Supports decision-making and control

**Role of CSA in SCM** 
- Provides traceability across versions and changes
- Ensures visibility of baseline states
- *Supplies evidence* for audits and reviews

*CSA vs. Status Reporting* 
CSA - Systematic record keeping
Status reporting - communication of current state

CSA feeds into status reports.

**CSA Outputs** 
- Version histories of CIs
- Change logs with approvals
- Baseline records
- Reports for audits and reviews

#### Reviews in SCM
- Peer or management evaluations of work products
- Focus on quality and correctness
- Less formal than audits

**Objectives** 
- Detect errors early
- Ensure compliance with standards
- Promote team learning and alignments
- Reduce rework costs

**Participants** 
- Author - presenter
- Reviewers - peers/ experts providing feedback
- Moderator/ Facilitator - guides the process
- Recorder - captures issues and decisions

**Deliverables** 
- *Review report* - summary of findings
- *Defect/ Action list* - Issues to resolve
- *Approval/ Rejection decision* of the work product being reviewed

#### Tasks in SCM
- Specific activities to manage configuration items.
- Tracking, Updating and Reporting
- Support audits, reviews and reporting

e.g. 
- Update CI version and status 
- Record change request approvals 
- Prepare status reports 
- Document review findings

**Task assignment and Ownership** 
- Assign tasks to specific team members
- Clarify responsibilities and deadlines
- Track completion and follow-up

**Tools for Task Management** 
- *Automated tools* - JIRA, Trello, MS Planner 
- *Manual tools* - Spreadsheets, task boards 

Ensure visibility and accountability.

**Importance** 
- Supports audit and reporting processes
- Ensure consistency and accuracy
- Reduces errors and rework
- Improves team efficiency

**==🔴Summary==** 
- Audits provide assurance of integrity
- Status reports provide visibility
- CSA maintains records and history
- Reviews and tasks support quality and control

# CH 1-L 4&5: Organizational Context Planning and SCM Plan and Tools
Like other management, CM needs people to perform the various activities and produce results.
Activities like:
- Configuration Identification
- Change management, disposition and implementation
- Configuration Control
- Status Accounting, CA etc.

### Organizational Context
"Context" includes - *culture*, *structure*, and *leadership*.
- it defines how decisions are made
- it affects resource allocation and priorities.
- it shapes SCM effectiveness and adoption.

**Cultural Influences on SCM** 
- Organizational culture (Shared values and beliefs)
	- Determines acceptance of rules and procedures
	- Impacts willingness to adopt SCM tools
	- Strong quality culture -> Strong SCM practices

**Organizational Structure and SCM** 
- Structure defines reporting lines and authority.
- Centralized Vs Decentralized decision-making
	- Strong hierarchy -> Centralized 
		- Stricter SCM enforcement

	- Flexible structure -> Decentralized 
		- Quicker but riskier

**Leadership and SCM Commitment** 
- Managers allocate resources for SCM
- Strong leadership - Compliance and adoption
- Weak leadership - Neglect of SCM activities

#### SCM Constraints
-  Constraints - Limits on SCM effectiveness
 - Can be internal or external to the organization
 - Often unavoidable & must be managed
 - Define what is realistic in SCM planning

**Constraints can be**: 
- **Technical:** legacy systems, tool incompatibility, integration challenges, high tool costs, security limitations.
- **Organizational/Process:** rigid standards, bureaucracy, resistance to change, inconsistent adoption, approval delays.
- **Resource:** limited budget, skilled personnel shortage, competing priorities, insufficient documentation time, staff overload.
- **External:** government regulations, customer contract requirements, compliance needs, market deadlines, legal/certification restrictions.

**Summary:** Constraints can't be eliminated, they guide realistic SCM design. Balance control, cost, and speed; adapt processes to context. so, our goal should be to optimize, not perfect.

### SCM Plan
- defines scope and objectives.
- Helps us align with organizational goals.
- Guides resource allocation
- provides structure for consistent practices

**High-Level SCM Planning** - big-picture direction for SCM.
- **Purpose:** common standards across teams, cross-department communication, risk anticipation, foundation for detailed planning
- **Elements:** scope, stakeholders/roles, milestones/phases, initial resources, SCM goals tied to project goals

**Strategic Alignment** - SCM must serve business objectives:
- Agile firms -> lightweight SCM; 
- regulated industries -> formal SCM
- Matching strategy to organization improves acceptance and success

**SCM Governance** - the oversight framework that defines accountability, enforces compliance, and authorizes decisions.
- **Structures:** defined roles (managers, auditors, engineers), CCB, review/approval processes, escalation paths, project management integration
- **CCB (Configuration Control Board):**
	- reviews proposed baseline changes 
	- approves/ rejects/ defers; 
	- checks goal/policy alignment; 
	- balances technical, cost, and schedule factors; 
	- keeps formal decision records

- **Principles of SCM Governance:** 
	- **Transparency**: ensures visibility of all SCM activities so stakeholders can see what's happening
	- **Continuous Improvement**: adapts and evolves over time as processes change
	- **Accountability**: clearly defines roles and responsibilities so everyone knows who owns what
	- **Consistency**: maintains uniform application of rules across projects and teams
	- **Compliance**: adheres to internal policies and external standards/regulations

**Benefits of strong governance:** consistency, stakeholder trust, compliance, fewer errors/conflicts, long-term discipline.

**Challenges:** bureaucracy and approval delays, staff resistance, balancing flexibility vs. control, need for ongoing leadership support.

### SCM Compliance
"Compliance" - following established rules (laws, standards, internal policies) to ensure reliability and accountability, protect against legal/contractual risks, and support certification and audits.

**Types of compliance:** 
- **Contractual** - fulfilling customer agreements
- **Regulatory** - adhering to legal and industry rules
- **Internal** - following company policies and processes
- **Standards** - alignment with ISO, IEEE, CMMI, etc.
- **Ethical Compliance** - Upholding responsibility and transparency

**Compliance and Audits:**
- Audits (internal or external) verify SCM rules are followed
- Focus on processes, records, and traceability
- Findings may lead to improvements or penalties
- Audits prove compliance to stakeholders

**Benefits:** product quality and safety, customer/regulator trust, reduced legal and financial risks, better reputation, continuous process improvement.

**Challenges:** complex/changing regulations, high compliance costs, staff resistance to extra procedures, risk of becoming a formality, balancing compliance with agility.

**Ensuring effective compliance:** clear policies and training, automated tracking tools, regular internal audits and reviews, leadership commitment, and a culture of responsibility and integrity.

### SCM Plan and Tools
**SCM Plan (SCMP)** - the project's rulebook: formal documentation of the SCM system that clarifies roles/processes, aligns the core team, subcontractors, and stakeholders, and serves as the single source of truth for all SCM activities.

**Purpose:** 
- Defines approach and procedures
- Sets responsibilities and roles
- Guides configuration control
- Ensures traceability and order
- Aligns with the development lifecycle

**Components of SCM Plan (per IEEE):** 
- **Introduction** - purpose, scope, organizational relationships, references
- **Criteria for Identification** - which Configuration Items (CIs) are covered
- **Limitations & Assumptions** - factors affecting the plan
- **CM Responsibilities & Authorities** - roles, responsibilities, authority lines
- **Project Organization** - structure and CM interfaces
- **Applicable Policies & Procedures** - standards, directives, methods
- **Planned Activities** - schedules, resources, milestones
- **CMP Maintenance** - update and review mechanisms

**Roles & Responsibilities:** the plan must define who oversees and documents configuration activities - SCM coordinator oversight, team accountability, stakeholder involvement, documentation ownership, and reporting obligations.

**Scope & Applicability:** defines where/how SCM applies - coverage, affected teams, CI categories, alignment with the lifecycle model.

**Configuration Identification:** selects and organizes items - categories, naming conventions, storage rules, ownership assignment.

**Scheduling and Milestones**: SCM Plan includes scheduling references to align configuration activities with overall project timelines.

**Change management in SCMP**: a core function within the SCM Plan.
- Controls modifications to items; Prevents unauthorized changes; Tracks requests and decisions; Requires review and approval; Improves quality and traceability

**Documentation:** specifies required records, update responsibilities, revision practices, and reference locations.

**SCMP vs. Organizational Planning:** the SCMP is project-level and operational., actionable procedures that bridge policy to execution, not strategy or governance rules.

#### Surveillance and Oversight
- ongoing monitoring of whether planned configuration activities are being followed (distinct from formal audits).
- Ensures plan compliance
- Detects deviations early
- Supports continuous improvement

**Surveillance activities:** 
- Review repositories and baselines
- Monitor change request logs
- Check adherence to workflow
- Identify recurring issues
- Report to responsible roles

> [!note]  Note for reader
> under this section, headers are just to divide items visually and not actual topic dividers. each one line under here is usually 1 page in the slides
#### Baseline Planning
**Baseline Planning** - defines how and when a product/document becomes a formally controlled reference point: Defines baseline purpose, Identifies baseline moments, documentation links, responsibility assignment.

**Resources and Interfaces** - specifies resources needed for CM: personnel, documentation, tools; interfaces with QA, PM, and stakeholders.

**Plan Review and Updates** - the SCMP isn't static; it's periodically reviewed to stay accurate and relevant: review frequency, assigned responsibility, revision tracking, alignment with the project.

**Integration with Quality Objectives** - connects SCM activities to broader organizational standards: supports traceability, reinforces documentation, links indirectly with audits, avoids procedural overlap.

**Communication and Reporting** - ensures stakeholders get information timely: communication paths, reporting roles, scheduled information flow, plan visibility.

#### Risk Considerations in SCM Planning
Identifies potential planning gaps, documentation risks, and coordination issues; plans mitigation steps.

**Alignment with Organizational Policies** - supports company standards, references regulatory needs, ensures documentation compliance, aligns responsibilities.

**Governance Structure in the Plan** - defines oversight roles, accountability lines, decision boundaries, and coordinates SCM responsibilities.

**Stakeholder Roles and Involvement** - internal (teams) and external (clients, regulators) stakeholders; defines involvement scope and communication channels.

**Maintaining Traceability in the Plan** - ensures item trace coverage, links items to baselines, supports documentation clarity, guides record structure.

**Coordination with Project Lifecycle** - aligns SCM timing with phases, supports documentation milestones, ensures baseline readiness, reflects the lifecycle model.

#### Documentation Hierarchy in the SCMP
- **SCMP** - master document governing all SCM activities
- **Policies & Standards** - organization-wide rules, compliance frameworks, references
- **Procedures & Guidelines** - step-by-step instructions for SCM functions
- **Supporting Documents** - checklists, templates, forms, training materials, tool manuals
- **Records & Reports** - baselines, change requests, audit reports, distribution lists

**Continuous Improvement of the Plan** - encourages feedback, supports iterative updates, reflects project lessons, preserves core objectives.

**Audit of the SCMP** (per Leo, 2015) - the SCMP is a controlled document and CI: controlled distribution/access, change management, auditing, all apply to it.

**Tool Support and Automation** - replaces manual tracking; ensures consistency and accuracy; supports change control workflows; enables collaboration; integrates with development processes.

**SCMP vs. SCM Tools** - complementary, not interchangeable:
- **Tool** -> automation and capability (How)
- **Plan** -> strategy, process, and governance (What, When, Who)
- Together -> mature, efficient, predictable engineering environment

**Metrics and Measurement in the Plan** - assess whether configuration activities are carried out as intended: tracking criteria, progress monitoring, improvement actions, alignment with plan goals.

# CH 2-L6: Software Config. Identification (SCI)
**Introduction** 
- It is the 1st step in SCM process.
- Identifies components to be managed and establishes unique identities for each.
- It enables baselines.

**Purpose** 
- To prevent confusion in large projects.
- Supports team collaboration 
- Facilitates impact analysis
- Provides accountability, traceability and reproducibility
- Facilitate accurate change control and reporting

**Elements of Configuration Identification** 
- Identification of Configuration Items (CIs)
- Establishment of baselines
- Naming and numbering conventions
- Version and revision control
- Documentation and traceability mechanisms

**Configuration Items (CIs)** 
The building blocks of configuration identification.
- A uniquely identifiable component of a system managed through SCM.
- Can be: Software, Document, Test data, Libraries and Tools.

- Computer Software Configuration Item - Top-level software configuration item - System
- Computer Software Components - Grouped units forming larger parts - Sub-System
- Computer Software Units - Basic software building blocks - Unit/Module

**Steps in Configuration Identification** 
1. Identify configuration items
2. Define each item’s boundaries & relationships
3. Assign unique identifiers and names
4. Record descriptive information
5. Establish baselines

**Impact of CI Selection** 
- CI selection affects control effort, documentation, and traceability
- Over- or under-selection leads to inefficiency or lack of control
- Must align with project complexity and risk

**Too Many vs. Too Few CIs** 
Too Many:
- Excessive documentation
- Redundant control
- Wasted resources

Too Few:
- Missing traceability
- Uncontrolled changes
- Audit difficulty

**Baselines and Identification** 
Identification ensures baseline clarity
- Clear identification -> unambiguous baselines -> everyone references the same controlled set of items.

**CI Selection Criteria and Checklist** 
- Technical or functional significance
- Reusability or integration dependency
- Criticality to performance or quality
- Frequency of change
- Customer or contractual requirement

**Configuration Items: Naming, Description and Documentation** 
*Naming*:
- Unique identifiers: names, numbers, or codes
- Should reflect hierarchy and version
- Follow organizational standards

*Description*:
- includes - its function, relationships, and version history
- Recorded in CI database or repository
- Supports audits and change tracking

**Acquisition and Control of CIs** 
After identifying the configuration acquisition & control follows:
- Define process for acquiring - Internally and externally developed CIs
- Validate authenticity and configuration status before inclusion
- Ensure supplier items conform to control procedures

**Principles of Configuration Items** 
Effective item identification rests on four principles:
- Unique identifiers
- Consistent naming conventions
- Version numbers
- Relationships between items

**Levels of Identification** 
Identification occurs at multiple levels of granularity.
1. **System level** - Overall solution
2. **Subsystem level** - major functional areas
3. **Component/module level** - Source code files or database schemas
4. **Document level** - Design reports, test plans, and manuals

### Software Library
**Software Library** - the central repository that stores and protects Configuration Items (CIs), supporting retrieval and versioning.

**Three types:**
- **Development library** - where work-in-progress items are created and modified freely
	- Not yet baselined.
	- May include prototypes and drafts

- **Controlled library** - where items are formally reviewed and versioned (read-only except through change control)
	- Holds baselined items
	- Used for reviews and audits

- **Master library** - the final, released, approved versions (the "official" baseline)
	- Releases and deliveries stored here 
	- Immutable once published

#### Configuration Control
The next step after CIs are identified and stored in libraries.
- Governs changes after identification
- Ensures discipline in modifications
- Prevents unauthorized changes
- Managed by Change Control Board (CCB)

**The Role of the CCB** 
- Evaluates change requests
- Balances risk, cost, and benefit
- Maintains baseline integrity
- Cross-functional representation

**Change Request (CR)** 
- Formal proposals for modification
- Submitted by stakeholders or team members
- Logged in a Change Management System
- Each CR has unique ID and status

**Role of Traceability in Identification** 
Traceability is one of the most important outcomes of effective configuration identification.
- Links requirements to design, code, tests
- Supports impact analysis
- Helps during audits
- Increases confidence in system integrity

### Benefits of Software Configuration Identification
- Reduces confusion
- Improves collaboration
- Enables control and auditing
- Supports compliance and quality

**Common Challenges in Identification** 
- Too many items tracked
- Poor naming conventions
- Inconsistent versioning
- Lack of ownership

**Best Practices for Item Identification** 
- Define clear criteria for CIs
- Establish consistent naming rules
- Automate version control
- Assign ownership to items

**Tools Supporting Identification** 
- Version control systems (Git, SVN)
- Change management tools (Jira, ServiceNow)
- Automated build and release tools
- Integrated SCM platforms

**Integration with Other SCM Activities**
- SCM Planning defines identification rules
- Status reporting tracks CI evolution
- Audits verify identification accuracy
- Tools enforce consistency

**Risks of Poor Identification** 
When configuration identification is poorly executed, the consequences can be severe.
- Lost or duplicated work
- Inability to trace changes
- Compliance failures
- Increased project costs

**==🔴Summary==** 
Software configuration identification is the foundation of SCM
- Identification is the foundation of SCM
- Libraries safeguard artifacts
- Control and CRs ensure discipline
- Implementation maintains consistency
- Supports audits and compliance

# CH 2-L7: SCI: Change Management
**Change Management** - A systematic process to handle modifications.
- Ensures orderly control over changes to baselined items. Protects product integrity.
- It involves documentation and traceability of every modification.
- Promotes communication among developers, testers, and stakeholders.

**Objectives** 
- Maintain integrity of software throughout evolution
- Maintain visibility and accountability for all changes
- Control the impact on schedule, cost and quality
- Provide traceability from request to implementation
- Support auditing and compliance with standards

**Why it is Important** 
- Changes are inevitable
- Uncontrolled changes cause instability and confusion
- Ensures alignment with business goals and priorities
- Protects the baseline from accidental modifications
- Enhances customer confidence and regulatory compliance

### The Change Management Process

```
[Change Request] → [Evaluation/ Impact Analysis] → [CCB Review] → 
     [Approve / Reject / Defer]
		               │
   ┌───────────────┴─────────────────┐
   ▼                                 ▼                                  
 [Rejected/Deferred]              [Approved] 
   │                                  │           
   ▼                                  ▼
[Notify Requester]            [Implement Change]                    
                                      │
                                      ▼
                             [Update Baseline & Docs]
                                      │
                                      ▼
                           [Verify & Close Request]
```

**Steps:** 
1. **Change Request** - A formal proposal to modify a configuration item. (what to change and why)
	- Contains priority, risk, and expected benefits.
	- Info Included: unique ID, description of the change & rational, impacted items, Estimated effort, resource or cost, and Priority level & risk category
	- Sources: 
		- improvements or bugs from DEVs, 
		- testers for a failed TC or quality issues, 
		- customers proposing enhancements
		- Managers for Compliance or cost reasons
		- Automated tools for detected anomalies

	- Categories: 
		- Corrective (fix bugs/defects)
		- Adaptive (respond to environment/requirements changes)
		- Perfective (improve performance/usability)
		- Preventive (reduce future risk/maintenance) 
		- Emergency (urgent changes requiring immediate attention)

	- CR Lifecycle:
		- Initiation -> Recording/logging -> Evaluation-> Approval/ R(by CCB) -> Implementation & Closure 

2. **Evaluation/ Impact Analysis** - assess effects on cost, schedule, quality, and other CIs
	- Purpose: Evaluates whether a change is necessary and feasible, assessing technical feasibility, resource availability, cost/schedule/risk impact, dependencies, and affected components.
	- Activities: analyzing affected modules, estimating effort, assessing/mitigating risk, checking consistency with requirements, and preparing reports for CCB review.
	- ***Impact Analysis***: systematic approach to understand the consequences of proposed modifications. 
		- Examines dependencies and interfaces between modules.
		- Evaluates potential side effects on performance and behavior.
		- Helps estimate testing scope and cost.
		- Ensures traceability from requirements to implementation.

3. **CCB Review** - Configuration Control Board evaluates the request
	- **Criteria for Change Approval** 
		- Alignment with project goals and requirements
		- Feasibility and technical soundness of the proposed change
		- Risk evaluation and mitigation adequacy.
		- Impact on schedule and cost.
		- Availability of resources and tools.
		
	- **The Approval Process** 
		- Present the change request and evaluation findings to the CCB
		- Discuss and clarify technical details
		- Reach a decision by voting or consensus
		- Formally document the decision and rationale
		- Notify relevant teams of next steps

4. **Decision** - approve, reject, or defer (with rationale recorded)
5. **Implementation** - if approved, make the change (only through controlled process)
	- Begins after formal approval
	- Involves planning, coding, and testing of the change.
	- Ends with integration and baseline update.
	- **Planning:** review approved docs, identify affected CIs, develop implementation plan, assign personnel, define rollback procedures
	- **Execution:** apply changes to baseline, update docs, build/integrate, test/verify, communicate status
	- **Post-Implementation Review (PIR):** verify goals met, assess side effects, confirm record updates, get final approval, document lessons learned

	- Key Principles:
		- Maintain traceability from CR to code changes
		- Apply controlled check-in(requesting for editing)/check-out(returning) procedures.
		- Perform peer reviews before committing changes.
		- Execute unit and integration testing after modification. 
		- Document lessons learned and outcomes.
	
6. **Baseline Update** - update the baseline and documentation to reflect the change
7. **Verification & Closure** - confirm the change works; close the request.
	- Conduct verification testing against change objectives.
	- Perform regression testing to detect side effects.
	- Update test documentation and results.
	- Ensure traceability to original requirements.
	- Obtain formal acceptance before baseline update.

**Deviations in Configuration Management** 
Are:
- ***temporary*** departures from baseline requirements
- typically, pre-approved under specific conditions
- used when strict compliance isn't possible/ is impractical.

**Waivers in Configuration Management** 
Are:
- ***permanent*** authorization for non-conformance. / for deviations.
- issued when requirement can not be met.
- becomes part of the configuration baseline.

**Change Tracking and Traceability** 
- record all approved and implemented changes, maintaining links between requests, approvals and code.
- use VC tools for documentation. 
- They enable audit trails for accountability.
- Support rollback and recovery.

**Configuration Auditing after Implementation** 
- Conducted to ensure full compliance with CM policies.

Purpose
- verify implementation aligns with approved request
- Ensure documentation and baselines are updated
- confirm testing and verification results.
- check for unauthorized changes
- conduct both functional and physical audits.

**Tools Supporting Change Management** 
- VCSs (Git, SVN, CVS)
- Issue tracking tools (JIRA)
- configuration databases (CMDB)
- automated build and deployment systems
- document management repositories

**Role of the Configuration Control Board (CCB)** 
Responsible for managing and approving changes.
- evaluates technical, cost and schedule impacts
- ensures consistency with project objectives
- authorizes deviations and waivers

**Communication in Change Management** 
- keep all stakeholders informed using standardized change reports.
- schedule periodic review meetings.
- update affected documentation and manuals

**Handling Emergency Changes** 
Immediate action is needed. These:
- arise from critical failures or security issues
- require fast evaluation and approval
- follow expedited implementation procedures
- must still be documented post-implementation
- reviewed Retrospectively by the CCB.

**Change Documentation and Reporting** 
- Maintain formal change logs and reports.
- Record request details, evaluations, and approvals. 
- Track implementation progress and results.
- Include deviations and waivers in reports.

**Integrating Change Management with Configuration Identification** 
- Links changes to specific configuration items.
- Updates item identifiers and baselines.
- Ensures consistency across repositories.
- Prevents orphaned or redundant changes.
- Promotes traceability throughout lifecycle.

**Integration with Configuration Control** 
Configuration control
- Enforces formal approval processes.
- Ensures changes meet quality and compliance standards.
- Ensures changes align with baseline control mechanisms.
- Coordinates between technical and managerial teams.
- Reduces risks of unauthorized modifications.

**Relationship Between Change Management and Configuration Status Accounting** 
Configuration status accounting (CSA)
 - Records current state of all configuration items.
- Reflects implemented and pending changes.
- Supports reporting and audit readiness.
- Provides visibility for stakeholders.
- Facilitates decision-making and resource planning.

**Auditing Deviations and Waivers** 
- Verify justification and approval documentation.
- Confirm validity and expiration of deviations.
- Ensure waivers are correctly recorded in baselines.
- Review impact on overall system integrity.
- Report audit findings and recommendations.

**Best Practices in Change Management** 
- Standardize change request procedures.
- Automate workflows using tools.
- Maintain traceability and version control.
- Ensure stakeholder engagement.
- Conduct periodic reviews and audits.

**Challenges in Change Management** 
- Resistance to process discipline.
- Poor documentation or tracking.
- Unclear communication channels.
- Lack of tool integration.
- Time and resource constraints.

**==🔴Summary==**
- Change management ensures controlled evolution.
- Includes evaluation, approval, and implementation.
- Deviations and waivers provide flexibility.
- Integration with other SCM elements is essential.
- Promotes quality, consistency, and accountability


