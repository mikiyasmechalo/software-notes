---
title: Quality Assurance & Testing
teacher: Ms. Aster Alemu
---
# CH 1: Foundational Concepts
**What Is Quality?** 
Quality is the degree to which a product fulfills the real needs of its actual user.
Quality that lives only in the specification and not in the user's experience is not really quality at all. It is *compliance*.

Standards and processes exist to HELP achieve quality, they are instruments.

The Quality Triangle, All Three Must Be Satisfied
1. FUNCTIONAL QUALITY: Does it do what the specification says?
2. STRUCTURAL QUALITY: Is the code maintainable, secure, and performant?
3. USER QUALITY: Does it solve the user's real problem effectively?


### Types of Bugs
**Functional Bugs** - the software does not do what it was specified to do.
- Discovered by comparing actual behavior against the requirements or acceptance criteria.
- The primary target of Black-box testing.

**Logic/ Algorithmic Bugs** - when the code runs without crashing but produces incorrect results due to a flawed algorithm, a wrong condition, or an incorrect formula. 
- Sources: off-by-one errors in loops, incorrect operator precedence, wrong comparison (< vs <=), and incorrect formula implementation.

**Performance bugs** - occur when the software does the right thing, but too slowly, or under conditions that expose unacceptable response times. 
- These bugs are invisible during unit testing with a single user and only emerge under load.
- Performance testing is a distinct discipline.

**Security Bugs** - allow unauthorized access, data exposure, or malicious manipulation. 
- Often arise from insufficient input validation (SQL injection, XSS), broken authentication, inadequate authorization checks (IDOR - accessing other users' data), and insecure data storage. 
- These bugs are specifically targeted by security testing (SAST, DAST, penetration testing).

**Compatibility Bugs** - hen the software works correctly in one environment but fails in another.
- D/t OS, browser, device, screen res.
- not failures in the core logic; failures in the assumption that all environments are equivalent.

**Usability Bugs** - defects in user experience rather than in functionality.
- The software does what it was specified to do - but the specification was wrong about what users actually needs.
- Confusing navigation, unclear error messages, non-intuitive workflows, inaccessible form fields, and inconsistent terminology are all usability bugs. 
- These are found by exploratory testing, user observation, and UAT, not by automated functional tests, which cannot measure confusion.

**Regression Bugs** - a previously working feature that stops working after a code change.
- The most common bugs in actively developed software.
- Automated regression testing exists.

**Integration Bugs** - occur at the interfaces between components, where one module passes data to another, calls an API, writes to a database, or sends a message.
- Each component may work perfectly in isolation.
- mismatched data formats, incorrect assumptions about response structures, timing issues, or version incompatibilities. 

### QA vs. QC
**Quality Assurance** is *proactive*. It asks: are we using the right processes, practices, and standards to prevent defects from being introduced in the first place?
**Quality Control** is *reactive*. It asks: does this artifact, this build, this output actually meet the required standard?
*e.g.* For a camera: QA is designing the production line so consistently good lenses are made. QC is testing each lens before it ships.

| Quality Assurance (QA)                                       | Quality Control (QC)                                    |
| ------------------------------------------------------------ | ------------------------------------------------------- |
| Proactive - prevents defects from being created.             | Reactive - finds defects that already exist.            |
| *Process-focused*: are we using the right practices?         | *Product-focused*: does this output meet requirements?  |
| Spans the entire development life-cycle.                     | Happens at checkpoints and the test phase.              |
| *e.g.* code review processes, CI/CD pipeline, test planning. | *e.g.* executing test cases, rejecting a failing build. |

#####  What Builds High-Quality Software? Four Factors That Multiply Each Other
>"One good test is a foundation, not a ceiling."

1. **Quality of test design - not just quantity** - ten well-designed test cases covering critical paths are more worth than 100 tests that all verify the happy path.
2. **Coverage of distinct scenarios** - systematically identify functional cases, negative cases, boundary values, edge cases, security scenarios, performance scenarios, and compatibility variations. Each category probes a different class of potential failure. 
3. **Testing against the actual requirement** - Tests must be derived from what the user actually needs, not just from what the developer implemented. 
4. **Testing at the right phase** - Quality is far cheaper to build at the analysis and design phases than to fix at the testing or production phase. Requirement review is important.

### The Seven Testing Principles
With this foundation established, the seven classical principles of software testing take on deeper meaning.
They are not arbitrary rules - each one encodes a hard-won lesson from decades of software failures.
1. *Complete testing is impossible* - Infinite input combinations exist for any non-trivial software. This is why testers prioritize by risk, not by completeness.
2. *Testing reveals defects, not their absence* - Passing all tests means the software survived the conditions those tests covered. Zero detected bugs ≠ zero bugs.
3. *Defect clustering* - Historically 80% of defects are found in approximately 20% of the codebase. Complex modules, recently changed code, and integration points are high-risk areas.
4. *Pesticide paradox* - Running the same test cases repeatedly finds diminishing numbers of new bugs. Tests need to evolve, new scenarios, new data, new conditions.
5. *Context dependency* - a banking application requires security-intensive, compliance-aware testing. A mobile game - performance and UX testing. strategy must match the context.
6. *Absence-of-errors fallacy* - A product with zero detected defects does not meet user needs has failed. 
7. *Early testing saves cost* - Defects found at requirements phase cost ×1 to fix. The same defects found in production cost ×100+. 

# Introduction to Software Testing
### SDLC Models and Testing
**Waterfall** 
- *Sequential*: Requirements → Design → Implementation → Testing → Deployment.
- *Testing*: After all development is complete - late defect discovery is expensive.
- *Best for*: Stable requirements; regulatory documentation-heavy environments.

**V-Model** 
- *Verification*: 'Are we building the product right?' - each phase checked against its requirements.
- *Validation*: 'Are we building the right product?' - final product checked against user needs.
- *Key advantage*: Test planning starts in parallel with development, not after it.

**Agile** 
- Agile is a philosophy and mindset, not a concrete process.
- The Agile manifesto does not prescribe how to work - it defines values and principles that good work should reflect.

The Agile Manifesto - Four Core Values
1. Individuals and interactions   OVER processes and tools.
2. Working software                   OVER comprehensive documentation.
3. Customer collaboration         OVER contract negotiation.
4. Responding to change           OVER following a plan.

The right-side items are still valued - the left-side is simply prioritized MORE.
Agile teams still write documentation; they just do not let it substitute for working software.

##### Scrum 
It organizes work into fixed-length cycles called Sprints, typically one to four weeks long.
At the end of each Sprint, the team delivers a working, tested product increment.
Scrum does not prescribe engineering practices; it focuses on team structure, work management, and the rhythm of delivery.

**Scrum roles** 3-main ones
* *Product Owner (PO)*: Represents customers and stakeholders, responsible for the Product Backlog, and accepts/rejects completed stories.
* *Scrum Master*: Facilitates Scrum events, removes obstacles, and coaches the organization on Scrum principles. does not assign work or manage people.
* *Development Team* (3-9 people): A self-organizing, cross-functional group that does the actual work, with no individual titles.

* *Software Developer / Engineer*: Designs, writes, and maintains production code, responsible for code quality and unit tests.
* *QA Engineer / Software Tester*: Designs and executes test plans, writes automated test scripts, reports defects, and verifies fixes.
* *UI/UX Designer*: Designs user interfaces and interaction flows, working one sprint ahead to ensure design decisions are ready before coding begins.
* *DevOps Engineer*: Maintains the CI/CD pipeline, manages deployment infrastructure, configures test environments, and monitors production.
* *Software Architect*: Defines the technical arc., making evolutionary design decisions sprint by sprint to ensure the system is organized and components interact effectively.

**Story Points and Sprint Planning** 
One of the most distinctive Scrum practices is the use of story points to estimate the size and complexity of user stories - rather than estimating in hours or days. 
A story point is a relative unit of measure. It does not represent a fixed amount of time; it represents complexity, effort, and uncertainty relative to other stories the team has seen before.

**Scrum Events** 
- *Sprint*: A time-box of 1-4 weeks where the team builds a potentially shippable product increment.
- *Sprint Planning*: A 8-hour meeting where the Product Owner presents high-priority backlog items and the Development Team selects and breaks them into tasks.
- *Daily Scrum*: A 15-minute daily meeting where team members coordinate and report on their progress.
- *Sprint Review*: A 4-hour meeting where the team demonstrates working software to stakeholders and the Product Owner accepts or rejects completed stories.
- *Sprint Retrospective*: A 3-hour meeting where the team reflects on their process and identifies improvements.

**Scrum artifacts** 
- *Product Backlog*: The ordered list of all work to be done on the product, owned by the Product Owner.
- *Sprint Backlog*: The set of Product Backlog items selected for the current Sprint, plus the tasks needed to deliver them, owned by the Development Team.
- *Increment*: The sum of all Product Backlog items completed during a Sprint and all previous Sprints, in a usable, tested, working state.

##### Kanban - by Toyota
Where Scrum organizes work into fixed-length Sprints, Kanban is a *continuous flow* system.
Work items move through a visual board as capacity allows - there is no iteration boundary, no Sprint planning ceremony, and no commitment to a fixed set of work per cycle. 

The central tool is the Kanban board - a visual display of all work in progress, organized into columns representing workflow stages. with cards as tasks.
A typical software board has columns such as: Backlog → Ready → In Progress → Code Review → Testing → Done. 

The most important Kanban rule is the WIP (Work In Progress) limit. 
Each column has a maximum number of items allowed at once. 

**Kanban vs. Scrum**
Choose Kanban when:
- Work arrives unpredictably (support tickets, bugs, maintenance tasks).
- Items vary enormously in size - some take hours, some take weeks.
- Fixed sprints would create artificial pressure on unrelated work.

Choose Scrum when:
- You are building a new product with evolving requirements.
- Regular Sprint Reviews provide valuable stakeholder feedback.
- Work can be decomposed into stories completable in one to four weeks.

In practice many teams blend both - using Scrum's Sprint structure with Kanban's WIP limits.
This combination is often called `Scrumban`.

Other frameworks under Agile:
1. **XP** (Extreme Programming): Emphasizes engineering practices like TDD, pair programming, and continuous integration.
2. **Crystal Clear**: A lightweight method for small, co-located teams that prioritizes people and collaboration.
3. **Lean SD** (Lean Software Development): Adapts Toyota's manufacturing principles to eliminate waste and deliver value quickly.
4. **DSDM** (Dynamic Systems Development Method): A traditional Agile framework popular in UK government and regulated industries.
5. **SAFe** (Scaled Agile Framework): Coordinates multiple Agile teams across large enterprises with program-level planning.

**Agile Work Hierarchy: Epic -> User Story -> Task** 

| Level      | Definition                                                               | Example                                                                                                          |
| ---------- | ------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------- |
| Epic       | Large feature spanning multiple sprints.                                 | Online Banking Fund Transfer System                                                                              |
| User Story | User-centered requirement. As a [role], I want [goal] so that [benefit]. | As a customer, I want to transfer money between my accounts so I can manage finances online.                     |
| Task       | Specific technical work item needed to implement the story.              | Build POST /api/transfer - Write unit tests for validation - Security test the endpoint - Write acceptance tests |

### Failure, Error, Fault, Defect

| **Term**           | **Precise Meaning**                                                                                                                        |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Error**          | A human mistake, a wrong decision made by a developer, analyst, or designer.                                                               |
| **Fault / Defect** | The code-level manifestation of an error, an imperfection in the source code, design document, or test artifact.                           |
| **Bug**            | Typically synonymous with "defect", but technically refers to a specific instance of a fault that has been triggered and caused a failure. |
| **Failure**        | An observable deviation from the expected behavior when a fault is triggered during execution.                                             |
| **Incident**       | Any unexpected behavior noticed during testing, before the root cause is identified.                                                       |

### Test Cases - The Foundation of Systematic Testing
A formal, documented set of conditions and steps designed to verify that a specific aspect of the software behaves correctly. 
They are precision instruments derived from requirements, designed to provide reproducible, evidence-based confirmation of quality.

**Stateless vs. State-Oriented Test Cases** 
Whether the test depends on the current state of the system or not.
What pre-conditions you need to set up, and what you need to verify or reset after the test runs.

*Stateless test cases*: The test produces the same result regardless of what happened before it ran.
- and the test does not change the system's state in a way that affects other tests.
- Simpler to design and maintain because they have no dependencies on execution order or prior state.

*State-oriented test cases*: The test depends on the system being in a specific state before execution, and/or it changes the system's state as a result. 
- may depend on what data is in the database, what session is active, what previous actions have occurred.
-  Require careful pre-condition setup and often post-condition cleanup.
- e.g. account locking after 5 failed login attempts.

**Expected Outcome** 
Observable, verifiable result that the tester compares against actual behavior.
It must not be vague, else the test is useless.
-  'The page should look correct' is not an expected outcome. 

Expected outcomes are not limited to a single return value. 
Depending on the nature of the feature being tested, an expected outcome may take several different forms:
- *Specific Return Value*: A clear, objective, and unambiguous outcome, such as a specific numeric value. e.g. a single number 15.00
- *State Change*: A change in the system's state, such as an account being locked or an order being confirmed. e.g. user record no longer exists in the database.
- *Sequence of Events*: A series of outputs in a specific order, such as a workflow or event-driven system. e.g. for ordering out of stock items: order->ack->status to PENDING_STOCK->confirmation->status processing->notify 
- *Set of Values*: A collection of items, where the expected outcome defines the complete set, including what must be present and what must not be present. e.g. 'Electronics' priced under $50. (E.R is a set w/c fit here.)

**What Makes a Good Test Case?** 
A good test case is complete, unambiguous, and reproducible. 
Enough context that when it fails, the developer receiving the bug report can reproduce the failure without needing to ask questions.
```
Standard Test Case Fields
Test Case ID:       Unique identifier (e.g., TC-AUTH-001)
Test Case Title:    Clear, concise description of what is being tested
Module/Feature:     Which part of the system (e.g., Authentication, Checkout)
Priority:           Critical / High / Medium / Low
Pre-conditions:     What must be true before the test can execute
Test Steps:         Numbered, precise actions the tester performs
Test Data:          Exact inputs used (email, password, file, values)
Expected Result:    Exactly what should happen - observable and specific
Actual Result:      What actually happened (filled in during execution)
Status:             Pass / Fail / Blocked / Not Executed
Defect ID:          Link to the bug report if the test fails
```

**Identifying Test Cases - How a Tester Thinks** 
Systematically identify categories of test conditions:  the expected valid inputs, the invalid inputs, the boundaries between valid and invalid, the edge cases that developers rarely think to handle, and the security scenarios that malicious users might attempt.

**Bug Report - Professional Standard** 
When a test case fails, the tester creates a bug report.
A professional bug report gives the developer everything they need to reproduce the failure, understand its impact, and fix it without needing to ask the tester follow-up questions.

e.g.
```
Bug ID: BUG-AUTH-031
Title: No lockout message shown after 5 failed login attempts
Reporter: Marta T. (QA Engineer)
Date: 2025-10-14
Severity: High
Priority: Critical
Status: Open
Linked Test: TC-AUTH-004
Environment: Browser: Chrome 119, OS: Windows 11, URL: staging.example.com
Steps to reproduce: ...
Expected Result: ...
Actual result: ...
Impact: ...
Attachments: screen_recording_lockout_bug.mp4, console_log_5th_attempt.txt
```

**Cost of Bugs - The Duality of Defect Costs in SDLC** 
1. *Exponential Cost of Repair (Late Detection)*:
	* Requirements Phase: $1
	* Coding Phase: $10
	* Production: $100+ (emergency patches, user impact, reputational damage)
2. *Structural Disaster (Early Flaws)*:
	* *Blueprint Flaws* (wrong requirements or design) are more catastrophic than execution "bugs".
	* *Late Defect*: "Doing things the wrong way" (fixable)
	* *Early Defect*: "Doing the *wrong* things" (fatal)

#####  Who Does Software Testing?
- *Test Manager*: Manages the test project, defines test plan, supervises test engineers.
- *Software Test Engineer / QA Engineer*: Designs test cases, executes tests, reports bugs.
- *Developers (Unit Testing)*: Write and maintain unit tests; responsible for TDD in Agile teams.
- *Business Analysts / Product Owners*: Define acceptance criteria; perform UAT.
- *End Users*: Participate in alpha and beta testing; provide real-world feedback that no internal test can replicate.


# CH 2: Fundamentals of Software Testing
##### Three Testing Dimensions
1. Structural (White-Box) vs. Functional (Black-Box)
	- Source of test cases: internal code knowledge OR external specification?
2. Static vs. Dynamic
	- Is the software EXECUTED during testing, or ANALYZED without execution?
3. Manual vs. Automated
	- Who or what executes the tests - human or tool?

### Structural vs. Functional Testing
- Structural testing, (white-box testing), derives test cases from the internal code itself. The tester reads the source code, understands its logic, and designs inputs to exercise specific paths, branches, and conditions.
- Functional testing, (black-box testing), derives test cases entirely from the external specification, the requirements, user stories, or use cases. 

| **Structural (White-Box)**                    | **Functional (Black-Box)**                        |
| --------------------------------------------- | ------------------------------------------------- |
| Uses internal code knowledge.                | Treats software as an opaque box.                |
| Tester examines source code.                 | Tester only sees inputs and outputs.             |
| Requires programming expertise.              | Requires domain/requirements knowledge.          |
| Tests paths, branches, conditions.           | Tests features, use cases, user stories.         |
| Goal: exercise all code paths.               | Goal: satisfy all requirements.                  |
| Example: path coverage in a payment function. | Example: testing that login form works correctly. |
- Gray-Box:  Best for integration and API testing, partial code knowledge improves test design.
- In Agile: Developers write white-box unit tests. Testers write black-box acceptance tests. Both mandatory.

### Static vs. Dynamic Testing
Is the software actually running when the test is performed? 

Static testing means examining an artifact. whether that is code, a requirements document, a design diagram, or a test plan without executing the software. 
- the most cost-effective form of testing because defects found at this stage cost almost nothing to fix.
- Finds: logic errors, inconsistencies, coding standard violations, missing requirements.
- Examples: code review, walkthrough, SonarQube, requirements review.

Dynamic testing means the software is compiled, deployed, and actually running while the test is performed. 
- Is the only way to detect runtime behaviors such as crashes, memory leaks, or incorrect outputs.
- Higher cost, requires a working build.
- Examples: unit tests, functional tests, load tests.


**All Four Combinations Exist** 
STATIC BLACK-BOX: Review the SPECIFICATION without running the software.
- Read requirements and find: ambiguity, incompleteness, untestable statements.
- Example: In sprint planning, asking 'What happens if the email doesn't exist?'

STATIC WHITE-BOX: Review the SOURCE CODE without running the software.
- Code review, peer review, static analysis tools (SonarQube, `ESLint`).
- Example: Reviewing a pull request for SQL injection vulnerabilities.

DYNAMIC BLACK-BOX: RUN the software; test through its external interface.
- Click through a login form, observe behavior, compare to expected.
- Most of what QA engineers do during feature testing.

DYNAMIC WHITE-BOX: RUN the software; use code knowledge to design precise tests.
- Write a unit test that directly calls a function and checks its return value.
- Measure branch coverage while tests execute.

Static testing is PREVENTION. Dynamic testing is DETECTION.

### Manual vs. Automated Testing
Who or what actually executes the tests?

Manual testing means a human tester works through test steps, observes results, and uses judgment to determine whether behavior is correct. 
- excels where human perception, judgment, and adaptability are required.
- exploratory, usability, UX, ad-hoc.
- Best for: new features, changing behavior.
- Tools: TestRail, Zephyr, Jira.

Automated testing means a script or tool executes steps, compares outputs to expected results, and produces a pass/fail report without human intervention at execution time.
- excels where speed, repeatability, and scale are required. 
- regression, load, repetitive checks.
- Best for: stable, frequently re-verified behavior.
- Tools: Selenium, Cypress, Playwright, JUnit.

They serve different purposes, and a mature testing practice needs both. 

> [!tldr] Golden Rule
>Automate What You Repeat, Explore What You Cannot Predict
>In Agile: Developers automate unit tests. QA automates regression. Manual = exploration.

### Role, Tasks, and Qualities of a Software Tester
**Modern Tester's Role** 
 tester is a quality advocate, not a gatekeeper. In Agile, testers collaborate from day one, refine acceptance criteria, and make quality everyone's shared responsibility.
 
Key Responsibilities
1. Review requirements and user stories for testability and completeness.
2. Design test plans, strategies, and test cases.
3. Execute tests and log defects with clear reproduction steps.
4. Verify bug fixes through retesting and regression.
5. Maintain and evolve the automated test suite.
6. Report test progress, coverage, and quality risk.

Qualities of an Effective Tester
- *Analytical mindset*: Decomposes complex requirements into testable conditions.
- *Skepticism*: Does not assume software works., always verifies.
- *Communication*: Writes clear, actionable bug reports developers can reproduce.
- *Empathy*: Tests from the user's perspective., 'what would a real user do?'
- *Technical curiosity*: Explores edge cases and unexpected inputs.

# CH 3: Black-Box Testing
The tester provides inputs and observes outputs without any knowledge of (or reference to) the internal code. 
Tests are derived entirely from external specifications: requirements documents, user stories, use cases, and acceptance criteria.
It is also called: Functional Testing, Behavioral Testing, Specification-Based Testing, and Closed-Box Testing.

### Advantages and Disadvantages
| **Advantages**                                                    | **Disadvantages**                                                   |
| ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| Test cases are written from user's perspective - highly relevant. | Cannot ensure all code paths are exercised.                         |
| No programming expertise required - domain knowledge is enough.   | Test design is difficult if specifications are vague or incomplete. |
| Tester is unbiased - not influenced by developer assumptions.     | Risk of redundant or missing test cases without code insight.       |
| Effective for integration, system, and acceptance testing.        | Finding root cause of failures requires code knowledge.             |

##### What Black-Box Testing Finds
- Missing or incorrect functionality - a feature doesn't behave as specified.
- Interface errors - buttons, forms, or navigation behave incorrectly.
- Data structure errors - incorrect display or storage of data.
- Performance errors - feature works but is too slow.
- Initialization and termination errors - app state incorrect at start or end of a session.

### Static Black-Box Testing
What to look for: Ambiguity ('should respond quickly' - how quick?), incompleteness (what happens on timeout?), inconsistency, un-testability.

Agile Example - Static Black-Box on a User Story
User Story: As a student, I want to submit my assignment online so I can work remotely.

Questions to raise BEFORE coding begins (static review):
- What file types are accepted? PDF only? Word? ZIP?
- What is the maximum file size?
- Can a student re-submit after the deadline?
- What happens if the student loses connection mid-upload?
- Does the student receive a confirmation email?
- What if two students submit files with the same filename?

Finding these gaps in sprint planning = preventing bugs before they exist.

### Dynamic Black-Box Testing Techniques
##### Equivalence Class Partitioning
Divide the input domain into classes where all values in a class are expected to behave identically. 
Test one representative from each class to reduce infinite inputs to a manageable set.

Example: Student Grade Input (0–100)
- Class 1: Below range  (< 0)     → Test: -5    → Expected: Validation error
- Class 2: Valid range  (0–100)   → Test: 75    → Expected: Grade accepted
- Class 3: Above range  (> 100)   → Test: 110   → Expected: Validation error
- Class 4: Non-numeric            → Test: 'A'   → Expected: Validation error
4 test cases effectively cover all possible inputs.

##### Boundary Value Analysis
Developers make off-by-one errors far more often than mid-range errors. 
Test the boundary values and their immediate neighbors.

Example: Loan Age Requirement (valid: 18–65)
- 17  → Invalid  (just below lower bound)
- 18  → Valid    (lower bound)
- 19  → Valid    (just inside lower bound)
- 64  → Valid    (just inside upper bound)
- 65  → Valid    (upper bound)
- 66  → Invalid  (just above upper bound)

The condition 'if (age >= 18 && age <= 65)' is most likely to be wrong at 17, 18, 65, 66.

##### Decision Table Testing
Maps every meaningful combination of conditions to expected actions. Each table row = one test case.
Example: Insurance Premium Calculation

| **Age < 25** | **Has Accident** | **Discount** | **Premium** |
| ------------ | ---------------- | ------------ | ----------- |
| Yes          | Yes              | No           | High Risk   |
| Yes          | No               | No           | Standard    |
| No           | Yes              | No           | Elevated    |
| No           | No               | Yes          | Low Risk    |

##### State Transition Testing
Used for systems with states triggered by events. Tests verify valid transitions work and invalid ones are rejected.

Example: ATM States
IDLE → CARD_INSERTED → PIN_ENTERED → AUTHENTICATED → TRANSACTION_DONE

Test: happy path / wrong PIN 3× → CARD_LOCKED / invalid transitions.

##### Random and Mutation Testing
- **Random Testing**: Provides random inputs to find unexpected crashes. Foundation of fuzz testing.
- **Mutation Testing**: Tester introduces small code changes (mutations) and checks if tests CATCH them. If tests pass with mutations, the test suite is weak.

##### Data Testing and State Testing
- **Data Testing**: Tests all data the user inputs - keyboard, mouse, file. Verifies correct handling of boundary, invalid, and extreme data values.
- **State Testing**: State diagrams map software modes. Tests ensure correct transitions and rejection of invalid state jumps.

# CH 4: White-Box Testing
Examines the internal code structure. The tester has full access to source code and uses it to design test cases that exercise specific paths, branches, and conditions. 
Every white-box test case is derived from the code, not the specification.


| **Advantages**                                                | **Disadvantages**                                        |
| ------------------------------------------------------------- | -------------------------------------------------------- |
| Tester can design highly targeted tests using code knowledge. | Requires programming expertise - skilled testers needed. |
| Helps optimize code - reveals dead/redundant code.            | Cannot find missing features - only tests what exists.   |
| Can achieve measurable code coverage.                         | Path coverage grows exponentially with code complexity.  |
| Catches hidden bugs invisible to black-box testing.           | Time-consuming for large codebases.                      |

### Static White-Box Testing
Analysis of code and technical artifacts WITHOUT execution.

**Formal Review Techniques** 
- *Peer Review (Buddy Review)*: Informal review between team members. Catches obvious issues quickly.
- *Walkthrough*: Developer presents code to 5-6 teammates who discuss structure, logic, and functionality.
- *Formal Inspection*: Structured, documented review. Roles: Moderator, Author, Inspector, Recorder. Most thorough but most expensive.
- *Static Analysis Tools*: SonarQube, `ESLint`, `Checkstyle`, Bandit (Python)., automated code scanning without execution.

**Common Code Errors** Found in Static Review
- Data Reference Errors: Using variables before initialization.
- Data Declaration Errors: Wrong type, length, or storage class.
- Computation Errors: Integer overflow, division by zero, type mismatches.
- Comparison Errors: Using < instead of <= at boundaries.
- Control Flow Errors: Infinite loops, unreachable code, missing break statements.
- Interface Errors: Wrong parameter types passed between modules.

### Dynamic White-Box Testing
Executes the code while using internal knowledge to design tests that cover specific paths, branches, and conditions.

##### Coverage Metrics
a family of related metrics, each measuring a different degree of thoroughness.

> 100% statement coverage does NOT guarantee 100% branch coverage. 

| Coverage Type      | What It Measures                                                                                                                            |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------- |
| Function Coverage  | Every function/method is called at least once. The most basic, easy to achieve, easy to fool.                                               |
| Statement Coverage | Every executable statement runs at least once. Minimum baseline. Common but insufficient alone.                                             |
| Branch Coverage    | Every branch (true AND false) of every decision executes. Stronger than statement, catches missed else-clauses and untested conditions.     |
| Condition Coverage | Every Boolean sub-expression evaluates to both true and false. Targets compound conditions (AND, OR).                                       |
| Path Coverage      | Every unique execution path through the function is traversed. Most thorough, grows exponentially with code complexity.                     |
| MC/DC Coverage     | Modified Condition/Decision Coverage. Each condition independently affects the outcome. Required in aviation (DO-178C) and medical devices. |

```
def example_function(x, y):
    # Statement 1
    if x > 0:
        # Statement 2
        print("X is positive")
    
    # Statement 3
    if y > 0:
        # Statement 4
        print("Y is positive")
    
    # Statement 5
    print("Done")
    

// x=1, y=1 would achieve 100% statement coverage but not all branches are covered
// the 2 if statements only went the true branch and we need x=0, y=0 to acheive 
// 100% branch coverage
```

> Function Coverage  ⊂  Statement Coverage  ⊂  Branch Coverage  ⊂  Path Coverage

> [!tldr] Recommended
> - Industry minimum recommendation: 80% BRANCH coverage for production code.
> - Not statement coverage - but branch coverage.
> - Condition Coverage:  Good for complex boolean logic.
> - Path Coverage:       Ideal but infeasible for large functions - use for critical algorithms.

##### Dynamic White-Box Testing vs. Debugging
| **Dynamic White-Box Testing**                                   | **Debugging**                                                  |
| --------------------------------------------------------------- | -------------------------------------------------------------- |
| Intentional - tester designs inputs to exercise specific paths. | Reactive - developer investigates after a failure is observed. |
| Systematic and measurable (coverage metrics).                   | Exploratory - follows the trail of a specific failure.         |
| Produces test cases that can be re-run.                         | Produces a fix, not a reusable test.                           |
| Goal: FIND defects.                                             | Goal: LOCATE and FIX a known defect.                           |

# CH 5: Special Types of Testing
### Test Levels - The Testing Hierarchy

| **Level**           | **What Is Tested**                                                   | **Who Runs It**                  |
| ------------------- | -------------------------------------------------------------------- | -------------------------------- |
| Unit Testing        | Individual functions, methods, or classes in isolation.              | Developers (TDD in Agile)        |
| Integration Testing | Multiple components working together - interfaces and data exchange. | Developers + QA                  |
| System Testing      | The complete integrated product against all requirements.            | Independent QA team              |
| Acceptance Testing  | Product from the user/customer perspective - are their needs met?    | Client, end-users, Product Owner |

A defect caught at unit level costs a fraction of what it costs when the same defect surfaces during system testing - which is why testing at every level, not just the end, is critical professional practice.

##### Unit Testing
Each module, a function, class, or service is tested in isolation, with external dependencies replaced by test doubles (mocks, stubs, fakes).
- Focus areas: Data structures, program logic, component interfaces, boundary conditions, error handling paths.
- Frameworks: JUnit/TestNG (Java), pytest (Python), Jest (JavaScript), NUnit (.NET), RSpec (Ruby).
- Best practice: Test-Driven Development (TDD) - write the test before the code.

**Test Driven Development** (TDD) Cycle: Red → Green → Refactor
1. *RED*: Write a failing test for the desired behavior.
2. *GREEN*: Write the minimum code to make the test pass.
3. *REFACTOR*: Improve the code without breaking the test.
TDD guarantees every line of production code has a corresponding test.

##### Integration Testing
Integration testing verifies that individually working modules cooperate correctly. Interface errors, data exchange bugs, and assumption mismatches are all integration-level defects.
- **Big Bang**: All modules combined and tested at once. Simple but hard to isolate failures.
- **Top-Down**: High-level modules first; lower modules replaced by stubs.
- **Bottom-Up**: Lower modules first; higher modules replaced by drivers.
- **Incremental (Agile preferred)**: Add one module at a time; test before adding the next.

##### System Testing
Evaluates the complete, integrated product against all specified requirements. It is black-box testing applied to the entire system, performed in a staging environment that mirrors production.
- **Scope**: End-to-end workflows, all components, external interfaces, data flows.
- **Who**: Independent QA team, separated from development to ensure unbiased testing.
- **Exit criteria**: All critical test cases pass; defect count within threshold; performance SLAs met.

##### Regression Testing
Regression testing verifies that new changes have not broken existing functionality.
*   **When**: After every bug fix, feature addition, refactoring, or dependency upgrade.
*   **How**: Run the automated regression suite on every commit (CI/CD pipeline).

**Automate Regression** 
- Catches breaks immediately on every commit.
- Tools: Selenium, Cypress, Playwright (UI), JUnit/`pytest` (unit), Postman/Newman (API).

##### Acceptance Testing
Types of Acceptance Testing
* **User Acceptance Testing (UAT)**: Real users verify the system meets actual business needs in a realistic environment.
* **Business Acceptance Testing (BAT)**: Development organization internally verifies the system will pass UAT.
* **Operational Acceptance Testing (OAT)**: Operations team verifies deployment, backup, recovery, and monitoring procedures.

**Alpha Testing and Beta Testing** 
Two stages of user acceptance testing that bring the product outside the internal team and into the hands of real people.
- they serve different purposes at different levels of product readiness.

*Alpha Testing - Internal Real-User Testing* 
- *WHO*:  by internal real users within the organization before external release.
- *WHEN*: before any external user accesses the product, and testers know it's unfinished.
- *WHERE*: in a controlled environment where testers can be monitored.
- *GOAL*: to find functional defects and usability issues missed by QA with fresh eyes.
*e.g.* A university staff testing a new student portal before students use it.
*What to collect*: bug reports, task completion rates, time-on-task measurements,
user confusion points, features users expected but could not find.

*Beta Testing - External Real-User Testing*
- *WHO*: by real end users outside the organization, representing the target user base.
- *WHEN*: after alpha testing is complete, before the product is publicly released.
- *WHERE*: in the user's own uncontrolled environment, simulating real-world usage.
- *GOAL*: to discover defects in real-world conditions and gather feedback on user needs.
*e.g.* Google releasing a new Gmail feature to a small percentage of users.
*What to collect*: crash reports, usage analytics, user satisfaction surveys, feature requests, abandonment points.

**Agile UAT: The Sprint Review** 
- In Agile, the Product Owner performs lightweight UAT at every sprint review.
- They accept or reject each user story based on whether acceptance criteria are met.
- This catches misalignment sprint by sprint rather than in a large batch at project end.

##### Configuration Testing
Evaluates how well the system performs under different hardware, software, network, and environmental configurations. 
**Goal**: ensure the product works across all supported environments.
* **Hardware variations**: CPU, RAM, storage, graphics cards, peripherals.
* **Software variations**: OS versions, browser versions, database versions.
* **Network configurations**: broadband, 3G, VPN, proxy.
* **Also known as**: Portable Testing, Hardware Compatibility Testing.
e.g. 
- Video player unusable on 3G - no adaptive bitrate streaming configured.
- Assignment form layout broken on small Android screens (360px width).
##### Compatibility Testing
Two directions:
* **Backward compatibility**: Can the new version of software work correctly with data, files, or systems produced by older versions?
	* Critical for software upgrades and migrations.
* **Forward compatibility**: Can an older version of the software handle data or messages produced by a future, newer version without crashing or corrupting information?
	* Critical for distributed systems and API versioning.

Both matter in professional software development, and which one takes priority depends on the context.

##### GUI / Usability Testing
GUI testing (usability testing) evaluates how well users can accomplish tasks with the interface. It is the most direct connection between testing and quality-as-user-satisfaction.

**Four Stages of GUI Testing**
1. **Low Level**: Individual UI controls, such as buttons, input fields, dropdowns, and checkboxes.
2. **Application Level**: Functional verification of workflows through the UI.
3. **Integration Level**: UI interactions with back-end services and APIs.
4. **System Level**: Complete end-to-end user journeys across the full product.

**Traits of a Good User Interface**
- **Intuitive**: Users can accomplish tasks without documentation.
- **Consistent**: Same patterns used throughout, with buttons looking and behaving the same way.
- **Flexible**: Supports different user workflows and preferences.
- **Comfortable**: Appropriate response times and forgiving error handling.
- **Responsive**: Works across screen sizes and input methods.
- **Accessible**: Usable by people with disabilities (WCAG compliance).

##### Smoke Testing
Checks whether the most basic functions of a new build are working before investing in detailed testing. (like checking for a literal smoke in a new PCB)

**Characteristics**
* **Broad Coverage**: Touches many features at a high level.
* **Shallow Depth**: Does not test edge cases or complex scenarios.
* **Fast**: Completes in 5-15 minutes.
* **Automated**: Triggered automatically when a new build is deployed.
* **Binary Result**: *PASS*: proceed to full testing. *FAIL*: reject build, notify developers.
* Also called: **Build Verification Test (BVT)**, **Build Acceptance Test**.

e.g. for a banking app: does login work?, does it load in 3 sec? can you see your balance? ...

##### Sanity Testing
A narrow, focused check performed after a specific bug fix or small change to verify the fix works and has not introduced obvious regressions in adjacent functionality. It is a subset of regression testing.

| **Testing Type** | **Description**                               | **Scope**    | **Performed**           | **Fail Criteria**   | **Automation**             |
| ---------------- | --------------------------------------------- | ------------ | ----------------------- | ------------------- | -------------------------- |
| Smoke Testing    | Broad and shallow  many features, brief check | Entire build | New build               | Reject entire build | Typically automated        |
| Sanity Testing   | Narrow and deep one area tested thoroughly    | Specific fix | Bug fix or small change | Reject specific fix | Can be manual or automated |

e.g. 
**Bug Fix:** 
* Login button was unresponsive with special characters in username
* Fixed by updating input validation regex

**Sanity Test Results:** 
* Username with @, spaces, or emojis now work as expected
* Normal login (no special characters) still works
* Password field unaffected by the change

##### Performance Testing
**Load Testing** 
Verifies the system meets performance requirements under *expected normal load*.
* **Goal**: Confirm the system meets its SLAs (Service Level Agreements) under normal conditions.
* **Metrics**: Response time (avg, 95th percentile), throughput (req/sec), error rate.
* **Tools**: Apache JMeter, k6, Gatling, Locust.

**Stress Testing**
Pushes the system *beyond* its designed capacity to find the breaking point and understand failure behavior. The goal is to know at what load it fails, and whether it fails gracefully or catastrophically.
- **Key question**: When it fails, does it crash completely or degrade gracefully?
- *Recovery testing*: After stress is removed, does the system recover automatically?
- Tools: **JMeter**, **Gatling**, **k6**, **LoadRunner** (enterprise).

**Spike, Endurance, and Scalability Testing**
* **Spike Testing**: Sudden dramatic load increase in seconds. Example: Black Friday traffic surge. Tests auto-scaling and burst capacity.
* **Endurance (Soak) Testing**: Normal load for hours/days. Finds memory leaks, connection exhaustion, gradual degradation.
* **Scalability Testing**: Does performance remain acceptable as data volume and users grow?


| Tool          | Best For                                 |
| ------------- | ---------------------------------------- |
| Apache JMeter | Load, stress, functional web/API testing |
| k6            | Developer-friendly scripted load tests   |
| Gatling       | High-throughput API load testing         |
| Locust        | Python-based complex scenario testing    |
| LoadRunner    | Enterprise performance testing           |

##### Security Testing
**Data Security Fundamentals**
* *Confidentiality*: Protect sensitive information from unauthorized access and exposure.
	+ Use access controls, encryption, and data classification.
* *Integrity*: Ensure data accuracy and prevent tampering or modification.
	+ Verify data integrity through security testing.
* *Authentication*: Validate user identities and prevent unauthorized access.
	+ Use mechanisms like passwords and multi-factor authentication.
* *Authorization*: Control access rights based on user roles and permissions.
	+ Verify that only authorized users can perform specific actions.
* *Availability*: Ensure systems and services are accessible when needed.
	+ Test resilience against DoS attacks and system failures.
* *Non-repudiation*: Establish accountability for user actions.
	+ Use digital signatures and audit logs to track transactions and approvals.

**Vulnerability Assessment** 
Systematic Automated Scanning for Known Security Weaknesses. Tools compare the system against databases of known vulnerabilities (CVEs - Common Vulnerabilities and Exposures).
* **Tools:** Nessus, OpenVAS, OWASP Dependency-Check (for software libraries)
* **Schedule:** Weekly or monthly automated scans; on every dependency update in CI/CD.

**Penetration Testing**
Ethical hackers manually attempt to exploit the system using real attacker techniques.
Produces proof-of-concept exploits and detailed remediation guidance.
* *Tools*: **Burp Suite**, OWASP ZAP, Metasploit, Nikto.
* *When*: Quarterly or annually; before major releases; after significant architecture changes.

**OWASP Top 10** 
* **SQL Injection**: Tricking the site into running database commands. Test with `' OR '1'='1` at login; it should be rejected.
* **XSS**: Injecting scripts into a site. Test with `<script>alert(1)</script>`; it should show as text not execute it as a script.
* **Broken Authentication**: Weak login/session handling. Test expired tokens and login attempt limits.
* **Broken Access Control**: Accessing data you shouldn't. Test by trying to view another user's data (e.g., `/users/2/orders`); expect a 403 error.
* **Security Misconfiguration**: Poor security settings. Check for exposed server versions and overly detailed error messages.

**The CIA Triad** - What Security Testing Protects
- CONFIDENTIALITY: Data accessible only to authorized users.
	- Test: Can an unauthenticated user access protected resources?

- INTEGRITY: Data is accurate and untampered.
	- Test: Can a user modify records they shouldn't be able to change?

- AVAILABILITY: System is operational when needed.
	- Test: Can a DoS attack render the system unusable?

**Types of Security Testing** 

| Type                         | Description & Tools                                                                                                                                               |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| SAST - Static Analysis       | Analyze source code for vulnerabilities without running it. Tools: SonarQube, Checkmarx, Semgrep. Finds: hardcoded secrets, injection patterns, unsafe functions. |
| DAST - Dynamic Analysis      | Test the running application from outside. Tools: OWASP ZAP, Burp Suite. Finds: XSS, injection, auth flaws in the live system.                                    |
| IAST - Interactive Analysis  | Agent inside running app monitors during test execution. Tools: Contrast Security. Low false positives.                                                           |
| Penetration                  | Ethical hacker exploits the system with real techniques. Output: proof-of-concept exploits + remediation guidance.                                                |
| Vulnerability Scanning       | Automated scan for known CVEs in infrastructure and libraries. Tools: Nessus, OpenVAS, OWASP Dependency-Check.                                                    |
| API Testing                  | Checks authentication, authorization, input validation, and data exposure.                                                                                        |
| Security Auditing            | Evaluates compliance with security policies and standards. Reviews configurations, access controls, and security practices.                                       |
| Risk Assessments             | Assesses the risk associated with specific threats or vulnerabilities.                                                                                            |
| Security Posture Assessments | Evaluates the overall security posture of an organization. Considers people, processes, and technology.                                                           |
**Key Security Testing Areas**
* **Network Security**: Firewalls, routers, switches - follow best practices? Open ports minimized?
* **Application Security**: Code, architecture, APIs - reviewed for vulnerabilities.
* **Client-Side Security**: Browser storage misuse, JavaScript injection, CSP headers.
* **Authentication & Authorization**: Strong password policies, MFA, session management, RBAC.
* **Data Security**: Verify encryption mechanisms, access controls, and data masking.
* **Web Security**: (e.g., SQL injection, cross-site scripting) Check session management, input validation, and secure communication.
* **Infrastructure Security**: Assess server configurations, operating systems, and services. Verify patch management, and user access controls.

**`DevSecOps`: Embedding Security Throughout Development**
1. **Commit:** We perform Static Application Security Testing (SAST) on every code push to identify security weaknesses.
2. **Build:** A dependency scanner checks all included libraries for known vulnerabilities (CVEs).
3. **Testing:** Automated Dynamic Application Security Testing (DAST) scans the application in a test environment.
4. **Pre-Release:** A security specialist conducts a manual penetration test.
5. **Production:** We continuously monitor the live environment using tools like SIEM and intrusion detection systems.

##### Monkey Testing and Gorilla Testing
**Monkey Testing** 
Sends random, unstructured inputs to the application, such as random clicks, data, and navigation sequences, to find stability failures and crashes that structured tests would never discover.

| **Dumb Monkey**                           | **Smart Monkey**                                      |
| ----------------------------------------- | ----------------------------------------------------- |
| Completely random, no model of the app    | Random but guided by a state model                    |
| Low bug yield                             | Higher yield, focuses on interesting states           |
| Easy to implement                         | Requires building an app state model                  |
| Good for: crash resistance, memory safety | Good for: complex state machines, security edge cases |

**Gorilla Testing** 
Concentrated, exhaustive testing of one specific module, like a gorilla pounding it relentlessly. 
Gorilla testing is deliberate: test every conceivable edge case in a single high-risk component.
* When to use: High-risk, high-frequency, or previously buggy modules: payment processing, authentication, file upload.

*Example*: testing a login module to ensure it handles incorrect credentials, forgotten passwords, and other edge cases.

##### Exploratory Testing
Exploratory testing is simultaneous learning, design, and execution. The tester explores the application guided by a mission (charter) rather than a script, using domain knowledge and intuition to find bugs that no script anticipated.
* **Session-Based Testing**: Define a charter for a focused 60–90 minute session. Document findings in real time.
* *What it finds*: Business logic errors, unexpected feature interactions, usability issues, and bugs nobody wrote a test case for.

##### A/B Testing
* A controlled experiment comparing two or more versions of a feature to determine which one performs better.
* Users are randomly divided into groups usually 50/50 (control and variant) and use the product normally.
	* usually it is an existing version and a new modified version.
* Metrics are compared after a statistically significant number of interactions to declare a winner.
* This method eliminates *subjective design* debates by prioritizing data-driven decisions over opinion.
- **Tools**: Optimizely, `LaunchDarkly` (feature flag–based), Google Optimize, VWO (Visual Website Optimizer), `Statsig`.

e.g. 
**Problem:** High cart abandonment (68%) due to a potentially overwhelming single-page checkout.
**Solution:** A 4-step checkout wizard was designed.
**A/B Test:**
*   **Groups:** Original single-page vs. 4-step wizard (25k users each).
*   **Goal:** Improve checkout completion rate.
- **Results:** maybe higher checkouts with the new wizard.

*Statistical significance*: Results are only valid when the sample size is large enough to rule out random variation. Never stop an A/B test early because early results look good, randomness can be misleading in the first hours or days.

##### Bug Bashes
A bug bash is a time-boxed event where the entire team, including developers, designers, PMs, QA, and customers, test the product simultaneously, bringing diverse perspectives.
* **Duration:** 2–4 hours
* **What happens:**
    * Developers find their own blindspots.
    * Designers find UX issues.
    * PMs find requirement mismatches.

**Best Practices**
1. Prepare devices in advance, including different browsers, OS, and mobile devices.
2. Define the scope of this bash, including which features are in scope.
3. No judgment: typos and crashes are equally valid to report.
4. Use a bug report template, including severity, steps to reproduce, and expected vs. actual results.
5. Triage immediately after, prioritizing and assigning critical bugs before release.


# CH 6: Compatibility & Configuration
[[#Compatibility Testing]] (link)
[[#Configuration Testing]] (link)

# CH 7: Documentation Testing
Documentation is part of the software product, it deserves the same testing rigor as the code.
Documentation testing verifies that all written materials (user guides, API docs, release notes, error messages) are accurate, complete, consistent with the actual software, and usable by their intended audience.
Documentation is 'good' when it contributes to: improved software usability, improved software reliability, and decreased product support costs.

**Types of Software Documentation**
* **Packaging Text and Graphics**: box copy, product images
* **Marketing Material and Inserts**: feature claims must be testable and accurate
* **Warranty and Registration**: legal terms must be clear and correct
* **End User License Agreement (EULA)**: terms of use
* **Installation and Setup Guides**: every step must be reproducible on a clean system
* **User Manuals**: step-by-step instructions; every step verified against actual software
* **In-app Help and Tooltips**: context-sensitive help visible in the UI
* **API Documentation**: endpoints, parameters, response formats, error codes
* **Release Notes**: all documented changes must be present; no undocumented changes

Important characteristics that any documentation testing program should include are: 
- Frequent and early testing 
- Assessment of accuracy and ease of use 
- Evaluation by people who did not write the documentation 

**Documentation Testing Checklist** 
1. **Accuracy** 
	* Features are as described and screenshots match the current UI.
	* Step-by-step instructions are reproducible and version numbers are correct.
2. **Completeness** 
	* All features, edge cases, and error conditions are documented.
	* Error explanations and recovery steps are provided.
	* Prerequisites and dependencies are clearly stated.
3. **Usability** 
	* Language is clear, concise, and suitable for the target audience.
	* Document organization is logical and easy to follow.
	* Links are working and the document is accessible for all users.

**API Documentation Testing** 
*API Documentation Test Cases* 
- TC-DOC-01: Every endpoint in the docs exists in the actual API.
- TC-DOC-02: Every documented request parameter is accepted by the API.
- TC-DOC-03: Documented response structure matches actual response structure.
- TC-DOC-04: All documented error codes are returned in the correct scenarios.
- TC-DOC-05: All code examples in the docs execute without error.

- Tool: Dredd - automatically tests your API against its OpenAPI/Swagger spec.
- Tool: Postman - run documented API examples as automated test collections.

# CH 8: Security Testing
[[#Security Testing]] (link)

# CH 9: Web Application Testing
Web application testing is a distinct field from traditional software testing due to fundamental differences in risk, failure modes, and necessary strategies. 
Unlike local applications, web apps operate on uncontrollable infrastructure, are accessed by unknown users on unfamiliar devices, are exposed to public internet threats, and experience failures that can impact millions simultaneously. Testers unfamiliar with these unique aspects will overlook critical potential issues.

**What Makes Web Application Testing Fundamentally Different** 
1. **Multi-user Concurrency:** Web apps serve many users simultaneously, requiring tests for race conditions, data conflicts, and session issues under load.
2. **Public Attack Surface:** Unlike local apps, web apps are internet-facing, necessitating security testing for vulnerabilities like SQL injection and XSS.
3. **Environment Fragmentation:** Web apps must function across diverse browsers, operating systems, and devices, demanding extensive cross-platform testing.
4. **Stateless Protocol:** HTTP's stateless nature requires testing of web app session management, cookies, and token handling.
5. **Third-Party Dependencies:** Web apps rely on external APIs and scripts, requiring integration and dependency testing.
6. **Real-time Performance:** Users expect rapid loading times, making performance testing crucial for business impact.
7. **Continuous Deployment:** Frequent deployments in web development necessitate automated regression testing within CI/CD pipelines.
8. **Accessibility and Legal Compliance:** Public-facing web applications must adhere to accessibility laws (e.g., WCAG) and data protection regulations (e.g., GDPR).

**Web Applications vs. Websites** 
A website primarily delivers static or semi-static content, text, images, links to users who read it. Testing a website focuses mainly on content accuracy, link validity, and basic browser compatibility.

A web application, is an interactive program that runs on a web server and is accessed through a browser. It allows users to perform actions, manipulate data, and engage in transactions. 

Testing a web application requires testing functionality, performance, security, database integrity, API contracts, accessibility, and much more.

| **Static Website**         | **Web Application**                          |
| -------------------------- | -------------------------------------------- |
| Primarily static content.  | Dynamic, interactive, stateful.              |
| Users consume information. | Users create, modify, interact with data.    |
| Simple HTML/CSS            | Complex JS frameworks (React, Angular, Vue). |
| Minimal backend            | APIs, databases, authentication, sessions.   |
| e.g. Brochure sites        | e.g. Gmail, GitHub, banking portals, LMS.    |

**What to Test in a Web Application** 
* **Functionality**: Features, UI elements, APIs, business logic, data validation, error handling. (Selenium, Cypress)
* **Performance**: Load testing, stress testing, scalability, response times. (JMeter, `LoadRunner`)
* **Compatibility**: Cross-browser, cross-device, cross-OS. (`BrowserStack`, Sauce Labs)
* **Security**: Authentication, authorization, input validation, data exposure. (OWASP ZAP, Nessus)
* **Database**: Data integrity, CRUD operations, performance, backup/recovery.
* **API**: Authentication, authorization, input validation, response format, error codes.
* **Regression**: CI/CD pipeline runs after every change. (Jenkins, `CircleCI`, Travis CI)
* **Accessibility**: WCAG 2.1 compliance: screen readers, keyboard navigation, color contrast.
* **Localization**: Multiple languages, date/time formats, currency, regional content.
* **Smoke Testing**: Build verification on every deployment.
* **Usability Testing** - Evaluate the ease of use and user experience of the web application.
* **User Acceptance Testing** - Validate the web application against user requirements and business processes.

### Responsive Design Testing
Responsive design ensures the web application works correctly across all screen sizes.

Breakpoints to Test
- Mobile portrait: 320px–480px (small phones), 480px–768px (large phones).
- Tablet: 768px–1024px (portrait and landscape).
- Desktop: 1024px–1440px (standard), 1440px+ (large/4K screens).

What to Verify
- Navigation collapses to hamburger menu on mobile.
- Text is readable (minimum 16px base font size).
- Touch targets are at least 44×44px (WCAG recommendation).
- Images scale correctly and do not overflow.
- Forms are usable with on-screen keyboard.

**Tools** 
`Chrome DevTools`, Device Toolbar:	Built-in browser to simulate screen sizes and pixel ratios instantly.
`Playwright`	- Automation framework, Run tests across Chrome/Firefox/Safari with viewport configuration. Best for automated responsive testing in CI.
`Percy / Chromatic`	- Visual regression, screenshot-based comparison across builds. Detects layout changes. Integrates with Storybook.

##### Browser Developer Tools
* **`console.log`**: In testing, it's invaluable for debugging by allowing you to:
    * Track the execution flow of your JavaScript code.
    * Inspect the values of variables at specific points.
    * Verify if certain conditions are being met.
    * Quickly check if a piece of code is being reached.

* **Breakpoints**: When the code execution reaches a breakpoint, it pauses. This allows you to:
    * Inspect the state of the application at that exact moment: variable values, call stack, scope...
    * Step through the code line by line to follow the execution logic.
    * Examine how data changes over time and identify the exact location where unexpected behavior occurs.
    * Evaluate expressions in the console while the code is paused.

**The Network panel** records all HTTP requests, detailing sent requests (headers, body) and received responses (status code, headers, body). This is crucial for testers to verify frontend-backend communication and API contracts, turning UI observations into bug reports.

**Network throttling**, simulates real-world network constraints (e.g., slow 3G) to test application performance under less-than-ideal conditions, revealing issues like long load times or buffering that wouldn't appear on fast connections.

**Lighthouse** a tool within Chrome `DevTools`, automates web quality audits across Performance, Accessibility, Best Practices, SEO, and PWA compliance. It provides scored reports with specific, actionable findings and recommendations for improvement. Lighthouse runs audits in a simulated environment, measures real metrics, and explains what's impacting the score and how to fix it.

More `DevTools` 
- **Elements Panel:** Inspect and modify live HTML/CSS to verify UI components and DOM structure.
- **Application Panel:** Inspect browser storage (cookies, localStorage, etc.), verify session data handling, and check cookie attributes for security.
- **Performance Panel:** Record runtime performance to identify jank, layout issues, and memory leaks.
- **Memory Panel:** Take heap snapshots to detect and diagnose memory leaks.
- **Security Panel:** Check HTTPS, certificate validity, and identify mixed content warnings.

##### Section 508 & WCAG Accessibility Compliance Testing
Section 508 mandates that all federal agencies and organizations receiving federal funding must ensure their digital products are accessible. (US Law)

**WCAG** The Technical Standard Behind 508
The Web Content Accessibility Guidelines (WCAG) provide the specific technical criteria that define accessible web content.

The WCAG `POUR` principles:
* **Perceivable:** Present information in ways all users can perceive (e.g., alt text for images, captions for videos).
* **Operable:** Ensure all functionality is operable via keyboard, with no keyboard traps, and avoids seizure-inducing flashes.
* **Understandable:** Make information and UI operations clear, with understandable error messages and proper form labeling.
* **Robust:** Ensure content is interpretable by assistive technologies using valid HTML and ARIA attributes.

*WCAG Conformance Levels* 

| Level                                 | Meaning                                                                                                                                                                                        |
| ------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Level A (Minimum)                     | The most basic accessibility requirements. Example: all images have alt attributes.                                                                                                            |
| Level AA (Standard - Required by 508) | Removes significant barriers for disabled users. This is the legal requirement for Section 508 and most national accessibility laws. Example: color contrast ratio ≥ 4.5:1 for normal text.    |
| Level AAA (Enhanced)                  | The highest level. Not required by law, but represents best practice. Some criteria are impossible to meet for all content types. Example: sign language interpretation for all audio content. |

Accessibility testing tools:
* **Automated Scanners:** axe DevTools, Lighthouse (quick audit), WAVE (visual overlay).
* **Screen Readers:** NVDA/JAWS (for blind users), VoiceOver (Apple devices).
* **Color Contrast:** Color Contrast Analyzer.
* **CI/CD Integration:** Pa11y (command-line).

##### Internationalization (i18n) and Localization (l10n) Testing

| **Concept** | **Description**                                                                           | **Frequency**   | **Example**                       | **Tests**                                                                       |
| ----------- | ----------------------------------------------------------------------------------------- | --------------- | --------------------------------- | ------------------------------------------------------------------------------- |
| i18n        | Design and build app for multiple languages, regions, and cultures                        | Done ONCE       | Storing UI text in external files | Can system accept and display characters from any language?                     |
| l10n        | Adapt app for specific locale, translating text, adjusting formats, and tailoring content | Done MANY TIMES | Providing Arabic translation file | Are all strings translated? Is translation accurate and culturally appropriate? |
*Simple Analogy* 
- i18n is building a house with interchangeable wall panels - designed to accept any panel.
- l10n is the specific panel you install for a specific country: Arabic wall, Amharic wall, French wall.
Without i18n done properly, l10n is impossible or extremely expensive.

**i18n (Internationalization) Testing:** Focuses on the *infrastructure* to support *any* locale.
* **Covers:** Character encoding (UTF-8), text expansion (layout fits longer text), RTL support, locale switching, and ensuring no hardcoded strings.

**l10n (Localization) Testing:** Verifies adaptation for a *specific* target locale.
* **Covers:** Complete and accurate translations (including plurals), cultural appropriateness, correct locale-specific formats, and ensuring no offensive content.

##### API Testing
An API is a defined contract that allows one piece of software to communicate with another. 
It specifies: what requests can be made, in what format, with what data, and what responses to expect back. 

**The Three Layers of a Web Application** 
*Layer 1: Presentation (Frontend)* 
* The browser UI - HTML, CSS, JavaScript. What the user sees and clicks.
* Tested by: UI/E2E tests (Selenium, Cypress, Playwright).

*Layer 2: Application (API / Backend)* 
* The server-side logic - business rules, data processing, authentication, calculations.
* Communicated through HTTP API endpoints.
* Tested by: API tests (Postman, REST Assured, Newman, k6).

*Layer 3: Data (Database)* 
* The persistent store - user records, transactions, content.
* Tested by: database integrity tests, query performance tests.

API testing lets you verify Layer 2 directly. faster, more precisely, and without depending on the UI being functional.

**HTTP Methods** 
1. **GET** - Test: correct data returned, filtering, pagination, and unauthorized access
2. **POST** - Test: successful creation, duplicate creation handling, required fields, and invalid data rejection
3. **PUT** - Test: full update success, partial data rejection, non-existent resource, and unauthorized update
4. **PATCH** - Test: partial update success, validation rules enforcement on partial data
5. **DELETE** - Test: successful deletion, resource no longer retrievable, cascading deletes, and unauthorized deletion

**What to Test in an API** 
- **Functional Correctness:** Valid requests get expected responses; side effects are correct; idempotency is maintained.
- **Input Validation:** Handles missing/invalid/malformed inputs gracefully with correct errors.
- **Auth/Authorization:** Correctly rejects unauthorized/unauthenticated requests; enforces permissions.
- **Pagination/Filtering:** Returns correct subsets of data based on parameters.
- **Contract Compliance:** Adheres strictly to the API specification (e.g., `OpenAPI`).
- **Performance:** Responds quickly under both single and concurrent load.

**What Attackers Target in APIs** 
Unlike a UI, which has visual cues and human checks, an API accepts raw programmatic requests - making it easy to automate attacks at high volume.
The OWASP API Security Top 10 is the industry standard reference for API vulnerabilities. 

*Vulnerability Areas* 
1. **Broken Object Level Authorization (BOLA/IDOR):** Accessing other users' resources by ID without proper authorization.
2. **Broken Authentication:** Weak token validation, non-expiring tokens, or insecure password handling.
3. **Excessive Data Exposure:** API returning more sensitive data than necessary.
4. **Mass Assignment:** Allowing users to update unauthorized fields (e.g., `isAdmin`).
5. **Injection:** Malicious input (SQL, NoSQL, command) via API requests.
6. **Rate Limiting Absent:** Lack of throttling on sensitive endpoints like login.
7. **Security Misconfiguration:** Overly permissive CORS, verbose error messages, exposed debug endpoints.

HTTP status code for testers:
**2xx - Success** 
- **200 OK:** Standard success; verify response body contains the requested resource.
- **201 Created:** Resource created successfully; verify existence via GET and Location header.
- **204 No Content:** Success with no body; confirm resource is gone and response is empty.

**3xx - Redirection** 
- **301 Moved Permanently:** Resource moved; ensure application follows redirect and checks for open redirect vulnerability.
- **304 Not Modified:** Client cache is valid; verify response body is empty and cached data is used.

**4xx - Client Errors** 
- **400 Bad Request:** Malformed request; verify descriptive error messages.
- **401 Unauthorized:** Authentication missing/invalid; test with no/expired/malformed tokens.
- **403 Forbidden:** Authenticated but not authorized; test access to restricted endpoints.
- **404 Not Found:** Resource doesn't exist; test with non-existent IDs and wrong URLs.
- **405 Method Not Allowed:** HTTP method not supported; test unsupported methods (e.g., DELETE on read-only).
- **409 Conflict:** Request conflicts with current state; test duplicate resource creation.
- **422 Un-processable Entity:** Semantically invalid request; test with values failing business rules.
- **429 Too Many Requests:** Rate limit exceeded; verify throttling is enforced and Retry-After header exists.

**5xx - Server Errors** 
- **500 Internal Server Error:** Generic server error; always a bug, ensure no sensitive data in error messages.
- **502 Bad Gateway:** Invalid response from upstream; simulate upstream failure.
- **503 Service Unavailable:** Server temporarily unavailable; load test for graceful degradation.
- **504 Gateway Timeout:** Upstream timeout; trigger slow calls and verify graceful timeout handling.

*API Testing Tools* 
* **Postman:** Widely used for API request creation, organization, and testing (manual & CI/CD).
* **Newman:** Postman's CLI for automated API tests in CI/CD.
* **REST Assured (Java):** Java library for coded API tests, integrates with JUnit/TestNG.
* **`Axios` / `SuperTest` (JS):** JS HTTP libraries for coded API tests with Jest/Mocha in Node.js.
* **k6:** API load testing tool for performance measurement under load.
* **Swagger / `OpenAPI`:** API documentation standard for understanding API contract and finding deviations.
* **Insomnia:** Lightweight Postman alternative for quick exploratory testing and documentation.

# CH 10: Mobile Application Testing

**Mobile Testing Challenges**
* **Device Fragmentation**: Thousands of Android models with varying screens, CPUs, RAM, and OS versions.
* **Platform Differences**: iOS and Android have distinct UI paradigms and OS behaviors.
* **Interruptions**: Calls, SMS, notifications, and low battery can interrupt app flow at any moment.
* **Connectivity**: WiFi, 4G, 3G, 2G, offline, and mid-session switching.
* **Battery and Resources**: Apps must not drain battery or consume excessive RAM.
* **Touch Interface**: Tap, swipe, pinch, and long press differ significantly from mouse/keyboard.

**Mobile App Types** 
Understanding the architecture of the app you are testing determines which tools you use, which failure modes you look for, and which platform-specific behaviors matter.

| Type    | Description                                              | Testing Focus                                                          |
| ------- | -------------------------------------------------------- | ---------------------------------------------------------------------- |
| Native  | Built for iOS (Swift) or Android (Kotlin) specifically.  | Platform gestures, hardware access (camera, GPS, NFC), OS integration. |
| Web App | Standard web app in mobile browser.                      | Responsive design, mobile browser compatibility.                       |
| Hybrid  | Web tech in native shell (React Native, Flutter, Ionic). | Both web and native concerns; bridge layer bugs.                       |
| PWA     | Web app with offline capability and `installability`.    | Service worker, offline mode, push notifications.                      |

### Mobile-Specific Testing Types
**Interrupt Testing** 
Mobile apps are constantly interrupted. Every interruption scenario must be tested:
* Incoming phone call during a critical operation (mid-payment, mid-recording).
* Incoming SMS or push notification.
* App sent to background and resumed after 5, 30, or 60 minutes.
* Device screen rotation during active operation.
* Low battery warning appearing.

**Performance Testing on Mobile** 
* **Startup time**: App should launch within 2 seconds (cold start) on mid-range devices.
* **Memory usage**: No abnormal RAM consumption or OS memory warnings.
* **Battery consumption**: Use battery profiling tools to verify normal drain.
* **Data usage**: Critical for users on limited data plans - measure per feature.

**Network Condition Testing** 
* **Offline**: App shows cached data or a clear offline message - does not crash.
* **Online to offline**: What happens when network drops mid-operation?
* **Recovery**: After going offline, app syncs correctly when connectivity returns.

##### Mobile Testing Tools
| Tool                      | Platform      | Use Case                                                                         |
| ------------------------- | ------------- | -------------------------------------------------------------------------------- |
| Appium                    | iOS + Android | Cross-platform test automation using WebDriver protocol. Open source.            |
| XCUITest                  | iOS only      | Apple's native UI testing framework. Fastest for iOS. Built into `Xcode`.        |
| Espresso                  | Android only  | Google's native Android testing framework. Fast, integrated with Android Studio. |
| Detox                     | iOS + Android | End-to-end testing for React Native apps. Good CI/CD integration.                |
| BrowserStack App Automate | iOS + Android | Run Appium tests on real physical devices in the cloud.                          |
| Firebase Test Lab         | iOS + Android | Google's cloud device testing. Real devices and emulators. Free tier.            |
| Charles Proxy             | iOS + Android | Intercept and inspect mobile app network traffic. Essential for API testing.     |

**Security hardening requirements** 
* **Code Encryption/Obfuscation:** Prevent reverse-engineering of compiled code.
* **Developer Options Detection:** Block app function if Android Developer Options are enabled.
* **Screenshot/Screen Recording Prevention:** Secure sensitive screen content from capture.
* **Custom Secure Keyboards:** Use proprietary keyboards for sensitive input (e.g., PINs).
* **Overlay Attack Prevention:** Block malicious apps from drawing transparent overlays.
* **Root/Jailbreak Detection:** Prevent app execution on compromised (rooted/jailbroken) devices.
* **Certificate Pinning:** Prevent man-in-the-middle attacks by trusting specific server certificates.

# CH 11: Automation Testing
Uses software tools to execute pre-scripted test cases, compare actual results with expected results, and report outcomes without human intervention.

### CI/CD
Stands for Continuous Integration and Continuous Delivery (or Deployment).

**Continuous Integration (CI)** 
The practice of frequently merging all developers' code changes into a shared repository typically multiple times per day. Each merge triggers an automated build and automated test suite.

**Continuous Delivery (CD)** 
Continuous Delivery extends CI: after automated tests pass, the software is automatically built into a deployable artifact and potentially deployed to a staging environment ready for production at any time with a single manual approval.

**Continuous Deployment** 
Continuous Deployment goes one step further: every change that passes all automated tests is automatically deployed to production without manual approval. Used by companies like Netflix, Amazon, and Google which deploy thousands of times per day.

##### The Test Automation Pyramid
Is a Strategy for Balanced Test Coverage
- Unit (base):  Fast (< 1 min total). Developers own. Run on every commit.
- API (middle): Medium speed (~2 min). QA + developers share. Test service contracts.
- E2E (end 2 end) (top): Slowest (~5-15 min). QA owns. Focus on critical business paths only.

Anti-pattern: 'Ice Cream Cone' - many E2E, few unit tests.
- Slow, expensive, fragile, and poor diagnostic information when tests fail.

**Benefits of Automation** 
- **Speed**: 1000 tests run in 5 minutes vs. days of manual execution.
- **Consistency**: Identical steps every run - no human error in execution.
- **24/7**: Tests run overnight, on weekends, on every commit.
- **Regression safety**: Broken behavior is caught immediately.
- **Parallel execution**: Run across hundreds of browser/device combinations simultaneously.
- **Frees testers**: Testers focus on exploratory testing and quality strategy instead of repetitive execution.

- *Saves Time and Money*: Faster execution, reusable tests
- *Improves Accuracy*: Automated tests perform the similar steps precisely, every time they are executed and always record detailed results
- *Increases Test Coverage*: Tests complex scenarios across configurations

### Automation Tools
**UI / End-to-End** 
* **Selenium WebDriver**: Industry standard. Java, Python, C#, JS. All major browsers.
* **Cypress**: Modern JavaScript E2E. Fast, great developer experience, built-in debugging.
* **Playwright (Microsoft)**: Cross-browser (Chrome, Firefox, Safari, Edge). 
* **Appium**: Cross-platform mobile automation for iOS and Android.

**Language-Independent (No-Code / Low-Code)** 
* **`Katalon` Studio**: GUI-driven with record/playback and built-in keywords. Scripting (Groovy).
* **`TestComplete`**: GUI-based with optional scripting. Enterprise tool.

**API Testing** 
* **Postman / Newman**: GUI for API testing; Newman runs collections in CI/CD pipelines.
* **REST Assured (Java)**: Fluent DSL for REST API testing in Java.
* **Karate DSL**: Combines API and UI testing in a single framework.

**CI/CD Integration** 
* **Jenkins**: Open-source automation server. Most widely used. Runs test suites on every commit.
* **GitHub Actions**: Built-in CI/CD for GitHub repositories. Free for open source. YAML-based pipelines.
* **GitLab CI/CD**: Integrated pipeline system for GitLab.
* **Azure DevOps, `CircleCI`, `TeamCity`**: Enterprise alternatives.

##### Modern Trends in Test Automation
- **AI-Powered Self-Healing Tests**: Tools like `Testim` and `Mabl` automatically update tests when the UI changes, reducing maintenance overhead.
- **Shift-Left Testing**: Automation starts in development, not in QA, where developers write tests as they code.
- **Cloud-Based Testing**: `BrowserStack`, Sauce Labs, `LambdaTest` provide thousands of browser/device combinations on demand.
- **Snapshot Testing**: Tools like Jest and Cypress capture UI states for automatic visual comparison on future runs.
- **Continuous Testing**: Testing at every stage of the CI/CD pipeline, not just at the end.

##### Fuzz Testing, Bug Bashes, and Beta Testing
**Fuzz Testing (Random Automation)**
Automatically generates random, unexpected, or malformed inputs to discover crashes and security vulnerabilities that structured tests miss.
* Tools: **AFL++**, **libFuzzer**, _OWASP ZAP Fuzzer_.
* Best targets: File upload endpoints, form inputs, API parsers, protocol implementations.

Types: 
- Random Input Data Generation (e.g., GenerateData) 
- Random Sequence of Data Input (Stochastic Testing) 
- Random Data from Databases 

**Bug Bashes**
Time-boxed team-wide testing event (2–4 hours). All roles participate. Diverse perspectives find diverse bugs. Best practice before major releases.

**Beta Testing**
Real external users test in production-like conditions before public launch. Closed beta (invited users) or Open beta (any user). Uses crash reporting tools: _Firebase Crashlytics_, _Sentry_, _Bugsnag_.

# Test Planning Fundamentals
The responsibility of creating the complete test plan for a project lies with the test manager.
- the entire project’s testing schedule and approach. 
- A good test plan will help to efficiently communicate and document the test effort with well constructed test plans, test cases, and test reports.

**Goals** 
* The main purpose of testing is to evaluate the effectiveness and efficiency of software.
* The goal is to reduce undetected errors in the system or software.

**Challenges and Solutions** 
* Achieving defect-free software is impossible, so high-quality testing is essential.
* Solutions include:
	+ Upgrading the effectiveness of test cases.
	+ Developing automatic software testing tools.

**Outcome** 
* Well-constructed test plans, test cases, and test reports help testers communicate and document test activities effectively.

##### Test Phases
To plan the test phases, the test team first analyzes the chosen development model and decides whether particular phases or stages of testing should be performed over the course of the project.
- Test planning is also one of the test phases.

**Testing Phase Criteria** 
Two important concepts connected with the test phases are the
- *entrance* and
- *exit criteria*. 
Each phase must have both.

The tests to be carried out are also planned during the test phase. These involve:
- *Unit Tests*: Deal with small units or modules of software. 
- *Integration Tests*: Deal with several units or modules that combine to form a subsystem. 
- *System Tests*: Deal with testing the entire software system. 

##### Test Strategy
A document that describes the approach that the test team adopts to test the software, both overall and for each phase. 
- Decisions: Tools development, purchase, or outsourcing

**Resource Requirements** 
Is the activity of deciding the requirements to accomplish the testing strategy. 
Resource requirements include:
- *People*: Number, experience, expertise; should they be full-time, part-time, contract, and so on.
- *Equipment*:  Computers, test hardware, printers, tools, and so on.
- *Office* and Lab Space: Location, size/area, arrangement. 
- *Software*: Word processors, databases, custom tools. What needs to be purchased and what needs to be written.
- *Outsource Companies*: Will they be employed? What will be the basis for choosing them? How much will they cost?

##### Test Cases
A document that describes a set of data inputs and operating conditions required to run a test, together with the expected results of the run. 
Example: Scenario: File Upload and Processing in a Web Application

| Case No. | Test Name                  | Description                                          | Expected Results                                                            | Pass/Fail |
| -------- | -------------------------- | ---------------------------------------------------- | --------------------------------------------------------------------------- | --------- |
| 1        | Upload Valid PDF File      | Tests uploading a valid PDF file (under 10MB).       | File uploads successfully, and the extracted name is displayed.             |           |
| 2        | Upload Invalid File Format | Tests uploading a non-PDF file (e.g., .jpg, .docx).  | System displays an error message: "Invalid file format."                    |           |
| 3        | Upload Large PDF File      | Tests uploading a PDF file larger than 10MB.         | System displays an error message: "File size exceeds the 10MB limit."       |           |
| 4        | Extract File Name          | Tests extracting the file name from an uploaded PDF. | The extracted file name matches the actual uploaded file name.              |           |
| 5        | Submit Form Without File   | Tests form submission without selecting a file.      | System displays an error message: "Please upload a file before submission." |           |

**Bug Reporting** 
The process of describing the problems found during the execution of the test case.
**Goal**: Track bugs from discovery to resolution

**Metrics and Statistics** 
*Purpose*: Measure progress and success
Examples:
- Bugs found daily
- Bugs by severity
- Bugs per feature
*Benefits*: Guide testing, set goals, improve process

# CH 10? Software Quality
Five Views of Software Quality
- Transcendental view
- User view
- Manufacturing view
- Product view
- Value-based view

**Transcendental view** 
- Quality is something that can be recognized through experience, but not defined in some tractable form.
- A good quality object stands out, and it is easily recognized.

**User view** 
- Quality concerns the extent to which a product meets user needs and expectations.
- A product is of good quality if it satisfies a large number of users.
- This view may encompass many subject elements, such as usability, reliability, and efficiency.
- *measurement* 
	- ratio of # of passed test cases to the total number of test cases designed to verify the functionalities.
	- **Gilb’s technique** 
		- The quality concept is broken down into component parts until each can be stated in terms of directly measurable qualities
		- e.g. Usability can be broken down into Learnability, Understandability, Operability


**Manufacturing view** 
Does a product satisfy the requirements?
- Any deviation from the requirements is seen as reducing the quality of the product.
The concept of process plays a key role.
"Conformance to requirements leads to uniformity in products." - some argue this doesn't mean "quality".
Product quality can be incrementally improved by improving the process.
The CMM and ISO 9001 models are based on the manufacturing view.
*measurement* - defect count and rework cost. 
- Defect count: The total number of defects detected during development and operation.
- Rework cost: How much does it cost to fix the known defects?

**Product view** 
*Hypothesis*: If a product is manufactured with good internal properties, then it will have good external properties.
e.g. Modularity enables testability.

**Value-based view** 
This represents the merger of two concepts: *excellence* and *worth*.
Quality is a measure of excellence, and value is a measure of worth.
*Central idea* - How much a customer is willing to pay for a certain level of quality.
- Quality is meaningless if a product does not make economic sense.
- The value-based view makes a trade-off between cost and quality.

### McCall’s Quality Factors and Criteria
**Quality Factors** 
A *quality factor* represents the behavioral characteristic of a system.
- Examples: correctness, reliability, efficiency, Integrity, Usability, maintainability, testability, flexibility, portability, Reusability, Interoperability

The 11 quality factors defined under *quality factor* have been grouped into three broad categories:
- **Product operation** - correctness, reliability, efficiency, Integrity, Usability
- **Product revision** - maintainability, testability, flexibility
- **Product transition** - portability, Reusability, Interoperability

**Quality Criteria** 
A quality criterion is an attribute of a quality factor that is related to software development.
Example: 
- Modularity is an attribute of the architecture of a software system.
- A highly modular software allows designers to put cohesive components in one module, thereby increasing the maintainability of the system.

McCall's quality criteria, lower-level attributes that contribute to the higher-level quality factors:
- **Access Audit:** Ease with which the software and data can be checked for compliance with standards.
- **Accuracy:** Precision of computations and output.
- **Completeness:** Degree to which full implementation of required functionalities has been achieved.
- **Communicativeness:** Ease with which inputs and outputs can be assimilated.
- **Conciseness:** Compactness of the source code.
- **Consistency:** Uniformity of design and documentation.
- **Data Commonality:** The degree to which common data definitions and formats are used.
- **Error Tolerance:** The degree to which the software operates correctly despite invalid inputs or errors.
- **Execution Efficiency:** Run-time efficiency of the software.
- **Expandability:** Degree to which storage requirements or software functions can be expanded.
- **Generality:** Broadness of the application functions.
- **Hardware Independence:** Degree to which a software is dependent on the underlying hardware.
- **Instrumentation:** Degree to which the program provides for the identification of errors.
- **Modularity:** Provision of highly independent modules.
- **Operability:** Ease of operation of the software.
- **Security:** Extent to which the software controls unauthorized access.
- **Self-documentation:** Extent to which the source code provides explanations for its operation.
- **Simplicity:** Ease with which the software can be understood.
- **Software Efficiency:** Run-time storage requirements of the software.
- **Traceability:** Ability to link software components to requirements.
- **Training:** Ease with which new users can use the system.

*Relationship Between Quality Factors and Quality Criteria* 
Each quality factor is positively influenced by a set of quality criteria, and the same quality criterion impacts a number of quality factors.
- Example: Simplicity impacts reliability, usability, and testability.

If an effort is made to improve one quality factor, another quality factor may be degraded.
- Portable code may be less efficient.

Some quality factors positively impact others. 
- An effort to improve the correctness of a system will increase its reliability.

##### The ISO 9126 Quality Characteristics

The ISO 9126 standard (now replaced by ISO/IEC 25010:2011) defines six main software quality characteristics, each with several sub-characteristics:

**1. Functionality:** The presence and appropriateness of functions for specified tasks and their properties.
- Suitability, Accurateness (or Accuracy), Interoperability, Compliance, Security
**2. Reliability:** The software's capability to maintain a specified level of performance under stated conditions for a stated period.
- Maturity, Fault tolerance, Recoverability
**3. Usability:** The effort needed for use by an implied set of users and their individual assessment of such use.
- Understandability, Learnability, Operability, Attractiveness
**4. Efficiency:** The relationship between the software's performance level and the amount of resources used.
- Time behavior, Resource behavior
**5. Maintainability:** The effort needed to make specified modifications and identify and fix faults.
- Analyzability, Changeability, Stability, Testability
**6. Portability:** The software's ability to be transferred from one environment to another.
- Adaptability, `Installability`, Co-existence, Replaceability

**McCall’s quality model vs. ISO 9126 model** 
What is called quality factor in McCall’s model is called a quality sub-characteristic in the ISO 9126 model.

*Differences*: 
1. **Focus:** ISO 9126 model focuses on user-visible characteristics, while McCall's model considers both internal and external qualities.
2. **Relationship between criteria and factors:** In McCall's model, one quality criterion can impact multiple quality factors. In ISO 9126, one sub-characteristic impacts exactly one quality characteristic.
3. **Level of detail:** McCall's high-level quality factors (e.g. testability) are considered low-level sub-characteristics in ISO 9126 (e.g. maintainability).

**The ISO 9000:2000 Software Quality Standard** - i didn't feel like reading this, sorry 

# Maturity Models
### Capability Maturity Model (CMM)
While awarding a contract, the customer needs to gain confidence that an organization is capable of delivering the desired product.
In the CMM model, the maturity level of an organization tells us to what extent an organization can produce low cost, high quality software.
Having known the current maturity level, an organization can work to reach the next higher level.

There are *five maturity levels* in the CMM model.
1. **Initial:** Processes are unpredictable, poorly controlled, and reactive. Success often depends on individual heroics rather than established procedures.
2. **Repeatable:** Basic project management processes are established and practices are documented and repeatable for similar projects. - QA, config. mgt..
3. **Defined:** Processes are standardized, documented, and integrated across the organization. Projects use tailored versions of these standard processes. - peer review, training, Organizational process focus and definition
4. **Managed:** Quantitative objectives are established for both process and product quality, and these are continually measured and controlled. - SQM, Qualitative process mgt.
5. **Optimizing:** The organization focuses on continuous process improvement through incremental and innovative technological improvements. - process change mgt., defect prevention

The key practices in every key process area are organized into five categories called common features.
The five categories of *common features* areas follows.
- Commitment to perform
- Ability to perform
- Activities performed
- Measurement and analysis
- Verifying implementation

*Application of the CMM* 
For an organization to be at a certain level of maturity, all the goals of all the KPAs at that level and all preceding levels too, must be met.
The SEI developed the Capability Maturity Model-Based Assessment Internal Process Improvement (CBA-IPI) to assist organizations for self-assessment.
The SEI developed the CMM Appraisal Framework (CAF) to provide a mechanism for formal evaluation of organizations.

### Test Process Improvement (TPI)
A test process is a certain way of performing activities related to defect detection.
A few such activities are as follows
- Identifying test goals.
- Preparing a test plan.
- Identifying different kinds of tests.
- Hiring test personnel.
- Designing test cases.
- Setting up test benches.
- Procuring test tools.
- Assigning test cases to test engineers.
- Prioritizing test cases for execution.
- Organizing the execution of test cases into multiple test cycles.

**A simple test process for system-level testing** 
```
Categorize the features of a system into k groups.
Design N_i test cases for feature category i, for 1 ≤i ≤ k. These N_i test cases are denoted by the set T_i.
Run T_1U … U T_k to detect defects.
Run T_1U … U T_k each defect fix until no more defects are found, or it is time to release the system.
```
Deficiencies in the above simple process.
- Test tools have not been used.
- Test cases have not been prioritized.
- The entire test suite has been executed in each test cycle.

Therefore, it is important to improve test processes by following a defined model.

A test process needs to be improved for three reasons.
- **Quality**: A better test process should give more insights into the quality characteristics of a system being tested.
- **Lead Time**: A better test process saves testing time.
	- One can prioritize test cases so that difficult-to-fix defects to gain time.
- **Cost**: A better test process is expected to be carried out with a lower cost.

An intuitive approach to improving a test process is as follows:
- Step 1: Determine an area for improvement.
- Step 2: Evaluate the current status of the test process.
- Step 3: Identify the next desired state and the means.
- Step 4: Implement the necessary changes to the process.
The above steps are straightforward, but their implementation is not.

The TPI model supports gradual process improvement.
- The current status of a test process is evaluated from different viewpoints, known as key areas and 20 key areas have been identified.
- The status of a test process w.r.t. a key area is represented in terms of one of four levels of maturity - A, B, C, and D.

*The 20 key areas are as follows*:
- Test strategy
- Life-cycle model
- Moment of involvement
- Planning and estimating
- Test specification technique
- Static test technique
- Metrics
- Test tools
- Test environment
- Office environment
- Commitment and motivation
- Test functions and training
- Scope of methodology
- Communication
- Reporting
- Defect management
- Test process management
- Evaluation
- Low-level testing

**Maturity levels of test processes** 
The Test Maturity Matrix shows that the overall maturity of a test process can be represented on a scale of 1-13.
The 13 scales of maturity of a test process are classified into three distinct segments as follows.
- **Controlled** (1-5): All component activities are planned and executed in phases according to the plan.
- **Efficient** (6-10): All the key areas, except Evaluation, are raised to at least B level with some being at C.
- **Optimizing** (11-13): All the key areas have reached their respective highest maturity levels.
	- Optimizing a test process means performing testing tasks in the best possible manner from the standpoint of quality, time, and cost.

The TMM framework describes an evolutionary path of test process maturity in five levels, or stages.
- Each stage is characterized by the concepts of
	- maturity goals
	- supporting maturity goals, and
	- activities, tasks, and responsibilities (ATRs)

1. **Initial:** Testing is a chaotic and unmanaged activity. There are no defined test processes, and testing is often performed ad-hoc *after* development is complete.
	- no maturity goals, 
2. **Phase Definition:** Testing is defined as a phase within the software development lifecycle, but it's often still performed late in the process. Basic test planning and execution begin.
	- Develop testing and debugging goals.
	- Initiate a test planning process.
	- Institutionalize basic testing techniques and methods.
3. **Integration:** Testing is integrated into the software lifecycle, moving beyond just a single phase. Test activities are planned and designed earlier, and there's a focus on test techniques and methods.
	- Establish a software test group.
	- Establish a technical training program.
	- Integrate testing into the software lifecycle.
	- Control and monitor the testing process.
4. **Management and Measurement:** Testing becomes a well-defined and managed process. Test metrics are collected and analyzed, and there's a focus on quality goals and defect prevention.
	- Establish an organization-wide review program.
	- Establish a test management program.
	- Evaluate software quality.
5. **Optimization/Prevention:** The testing process is continuously improved through defect prevention and process optimization. There's a strong emphasis on early testing, automated testing, and continuous feedback to improve development.
	- Application of process data for defect prevention
	- Statistical quality control
	- Test process optimization

For an organization to reach a certain level, the corresponding maturity goals must be met by the organization.
- Maturity goals are supported by maturity subgoals.
- Maturity subgoals are achieved by means of ATRs.
- ATRs address issues concerning implementation of activities and tasks.
- ATRs also address how an organization can adapt its practices so that it can move in-line with the TMM model.
- ATRs are refined into “views” from the perspectives of three groups:
	- Managers
	- Developers and test engineers
	- Customers (user/client).
