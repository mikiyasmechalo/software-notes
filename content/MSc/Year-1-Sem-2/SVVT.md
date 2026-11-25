---
teacher: Dr. Girma
full name: Software Verification Validation and Testing
---
# CH 1: Intro to ST
**What is Software Testing?** 
A systematic process of evaluating a software application or system to:
- identify bugs
- ensure requirements are met
- verify it satisfies user expectations

It may be:
- *Positive Testing*: operate the app normally and see if it behaves normally using variety of legal test data including boundary values to see if it fails.
- *Negative Testing*: Test for abnormal operations with abnormal data to see if it crashes.
- A good tester is one who is successful in making the system fail.

**Key testing Activities**:
- *Planning*: Defining the scope, objectives, approach, resources, and schedule.
- *Design*: Creating test cases, test data, and test scripts.
- *Execution*: Running tests and comparing actual results to expected results.
- *Analysis*: Evaluating test results, identifying root causes of defects.
- *Reporting*: Documenting and communicating test results and findings

**Goals of Testing** 
- *Defect Detection*: Finding errors before the software is released.
- *Quality Assurance*: Ensuring the software meets defined quality standards.
- *Risk Reduction*: Minimizing the risk of failures in the production environment.
- *Verification and Validation* (V&V): Confirming that the software is built correctly and meets user needs.
- *Confidence Building*: Providing confidence that the software is reliable and performs as intended.

Testing is NOT: 
- Haphazard clicking.
- Fixing bugs.
- One time activity.

### Principles of Testing
These fundamental principles guide effective testing:
1. *Testing shows the presence of defects*, not their absence. Even extensive testing cannot guarantee a bug-free system.
2. *Exhaustive testing is impossible*. There are too many possible inputs, combinations, and execution paths to test everything.
3. *Early testing* saves time and money. The earlier defects are found, the cheaper they are to fix.
4. *Defects cluster together*. A small number of modules often contain the majority of defects.
5. *Pesticide paradox*. Running the same tests repeatedly will eventually stop finding new bugs. Tests need to be updated and varied. (law of diminishing returns)
6. *Testing is context-dependent*. The best testing approach depends on the specific software, project, and risks.
7. *Absence-of-errors is a fallacy*. Just because no defects are found doesn't mean the software is usable or meets user needs.

### Error, Fault, Failure: The Defect Chain
- **Error** - root cause: A human mistake made during the software development process (coding error, misunderstood requirements).
- **Fault** (Defect/Bug) - the problem: The manifestation of an error within the software (e.g., incorrect code, a missing requirement).
- **Failure**: An observable deviation of the software from its expected behavior. It's the consequence of a fault.
> i.e. Error -> Fault -> Failure

### Testing Vs. Debugging
1. **Testing**: finding defects by executing the software and observing its behavior.
	- who? often independent testers,
	- how? planned, systematic and documented
	- output? defect reports, test results
2. **Debugging**: analyzing and fixing the underlying cause of defects (the faults) found during testing.
	- who? developers
	- how? iterative, less structured
	- output? corrected code, updated system

##### Sources of Software Problems
Requirements Problems:
- Ambiguous, incomplete, inconsistent, or incorrect requirements.
- Frequently changing requirements.
- Lack of user input during requirements gathering.

Design Flaws:
- Poorly designed architecture or algorithms.
- Inadequate consideration of error handling or security.
- Lack of modularity or maintainability.

Coding Errors:
- Syntax errors (caught by compilers).
- Logic errors (incorrect algorithms or conditions).
- Typos.
- Incorrect use of libraries or APIs.
- Memory leaks or resource management issues

Testing Deficiencies:
- Inadequate test coverage.
- Incorrect or incomplete test cases.
- Poor test execution or reporting.

Human Factors:
- Lack of communication or collaboration.
- Insufficient training or experience.
- Time pressure and unrealistic deadlines.
- Stress and fatigue.

**Adverse Effects of Faulty Software** 
Software defects can have a wide range of negative consequences:
1. *Financial*: Lost revenue, increased development costs, fines, lawsuits.
2. *Reputational*: Damaged brand image, loss of customer trust.
3. *Operational*: Disruptions to business processes, reduced productivity.
4. *Safety*: In safety-critical systems (medical, aviation), defects can lead to injury or death.
5. *Security*: Vulnerabilities can be exploited by attackers, leading to data breaches or system compromise.
6. *User Dissatisfaction*: Frustration, wasted time, and reduced user adoption.

### Testing Models
A. **Traditional (waterfall)** 
- testing is a separate phase that happens after development
- *Disadvantage*: slate defect detection, limited feedback, inflexible to changes

B. **V-model** 
- each development phase has a testing attached to it.
- test planning and design start early.
- *Advantages*: early defect detection, better test integration, clearer traceability.

C. **Agile**
- Testing integrated throughout development. often through sprints.
- close collaboration between developers and testers.
- continuous testing and feedback.
- Test-Driven Dev. (TDD) and Behavior-Driven Dev. (BDD) are common practices
- *Advantages*: Highly adaptable to change, faster feedback, improved communication, higher quality.

### Software Testing Life Cycle (STLC)
The STLC is a sequence of activities performed during the testing process to ensure software quality. 
Typical STLC Phases:
1. *Requirements Analysis*: Understanding the requirements and identifying testable aspects.
2. *Test Planning*: Defining the scope, objectives, approach, resources, and schedule. Creating a test plan document.
3. *Test Case Development*: Designing and documenting test cases based on the requirements and design.
4. *Test Environment Setup*: Preparing the necessary hardware, software, and data for testing.
5. *Test Execution*: Running the test cases and recording the results (pass/fail, defects).
6. *Test Cycle Closure*: Analyzing results, preparing a summary report, and finalizing the testing activities.

**Economics of Testing: Cost vs. Benefit** 
- *Cost of Defects*: The cost of fixing a defect increases exponentially as it progresses through the SDLC. 
- *Early Testing is Key*: Investing in early testing activities (e.g., requirements reviews, static analysis, unit testing) is a cost-effective strategy.

*Return on Investment (ROI)*: Effective testing provides a significant ROI by:
- Reducing development costs (less rework).
- Improving software quality (fewer defects).
- Increasing customer satisfaction (reliable software).
- Minimizing risks (financial, reputational, safety).


### Essential Testing Terminologies
1. **Test Basis**: Source of info for test cases (e.g., req docs, design specs).
2. **Test Condition**: Specific aspect of *test basis* relevant for testing. (e.g. a req, a function)
3. **Test Case**: Detailed instructions for executing a test. 
4. **Test Suite**: Collection of related test cases.
5. **Test Script**: Automated test case written in a programming lang.
6. **Test Data**: Input data for test cases.
7. **Test Environment**: Setup for testing (hardware, software, etc.).
8. **Test Oracle**: Reliable source for expected results (e.g., req doc, previous version).
9. **Test Coverage**: Measure of how thoroughly testing exercises software.
10. **Verification**: Checking if software meets its specs.
11. **Validation**: Checking if software meets user needs.


# CH 2: Software Quality and Management
### What is Quality?
- Conformance to requirements
- Fitness for use
- Meets explicit and implicit stakeholder expectations

Software-Specific Challenges:
* Intangibility, evolving requirements, and conflicting stakeholder priorities.

**Software Quality**: Encompasses not just the absence of defects, but also factors like:
* *Functionality*: Does it do what it's supposed to do?
* *Reliability*: Does it work consistently without failures?
* *Usability*: Is it easy to learn and use?
* *Efficiency*: Does it use resources (time, memory) effectively?
* *Maintainability*: Is it easy to modify and fix?
* *Portability*: Can it be easily transferred to different environments?

**Quality software** - reasonably bug or defect free, is delivered in time and within the specified budget, meets the requirements and/or expectations, and is maintainable.
- Software that performs all functions as specified in the SRS document, but has an almost unusable user interface cannot be considered as a quality product.
- Software which does everything that users want, but has an almost incomprehensible and unmaintainable code cannot be considered as a quality product.

`Quality SW = reasonably bug free + Time + budget + maintainable + meet specification` 

##### ISO/IEC 25010 (formerly ISO/IEC 9126)
1. *Functional Suitability*: Functional completeness, correctness, and appropriateness.
2. *Performance Efficiency*: Time behavior, resource utilization, capacity.
3. *Compatibility*: Co-existence, interoperability.
4. *Usability*: Appropriateness recognizability, learnability, operability, user error protection, user interface aesthetics, accessibility.
5. *Reliability*: Maturity, availability, fault tolerance, recoverability.
6. *Security*: Confidentiality, integrity, non-repudiation, accountability, authenticity.
7. *Maintainability*: Modularity, reusability, analyzability, modifiability, testability.
8. *Portability*: Adaptability, install-ability, replaceability.

### Software Quality Management Systems
"a management process that aims to develop and manage the quality of software in such a way so as to best ensure that the product meets the quality standards expected by the customer, regulators and developers, if any" 

QMS - A formalized system that documents processes, procedures, and responsibilities for achieving quality policies and objectives. It's a framework for managing quality.

Key Components of a QMS:
- *Quality Policy*: A statement of the organization's overall quality goals.
- *Quality Manual*: A document that describes the QMS. Outlines the organizational structure, responsibilities, and procedures for implementing the QMS.
- *Procedures*: Detailed instructions for performing specific tasks.
- *Work Instructions*: Even more detailed instructions, often for specific jobs.
- *Records*: Evidence that processes are being followed (e.g., test results, audit reports).

### Quality System Activities and Evolution
Activities of Quality System:
- Auditing of projects
- Development of:
	- standards, procedures, and guidelines, etc.
- Production of reports for the top management 
	- summarizing the effectiveness of the quality system in the organization.
- Review of the quality system itself.

**Quality systems** has 4 stages of evolution
1. Inspection
2. Quality Control (QC)
3. Quality Assurance (QA)
4. Total Quality Management (TQM)

**Quality Control** 
- *Focus*: product-oriented, identifies defects in the output.
- *Activities*: inspection, testing and measuring to test if requirements are met.
- *Reactive*: QC happens after a product is built.
- e.g. cross browser testing for UI.

**Quality Assurance** 
- *Focus*: process oriented, ensures processes are effective and lead to high-quality outputs.
- *Activities*: define processes, conduct audits, provide training, implement preventative measures.
- *Proactive*: QA aims to prevent defects from occurring in the first place.
- e.g. coding standards and code reviews.

**Total Quality Management** 
- A management philosophy that emphasizes *continuous improvement* in all aspects of an organization, with a strong focus on customer satisfaction.
*Principles*:
- `Customer Focus`: Understanding and meeting customer needs.
- `Continuous Improvement`: Constantly striving to improve processes and products.
- `Employee Involvement`: Empowering employees to participate in quality improvement efforts.
- `Process-Oriented`: Focusing on improving processes rather than just inspecting outputs.
- `Data-Driven Decision Making`: Using data to track progress and make informed decisions.
- `Leadership Commitment`: Strong leadership support for quality initiatives.

**Business Process Re-engineering (BPR)** 
- The fundamental rethinking and radical redesign of business processes to achieve dramatic improvements in critical, contemporary measures of performance, such as cost, quality, service, and speed.
- It is about process improvement.

##### ISO 9000
 It specifies requirements for a QMS that an organization can use to demonstrate its ability to consistently provide products and services that meet customer and regulatory requirements.
 ISO 9000 registration process consists of several stages.
1. Application stage:
	- Applies to a registrar for registration.
2. Pre-assessment:
	- the registrar makes a rough assessment of the organization.
3. Compliance audit: the registrar checks whether the suggestions made by it during review have been complied.

**Significance** 
- Improved Customer Satisfaction: Demonstrates a commitment to quality.
- Enhanced Credibility: Provides assurance to customers and stakeholders.
- Increased Efficiency: Improves processes and reduces waste.
- Better Risk Management: Helps identify and mitigate risks.
- Competitive Advantage: Can be a requirement for doing business with certain organizations.
- Continuous Improvement: Promotes a culture of continuous improvement.

**ISO 9001** - Focus - Process quality
**ISO/IEC 25010** - Focus - Product quality
- ISO 9001 provides a framework for managing quality (the processes).
- ISO/IEC 25010 defines the attributes of a high-quality software product.



# CH 3: Testing Fundamentals
* Levels
	* Unit testing
	* Integration testing
	* System testing
	* User Acceptance testing (UAT)
- Functional 
	* Software Requirements
	* What software does
- Non-Functional
	* how the system behaves
	* User expectations

### Software Verification and Validation
What is V&V? A comprehensive approach to ensuring software quality, encompassing two key activities.
- *Verification*: "Are we building the product right?" (Conformance to specifications). Often done through reviews, inspections & walkthroughs. Static analysis
- *Validation*: "Are we building the right product?" (Meets user needs). Involves executing the software.
- *Mnemonic*: Verification = Voice of the Developer. Validation = Voice of the Customer.
- *V & V benefits*: Early Defect Detection, Improved Software Quality, Customer Satisfaction, and Reduced Costs.

### Static vs. Dynamic Testing
**1. Static Testing:** 
- Examining work products (requirements, design, code, test plans) without executing the code. It's about prevention.
- Techniques:
	- *Reviews*: Informal reviews, walkthroughs, technical reviews, inspections.
	- *Static Analysis*: Using automated tools to analyze code for potential defects, coding standard violations, and security vulnerabilities.
- *Benefits*: Early defect detection, improved communication, reduced development time and cost.

**2. Dynamic Testing:** 
- Executing the software to find defects. It's about detection.
- *Techniques*: Unit testing, integration testing, system testing, acceptance testing, performance testing, security testing, etc.
- *Benefits*: Finds defects that cannot be found through static testing (e.g., runtime errors, performance issues), verifies that the software actually works as expected

##### Types of Manual Testing
*Manual testing* - e.g. white box testing, black box testing and grey box testing
*Automated testing* involves creation of test scripts or codes that automate the execution of test cases using automated tools. 

Automation tools can assist in test case generation, data handling, test execution, and result analysis, enhancing the overall testing process and efficiency.

**Exploratory Testing** 
- *Description*: An unscripted approach where testers simultaneously learn about the system, design tests, and execute them. Relies on the tester's skill, intuition, and experience.
- *Benefits*: Can find defects that might be missed by scripted tests, good for finding usability issues and exploring edge cases.
- *When to Use*: When requirements are unclear or incomplete, when time is limited, or when you want to explore the system from a user's perspective.

**Usability Testing**:
- *Description*: Evaluating how easy the software is to use by observing real users interaction.
- *Benefits*: Identifies usability problems that can make the software difficult or frustrating to use, even if it is functionally correct.
- *When to Use*: Throughout the development process, mainly during design and prototyping.

**Ad-hoc Testing** 
- No specific approach.
- Part of Exploratory Testing.
- Performed by a person familiar with the software

*Other Manual Testing Techniques*: Many of the dynamic testing techniques discussed later (e.g., black-box testing, white-box testing) can be performed manually.

- Smoke testing vs Sanity testing Smoke Testing: Broad checks of critical functionality after a build. 
	 - Sanity Testing: Focused checks on specific functionalities after changes.
- Gorilla testing vs monkey testing: Gorilla Testing: Focused, intensive testing of a specific module to find defects. 
	- Monkey Testing: Random and unpredictable testing to catch unexpected bugs.

### Functional vs. Non-functional Testing
**Functional Testing**:
- Verifying that the software functions correctly according to its specifications. (what the software does.)
- *Techniques*: Black-box testing techniques (e.g., equivalence partitioning, boundary value analysis, decision table testing, use case testing).
- *Example*: Testing that a user can log in with a valid username and password, add items to a shopping cart, and complete a purchase.

**Non-Functional Testing**: 
- *Definition*: Evaluating the quality characteristics of the software, such as performance, security, usability, reliability, and scalability. (how well the software performs.)
- *Techniques*: Performance testing (load, stress, endurance), security testing (vulnerability scanning, penetration testing), usability testing, accessibility testing, etc.
- *Example*: Testing how quickly a website loads, how many concurrent users it can handle, how secure it is against attacks, and how easy it is to use.

### Levels of Testing 
**Unit Testing**
* Description: Testing individual components (units) of software in isolation. e.g. a fun., a class
* Focus: Verifying each unit works correctly according to its specifications.
* Who: Developers typically perform unit testing.
* Techniques: White-box and black-box testing.
* Example: Testing a function that calculates the factorial of a number.

*Note*: Unit tests are easier to write and quicker to execute. The time and effort to implement and maintain the tests increases from unit testing to acceptance testing. 

**Integration Testing** 
* Description: Verifying interactions between system components.
* Focus: Detecting interface defects.
* Who: Developers and/or testers.
* Techniques: Black-box and white-box testing.
* Example: Testing how a login module interacts with a user database module.

**System Testing** 
* Description: Testing the complete system to ensure it meets all requirements.
* Focus: End-to-end testing in a realistic environment.
* Who: Independent testers (not developers).
* Techniques: Primarily black-box testing.
* Example: Testing an e-commerce website's entire functionality.

**Acceptance Testing**: Performed by customers.


# CH 4: Test Management and Documentation
Documents are created to ensure that all stakeholders, including developers, testers, and users, have a clear understanding of the software application's features and functionalities.

Testing documentation is the documentation of artifacts that are created during or before the testing of a software application.

**Importance of Documentation**:
- *Communication*: Provides a clear and consistent record of information for all stakeholders.
- *Traceability*: Links requirements, design, code, tests, and defects.
- *Maintainability*: Makes it easier to understand, modify, and maintain the software and testing artifacts.
- *Knowledge Transfer*: Helps new team members understand the project.
- *Auditing and Compliance*: Provides evidence of testing for audits and regulatory comp.
- *Repeatability*: Ensures that testing can be repeated consistently.

### Types Documentation
**PRD (Product Requirement Document)** 
- *What*: Set of Software Requirements
- *Who*: Product Marketing, Sales, Technical Support
- *When*: Planning stage
- *Why*: We need to know what the product is supposed to do

Quality Assurance (QA) role: 
- Participate in reviews 
- Analyze for completeness
- Spot ambiguities 
- Highlight contradictions 
- Provide feedback on features/usability

**FS (Functional Specification)** 
- *What*: software design document;
- *Who*: Engineers, Architects;
- *When*: planning/ design/ coding stage(s);
- *Why*: we need to know how the product will be designed;

**UI Spec (User Interface Specification)** 
- UI Spec is a document that outlines the design and layout of the software application's UI.
- It includes detailed descriptions of the screens, buttons, icons, and other UI elements.
- Created by the design team, which includes UX designers, visual designers, and front-end developers
- Created after the Product Req. have been defined and the FS have been written.

### Test Planning: Test Plans, Test Cases, and Test Suites
##### Test Planning
*Test Plan*: Document detailing scope, approach, resources, and schedule.
- It serves as a blueprint for testing activities, ensuring clarity and direction.
*Test Strategy*: High-level approach to testing.
Example: A test plan may specify testing timelines, while the test strategy outlines testing types.

##### Test Plan
- What: a document describing the scope, approach, resources and schedule of intended testing activities; identifies test items, the features to be tested, the testing tasks, who will do each task and any risks requiring contingency planning;
- Who: QA;
- When: (planning)/design/coding/testing stage(s);
- Why:
	- Divide responsibilities between teams involved; if more than one QA team is involved (i.e., manual/ automation, or English /Localization)
	- Plan for test resources / timelines ; 
	- Plan for test coverage; 
	- Plan for test environment set up, software deployment and configuration models coverage.
QA role: 
- Create and maintain the document;
- Analyze for completeness;
- Have it reviewed and signed by Project Team leads/managers.

**Test Plan Attributes** - objective, scope, test methodology, approach , assumption, risk, mitigation/ contingency plan, role and responsibility, schedule, defect tracking, test environments, entry and exit criteria, test automation, effort estimation, test deliverables, template.

Example: A test plan for a mobile banking app might specify:
- Scope: Testing all features of the app on iOS and Android devices.
- Approach: Black-box testing (functional, usability, security, performance).
- Levels: Integration testing, system testing, acceptance testing.
- Entry Criteria: All unit tests passed, test environment set up.
- Exit Criteria: All critical and major defects fixed, 95% test case pass rate.

**Test reporting** 
Concerned with summarizing information about the testing endeavor, including
- What happened during a period of testing (ex: dates when exit criteria were met)
- Analyzed metrics to support decisions about future actions (ex: the economic benefit of continued testing)

**Good Test Plans** 
a. Developed and Reviewed early
b. Clear, Complete and Specific
c. Specifies tangible deliverables that can be inspected
d. Staff knows what to expect and when to expect it
e. Realistic quality levels for goals
f. Includes time for planning
g. Can be monitored and updated
h. Includes user responsibilities
i. Based on past experience
j. Recognizes learning curves

##### Test Cases
Five required elements of a Test Case:
- *ID* - unique identifier of a test case;
- *Features* to be tested / steps / input values - what you need to do;
- *Expected result* / output values - what you are supposed to get from application;
- *Actual result* - what you really get from application;
- *Pass / Fail*.

Optional elements of a Test Case:
- Title - verbal description indicative of testcase objective;
- Goal / objective - primary verification point of the test case;
- Project / application ID / title - for TC classification / better tracking;
- Functional area - for better TC tracking;
- Bug numbers for Failed test cases - for better error / failure tracking (ISO 9000);
- Positive / Negative class - for test execution planning;
- Manual / Automatable / Automated parameter etc. - for planning purposes;
- Test Environment

Classes:
* Positive and Negative;
* Functional, Non-Functional and UI;
* Implicit verifications and explicit verifications;
* Systematic testing and ad-hoc;

*Example*:
- Test Case ID: TC_Login_001
- Test Case Name: Verify successful login with valid credentials
- Test Objective: Verify that a user can log in with a valid username and password.
- Preconditions: User account exists with username "`testuser`" and password "`password123`".
- Test Steps:
 1. Navigate to the login page.
 2. Enter "`testuser`" in the username field.
 3. Enter "`password123`" in the password field.
 4. Click the "Login" button.
- Test Data: Username: "`testuser`", Password: "`password123`"
- Expected Results: User is logged in and redirected to the home page.
- Postconditions: User is logged in.
- Actual Results: (To be filled in during execution)
- Pass/Fail: (To be filled in during execution)

##### Test Suite
A document specifying a sequence of actions for the execution of multiple test cases.
*Purpose*: To organize test cases into logical groups.
- To put the test cases into an executable order, although individual test cases may have an internal set of steps or procedures. 
Is *typically manual*, if automated, typically referred to as test script (though manual procedures can also be a type of script).

Examples of Test Suite Organization:
- *By Feature*: A test suite for each feature of the software (e.g., "Login Test Suite," "Shopping Cart Test Suite").
- *By Test Level*: A test suite for each level of testing (e.g., "Integration Test Suite," "System Test Suite").
- *By Priority*: A test suite for high-priority tests (e.g., "Smoke Test Suite").
- *By Regression Test*: A test suite including all regression tests.

### Traceability matrix
**Purpose**: Ensure that every software feature is properly documented and tested
Key Stakeholders:
- Who: Engineers, QA Team
- When: During design, coding, and testing stages

Documentation Flow:
- PRD (Product Requirements Document)
	- Defines the product's requirements and features
- FS (Functional Specification)
	- Outlines the system's behavior and functionality
	- Ensures that PRD requirements are met
- Test Documents
	- Test Cases: Documented test scenarios to validate system functionality
	- Test Suites: Collections of related test cases to ensure comprehensive testing

Why: To ensure that:
- Each requirement is covered in the Functional Specification (FS)
- Each requirement is tested thoroughly through Test Cases and Test Suites

*Example* 

| PRD section                                       | FS section                                           | Test case                                                                                                                         | Notes |
| ------------------------------------------------- | ---------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ----- |
| 1.1. Validation of user login<br>credentials.<br> | 4.1. User login<br>validation.                       | 6.1.4. User login with proper credentials.<br>6.1.5. User login with invalid username.<br>6.1.6. User login with invalid password |       |
| 1.2. Validation of credit card <br>information    | 7.2.4. Credit card <br>information <br>verification. | 10.1.1. Valid credit card information input.<br>10.1.2. Invalid credit card number.<br>10.1.3. Invalid credit card name.          |       |

### Risk Analysis in Software Testing
The process of identifying, analyzing, and prioritizing potential risks that could affect the software or the testing process.

**Why is Risk Analysis Important for Testing?** 
- *Focus Testing Efforts* 
- *Resource Allocation* 
- *Test Strategy Selection*: Choose appropriate testing techniques.
- *Contingency Planning*: Develop plans to address potential problems.

**Steps in Risk Analysis** 
* **Risk Identification**: Identify potential risks. This can be done through brainstorming, reviewing past projects, using checklists, and consulting with experts.
Examples of Risks (Product Risks):
- Complex functionality.
- New technology.
- Tight deadlines.
- Lack of skilled resources.
- Unclear or changing requirements

Examples of Risks (Project/Test Risks):
- Test environment not ready on time.
- Test data not available.
- Lack of communication between developers and testers.

* **Risk Assessment**: Analyze each risk to determine its likelihood (probability of occurring) and impact (severity of the consequences).
	- Likelihood: Often rated on a scale (e.g., High, Medium, Low).
	- Impact: Often rated on a scale (e.g., High, Medium, Low).
* **Risk Prioritization**: Prioritize risks based on their likelihood and impact. A common approach is to use a risk matrix.

| Feature<br>        | Likelihood of failure (Eng, QA, Tech Support) | Impact of failure (PM, Tech Support, Sales, QA) | Risk Factor<br> |
| ------------------------- | --------------------------------------------- | ----------------------------------------------- | --------------- |
| 1. Login         | 2                       | 10                       | 20       |
| 2. create database record | 5                       | 7                        | 35       |
| 3. modify database record | 3                       | 6                        | 18       |

**Risk Mitigation**: Develop strategies to reduce the likelihood or impact of high-priority risks.
Examples of Mitigation Strategies:
- More frequent testing of high-risk areas.
- Early prototyping of new features.
- Additional training for team members.
- Developing contingency plans.

**Risk Monitoring**: Track, Control, and Monitor identified risks.
e.g.

| Risk | Likelihood | Impact | Priority | Mitigation Strategy |
| :--- | :--- | :--- | :--- | :--- |
| Complex login module | High | High | High | More frequent testing, code reviews, early prototyping |
| Test environment unavailable | Medium | High | High | Develop a contingency plan. |
| New feature added late | Low | Medium | Medium | Re-prioritize testing, consider reducing scope. |

# CH 5: Test Case Design
The process of creating a set of test cases that adequately cover the software's functionality and requirements.

Why is it Important?
- *Effective Defect Detection*: Well-designed tests are more likely to find important bugs.
- *Efficient Testing*: Avoids redundant testing and focuses on the most critical areas.
- *Test Coverage*: Ensures that all relevant aspects of the software are tested.
- *Traceability*: Connects tests back to requirements, making it clear what is being tested.

Test Case vs Test Data vs Test Oracle

| Feature    | Test Case                   | Test Data                   | Test Oracle                         |
| :------------- | :--------------------------------------------- | :--------------------------------------------- | :---------------------------------------------------------- |
| **Definition** | Set of steps to test a specific feature.    | Input values used to execute a test case.   | Mechanism for determining expected output.         |
| **Purpose**  | Verify functionality and requirements.     | Provide input for software to process.     | Validate if the actual result matches the expected.     |
| **Scope** | Broad, encompassing the entire testing process | Narrow, specific to the input of a test case  | Provides a baseline for comparison and validation.     |
| **Contents**  | Steps, expected results, preconditions.    | Values, files, database entries.        | Specifications, known results, human expertise.       |
| **Example**  | "Verify user login with valid credentials"   | Username: "User123"<br>Password: "password123" | System requirement: Successful login redirects to dashboard |

### Black Box Testing 
- *Definition*: A software testing method that evaluates functionality without knowledge of internal code structure.
- *Common Usage*: Performed in everyday applications, from software to physical products.
- Characteristics:
	- No knowledge of internal code
	- Focus on functionality

**Types** 
- Functional Testing
	- Tests functional requirements/specifications.
	- Example: Smoke Testing, Sanity Testing, Integration Testing, System Testing, Regression Testing, User Acceptance Testing

- Non-Functional Testing 
	- Tests performance and usability aspects.
	- Example: Performance testing, Usability Testing, Compatibility Testing, Stress Testing, Scalability Testing, Load testing 

**Techniques** 
- Equivalence Partitioning
- Boundary Value Analysis
- Decision Table Testing
- State Transition Testing

1. **Equivalence Partitioning (EP)** 
	- Divides the input domain into equivalence classes. 
	- You select one representative value from each class to test.
	- *Test Cases*: You would create three test cases, one from each class.
	Example: The “age” text field accepts only numbers from 18 to 60. There will be three sets of classes or groups. Age input (Valid: 18-60, Invalid: <18, >60)

2. **Boundary Value Analysis (BVA)** 
	- using input variable values at the edges of input ranges.
	- Example: Accepts values 1-100. 
	Test Cases: 
	- Input 0 (Invalid)
	- Input 1 (Valid)
	- Input 100 (Valid)
	- Input 101 (Invalid)

3. **Cause effect graphing /Decision Table** 
	- A “*Cause*” stands for a separate input condition that fetches about an internal change in the system. 
	- An “*Effect*” represents an output condition, a system transformation or a state resulting from a combination of causes.
	- It is a testing technique that aids in choosing test cases that logically relate Causes (inputs) to Effects (outputs) to produce test cases.

	According to Myer Cause & Effect Graphing is done through the following steps:
	- Step - 1: For a module, identify the input conditions (causes) and actions (effect).
	- Step - 2: Develop a cause-effect graph.
	- Step - 3: Transform cause-effect graph into a decision table.
	- Step - 4: Convert decision table rules to test cases. Each column of the decision table represents a test case.

![[Pasted image 20260406104118.png]]

**Example** 1: The “Print message module” is software that read two characters and, depending of their values, messages must be printed.
- The first character must be an “A” or a “B”.
- The second character must be a digit.
1. If the first character is an “A” or “B” and the second character is a digit, the file must be updated.
2. If the first character is incorrect (not an “A” or “B”), the message X must be printed.
3. If the second character is incorrect (not a digit), the message Y must be printed.

Solutions:
Causes:  
- C1: Character in col1 is ‘a’
- C2: Character in col1 is ‘b’
- C3: Character in col2 is a digit

Effects:  
- e1: File is updated if ((C1 OR C2) AND C3)’
- e2: Message X is displayed if (NOT(C1) AND NOT(C2)) OR((NOT(C1 OR C2))
- e3: Message Y is displayed if NOT(C3)
![[Pasted image 20260406104243.png]]

| TC ID   | TC Name                  | Description                                                                                      | Steps                                                                                                | Expected result  |
| :------ | :----------------------- | :----------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------- | :--------------- |
| **TC1** | TC1_FileUpdate Scenorio1 | Validate that system updates the file when first character is A and second character is a digit. | 1. Open the application.<br>2. Enter first character as "A"<br>3. Enter second character as a digit  | File is updated. |
| **TC2** | TC2_FileUpdate Scenario2 | Validate that system updates the file when first character is B and second character is a digit. | 1. Open the application. <br>2. Enter first character as "B"<br>3. Enter second character as a digit | File is updated. |
| ...     |                          |                                                                                                  |                                                                                                      |                  |

4. **State Transitional Diagrams** 
- Identify a finite number of states the model execution goes through
- Create a state transition diagram showing how the model transitions from one state to the other.
- Assess the model accuracy by analyzing the conditions under which a state change occurs.
- *State transition*: A transition between two states of a component or system. 

Example 1: Flight Reservation Login States Transition. In flight reservation login screen, consider you have to enter correct agent  name and password to access the reservation application.

start -> 1st try (incorrect pin)-> 2nd try (incorrect pin) -> 3rd try (incorrect pin) -> acc blocked
                                ↓(correct)                     ↓(correct)                ↓(correct)
                                Access granted           <-                              <-


Advantages
- No technical knowledge required.
- Independent testing and development.
- Effective for large, complex applications.
- Early detection of defects.

Disadvantages
- Limited coverage of internal structures
- Potential for missing edge cases
- Inefficiency in identifying internal errors
- Difficulty in identifying the root cause of defects.

### White Box Testing
*Definition*: A testing technique evaluating the internal structure and code of a program.
- Also Known As: Clear box testing, glass box testing, structural testing.

Key Aspects 
- *Focus*: Examines internal operations to ensure compliance with specifications.
- *Objective*: Verify all internal components have been adequately tested.

Characteristics: 
- Knowledge of internal code
- Focus on code structure and logic

Techniques
- *Code/statement Coverage*: Evaluates the extent to which code is executed.
- *Branch Coverage*: Tests all decision points (true/false).
- *Path Coverage*: Ensures all possible paths through the code are tested.
- *Loop Testing*: Tests loops, including single, nested, and concatenated loops.

##### 1. Statement coverage
- Statement coverage is a white box testing technique, which involves the execution of all the statements at least once in the source code. 
- Through statement coverage we can identify the statements executed and where the code is not executed because of blockage.
- The statement coverage covers only the true conditions. (its main drawback)

The statement coverage is count as per below formula:
$$(\text{Statement coverage} = \text{No of statements Executed}/\text{Total no of statements in the source code} * 100)$$

Example:
```
Read A
Read B
if A>B
  Print “A is greater than B”
else
  Print "B is greater than A"
endif
```
- Set 1: If A =5, B =2
	- No of statements Executed: 5
	- Total no of statements in the source code: 7
	- Statement coverage =$5/7*100 = 71.00\%$ 
- Set 2: If A =2, B =5 \[False-Not supported by Statement coverage\] 
	- No of statements Executed: 6
	- Total no of statements in the source code: 7
	- Statement coverage =$6/7*100 = 85.20 \%$ 

##### 2. Branch/Decision coverage:
- Branch coverage is also known as Decision coverage or all-edges coverage.
- It covers both the true and false conditions unlikely the statement coverage.
- A more in-depth view of the source code than simple statement coverage.

The formula to calculate decision coverage is:
$$\text{Decision Coverage}=(\text{Number of decision outcomes executed}/\text{Total number of decision outcomes})*100\%$$

Example:
```
READ X
READ Y
IF (X > Y)
       PRINT  "X is greater that Y"
ENDIF
To get 100% statement coverage only one test case is not sufficient for this pseudo-code.
```

T-case 1: X=10 Y=5 (FALSE condition of the IF statement is not exercised.)
So the final TEST SET for 100% decision coverage will be:
T-case 1: X=10, Y=5
T-case 2: X=2, Y=10

>*Note*: 100% decision coverage guarantees 100% statement coverage but 100% statement coverage does not guarantee 100% decision coverage.

##### 3. Loop Testing:
Loop testing validates four different classes of loop constructs
- Simple loops
- Nested loops
- Concatenated loops
- Unstructured loops

Testing occurs by varying the loop boundary values
Examples: 
```
for (i = 0; i < MAX_INDEX; i++) ..
while (currentTemp >= MINIMUM_TEMPERATURE) ..
```

**Simple Loop Testing**:
1) Skip the loop entirely - Verifies that the code doesn't crash if the loop never executes (e.g., if a list is empty).
2) Only one pass through the loop - "off-by-one" errors.
3) Two passes through the loop - "off-by-one" errors.
4) m passes through the loop, where m < n. - general logic
5) n –1, n, n + 1 passes through the loop, ‘n’ is the maximum number of allowable passes through the loop. - boundaries
e.g. 
```
def count_up_to(n):
	count = 0
	wile count < n:
		count +=1
	return count
```

| test case | input | expected output |
| --------- | ----- | --------------- |
| 01        | 5     | 5               |
| 02        | 0     | 0               |

**Nested Loop Testing**:
1) Start at the innermost loop; set all other loops to minimum values
2) Conduct simple loop tests for the innermost loop while holding the outer loops at their minimum iteration parameter values; add other tests for out-of-range or excluded values
3) Work outward, conducting tests for the next loop, but keeping all other outer loops at minimum values and other nested loops to “typical” values
4) Continue until all loops have been tested
e.g. 
```
def print_matrix(matrix):
	for row in matrix:
		for value in row:
			print(value,end="")
		print()
```

| test case | input             | expected output |
| --------- | ----------------- | --------------- |
| TC01      | \[\[1,2], \[3,4]] | 1 2 \n 3 4      |
| TC02      | \[\[]]            | no output       |

**Concatenated Loop Testing** 
- For independent loops, use the same approach as for simple loops
- Otherwise, use the approach applied for nested loops

```
def process_numbers(numbers):
	for n in numbers:
		print(n)
	for n in numbers:
		print(n*2)
```

| Test case | Input   | Expected output  |
| --------- | ------- | ---------------- |
| TC01      | \[1, 2] | 1 \n 2 \n 2 \n 4 |
| TC02      | \[]     | no output        |

 **Unstructured Loop Testing**:
- Redesign the code to reflect the use of structured programming practices
- Depending on the resultant design, apply testing for simple loops, nested loops, or concatenated loops 

##### 4. Path coverage
The basis path method enables the test-case designer to derive a logical complexity measure of a procedural design and use this measure as a guide for defining a basis set of execution paths. 
Test cases derived to exercise the basis set are guaranteed to execute every statement in the program at least one time during testing.
Steps:
1) Using the design or code as a foundation, draw a corresponding flow graph
2) Determine the cyclomatic complexity of the resultant flow graph
3) Determine a basis set of linearly independent paths
4) Prepare test cases that will force execution of each path in the basis set

e.g. 
```
INPUT A & B
C=A+B
IF C>100
PRINT "Its done"

END IF
IF A>50
PRINT "Its pending"
END IF
```
![[Pasted image 20260406113426.png]]
Red Line – TestCase_01 = (A=50, B=60)
Blue Line = TestCase_02 = (A=55, B=40)
Orange Line = TestCase_03 = (A=40, B=65)
Green Line = TestCase_04 = (A=30, B=30)
![[Pasted image 20260406113741.png]]

**Path coverage: Independent Paths** 
- Defined as a path through the program from the start node until the end node that introduces at least one new set of processing statements or a new condition (i.e., new nodes)
- Must move along at least one edge that has not been traversed before by a previous path
- Basis set for flow graph above
- Path 1: 0-1-11
- Path 2: 0-1-2-3-4-5-10-1-11
- Path 3: 0-1-2-3-6-8-9-10-1-11
- Path 4: 0-1-2-3-6-7-9-10-1-11
- The number of paths in the basis set is determined by the cyclomatic complexity

**Path coverage: Cyclometric Complexity** 
- Provides a quantitative measure of the logical complexity of a program
- Defines the number of independent paths in the basis set 
- Provides an upper bound for the number of tests that must be conducted to ensure all statements have been executed at least once
- Can be computed three ways
	- The number of regions
	- V(G) = E - N + 2, where E - number of edges and N - number of nodes in graph G
	- V(G) = P + 1, where P is the number of predicate(condition) nodes in the flow graph G
- Results in the following equations for the example flow graph
	- Number of regions = 4
	- V(G) = 14 edges - 12 nodes + 2 = 4
	- V(G) = 3 predicate nodes + 1 = 4

**Note** 
- After determining the independent paths, design test cases for each path
- The minimum number of test cases is equal to the cyclomatic complexity.
- Problem - path testing cannot test all possible combinations of paths through a program. There are an infinite number of possible path combinations in programs with loops

##### White Box Testing: Why
Ensures: 
- All independent paths within a module are exercised.
- Logical decisions are validated for true/false values.
- All loops function correctly.

Discovers: 
- Logical and design errors.
- Typographical and syntax errors

Advantages:
- Thorough examination of code
- Effective for uncovering hidden errors
- Helps optimize code quality

Disadvantages:
- Requires programming knowledge
- Time-consuming for large codebases
- May overlook user experience issues


| BBT                                 | WBT                                                |
| ----------------------------------- | -------------------------------------------------- |
| Knowledge of external behavior only | Knowledge of internal code structure               |
| Focuses on functionality            | Focuses on code execution                          |
| Higher level testing                | Lower level testing                                |
| Conducted by tester                 | Conducted by developers/testers with coding skills |

Tools for White Box Testing
- `Veracode`: Identifies software flaws across multiple languages.
- `EclEmma`: Java code coverage tool for Eclipse.
- `GoogleTest`: C++ testing framework with extensive features.
- `JUnit`: Framework for unit testing in Java.


# CH 6: Software Test Automation Frameworks
Test automation is used to automate repetitive tasks and other testing tasks which are difficult to perform manually. 

**When to automate?** 
- Frequent regression testing
- Repeated test case execution is required
- User Acceptance Tests 
- Faster Feedback to the developers
- Reduce the Human Effort

### Testing Frameworks
A *framework* is a combination of set protocols, rules, standards and guidelines that can be incorporated or followed as a whole.

**Test Automation Framework (TAF):** 
Is scaffolding that is laid to provide an execution environment for the automation test scripts.  
Is a constructive blend of various guidelines, coding standards, concepts, processes, practices, project hierarchies, modularity, reporting mechanism, test data injections etc. to pillar automation testing.

*Advantages* 
- Reusability of code 
- Maximum coverage 
- Recovery scenario 
- Low-cost maintenance 
- Minimal manual intervention 
- Easy Reporting

#### Types of Test Frameworks
##### Linear Scripting Testing Framework 
AKA record and playback testing framework.
Users target a specific program functionality, create test scripts in sequential order and run them individually. 
This process includes capturing all the tests like navigation, inputs, etc., and playing them back repeatedly to conduct the test. 

Pros:
- Better for small projects, faster delivery to customer

Cons:
- No reusability at all. 
- Hard coding the data doesn't allow us to run with multiple data sets. Maintenance is high - It requires a lot of effort to do even small changes.

##### Module Based Testing Framework 
Divides the entire “Application Under Test” into a number of logical and isolated modules, each with a separate and independent test script. 
Consequently, these individual test scripts can be integrated to form a more extensive test script that encompasses several modules.

Pros:
- Easy to reuse and modify

Cons:
- Need to modify test script while changing test data

##### Library Architecture Testing Framework 
The basic fundamental behind the framework is to determine the common steps and group them into functions under a library and call those functions in the test scripts whenever required.

*Example*: For instance, common actions like logging in can be grouped into a single function within a library, allowing any test script that needs to log in to simply call this function instead of repeatedly writing the same code.

Pros:
- Great degree of re-usability like MBFT.

Cons:
- Need to modify test script while changing test data 
- Adding library might complicate to some extent

##### Data Driven Testing Framework 
Unlike MBTF and LATF, Data Driven Testing Framework helps the user segregate the test script logic and the test data from each other.
It lets the user store the test data into an external database or other sources like csv, txt file, xml, etc.. 
The data is conventionally stored in “Key-Value” pairs. Thus, the key can be used to access and populate the data within the test scripts.

*Example*, Consider a login test. Instead of writing separate tests for each user, you could store a list of usernames and passwords in a CSV file. The test script would then read each row from the CSV, using the "username" and "password" keys to attempt a login. This way, the same login test logic is executed multiple times with different data, testing various user credentials without modifying the test script itself.

Pros:
- it considerably reduces the total number of scripts required to cover all the possible combinations of test scenarios. "less code".
- Increases flexibility and maintainability as any change in the test data matrix would not hamper the test script code.

Cons:
- The process is complex and requires an extra effort to come up with the test data sources and reading mechanisms.  
- Requires proficiency in a programming language that is being used to develop test scripts

##### Keyword Driven Testing Framework
A Keyword-Driven Testing Framework (KDTF) is an automation framework design approach that separates the test automation logic from the test case design. The core idea is to define "keywords" that represent common actions performed during testing, and then use these keywords in a structured, usually tabular, format to create test cases.

It is an extension to DDTF in a sense that it not only segregates the test data from the scripts, it also keeps the certain set of code belonging to the test script into an external data file. 
These set of code are known as Keywords and hence the framework is so named. Keywords are self-guiding as to what actions need to be performed on the application.  

The keywords and the test data are stored in a tabular like structure and thus it is also called *Table driven Framework*. Take a notice that keywords and test data are entities independent of the automation tool being used. 

*Example - Email Login* 
KDTF separates test logic ("Keywords") into a base code, test data, and test case definitions into external tables. The "Locator/Data" column in the test case table directs keywords on *where* to act and *what* data to use.

1.  *Keywords (in Framework's Base Code):* These are generic functions like `open_browser()`, `navigate_to_url(url)`, `enter_text(locator, text)`, `click_element(locator)`, `verify_page_title(expected_title)`.
	- **Example:** A `Login` keyword might encapsulate `enter_text(username_field_locator, username)`, `enter_text(password_field_locator, password)`, `click_button(login_button_locator)`.

2.  *Test Data Table (`LoginTestData.csv`):* Stores specific values.

| DataKey       | Value                                  |
| :------------ | :------------------------------------- |
| `login_url`   | `https://your-email-service.com/login` |
| `valid_email` | `testuser@example.com`                 |
| `valid_password` | `SecurePass123`                     |
| `dashboard_title` | `Inbox - Your Email Service`         |
3.  *Test Case Definition Table (`LoginTestCases.csv`):* Orchestrates tests, linking keywords to locators/data.

| TestCaseID | Keyword                  | Locator/Data                      |
| :--------- | :----------------------- | :-------------------------------- |
| `TC_001`   | `open_browser`           |                                   |
| `TC_001`   | `navigate_to_url`        | `login_url` (from TestData)       |
| `TC_001`   | `enter_text`             | `id=email_field`, `valid_email`   |
| `TC_001`   | `enter_text`             | `id=password_field`, `valid_password` |
| `TC_001`   | `click_element`          | `id=login_button`                 |
| `TC_001`   | `verify_page_title`      | `dashboard_title` (from TestData) |
The automation engine reads `LoginTestCases.csv`, calls the corresponding keyword function from its base code, and uses the `Locator/Data` column to supply element identifiers and specific test data.
 * *Locator/Object Identifier*: How to locate the UI element (e.g., `id=username`, `xpath=//button[@name='login']`).

Pros:
- Possessing scripting knowledge is not required, unlike Data Driven Testing. 
- A single keyword can be used across multiple test script.
- easy maintenance and readability

Cons:
- The user should be well versed with the Keyword creation mechanism to be able to efficiently leverage the benefits provided by the framework.
- The framework becomes complicated gradually as it grows and a number of new keywords are introduced.
- High Initial Setup Effort & hard to debug

##### Hybrid Testing Framework
A combination of more than one above mentioned frameworks. The best thing about such a setup is that it leverages the benefits of all kinds of associated frameworks. 

Example of Hybrid Testing Framework: the Test sheet would contain both the keywords and the Data for testing login page. 

In this hybrid approach, the test automation engine reads directly from a single test sheet (e.g., an Excel or CSV file). Each row represents a test step, containing the keyword to execute, the element locator, and the specific data for that step.

**Test Sheet: `LoginTestScenario.csv`**

| TestCaseID | Step | Keyword              | Locator (Optional)   | Test Data (Optional)        | Expected Result / Description                            |
| :--------- | :--- | :------------------- | :------------------- | :-------------------------- | :------------------------------------------------------- |
| `TC_001`   | 1    | `OpenBrowser`        |                      | `Chrome`                    | Browser should launch successfully                       |
| `TC_001`   | 2    | `NavigateToURL`      |                      | `https://myemail.com/login` | Login page should load                                   |
| `TC_001`   | 3    | `EnterText`          | `id=email_field`     | `valid_user@example.com`    | Username `valid_user@example.com` entered                |
| `TC_001`   | 4    | `EnterText`          | `id=password_field`  | `SecurePass123`             | Password `SecurePass123` entered                         |
| `TC_001`   | 5    | `ClickButton`        | `id=login_button`    |                             | Login button should be clicked successfully              |
| `TC_001`   | 6    | `VerifyPageTitle`    |                      | `Inbox - My Email Service`  | Page title should be "Inbox - My Email Service"          |
| `TC_002`   | 1    | `OpenBrowser`        |                      | `Firefox`                   | Browser should launch successfully                       |
| `TC_002`   | 2    | `NavigateToURL`      |                      | `https://myemail.com/login` | Login page should load                                   |
| `TC_002`   | 3    | `EnterText`          | `id=email_field`     | `invalid_user@example.com`  | Invalid username entered                                 |
| `TC_002`   | 4    | `EnterText`          | `id=password_field`  | `WrongPass`                 | Invalid password entered                                 |
| `TC_002`   | 5    | `ClickButton`        | `id=login_button`    |                             | Login button should be clicked                           |
| `TC_002`   | 6    | `VerifyErrorMessage` | `css=.error-message` | `Invalid credentials.`      | Error message "Invalid credentials." should be displayed |

**How it works:** 
The automation engine reads each row. For `TC_001`, step 3, it would:
1.  Identify the `Keyword`: `EnterText`.
2.  Retrieve the `Locator`: `id=email_field`.
3.  Retrieve the `Test Data`: `valid_user@example.com`.
4.  Call the underlying `enter_text()` function in the framework's code, passing `id=email_field` and `valid_user@example.com` as arguments.

This hybrid approach offers the benefits of both:
* **Readability and Maintainability (from KDTF):** Business-level keywords make tests easy to understand.
* **Data Flexibility (from Data-Driven):** Test data is directly managed within the test definition, making it easy to create multiple scenarios by simply changing data values or adding new rows/columns to the sheet.
* **Reduced Complexity:** For simpler tests, having keywords and data in one place can be less cumbersome than managing separate data files.

In the above example, keyword column contains all the required keywords used in the particular test case and data column drives all the data required in the test scenario.  
If any step does not need any input then it can be left empty. 

##### Behavior Driven Testing Framework
Allows automation of functional validations in easily readable and understandable format to Business Analysts, Developers, Testers, etc.
Such frameworks do not necessarily require the user to be acquainted with the programming language.
There are different tools available for BDD like `cucumber`, `Jbehave` etc.  
- `Gherkin` language is used to write test cases in Cucumber.

#### Levels of Test Automation 
Test automation can be categorized into different levels based on its sophistication, reusability, and structure, evolving from simple scripts to comprehensive frameworks.

1. **Basic Level (Script-Based Automation):** 
	* **Description:** This is the entry point for test automation, often involving simple, standalone scripts written for individual test cases. Testers might use *record-and-playback* tools or write basic linear scripts.
	* **Characteristics:** Low reusability, high duplication of code, difficult to maintain, often lacks robust error handling or reporting. It's effective for automating a few repetitive tasks but struggles with scale.
	*  **Focus:** Getting tests automated quickly, often for specific, isolated scenarios.

2. **Advanced Level (Modular & Data-Driven Automation):** 
	* **Description:** Testers focus on making scripts more modular, reusable, and robust. This includes implementing techniques like function libraries, object repositories, and data-driven approaches where test data is separated from the test logic. This often includes Keyword-Driven, Data-Driven, Hybrid, or Behavior-Driven Development (BDD) frameworks.
	* **Characteristics:** Improved reusability and maintainability, reduced script duplication, better error handling, and more flexible test execution (running the same test with different data).
	* **Focus:** Creating more efficient and maintainable automated tests that can handle variations in data and UI.

3. **Framework Level (Structured Automation Frameworks):** 
	* **Description:** This represents the highest level of maturity, where a well-defined architecture and a collection of tools, *libraries*, conventions, and guidelines are established to support test automation across an entire project or organization. 
	* **Characteristics:** High reusability, ease of scaling, standardized reporting, seamless integration with CI/CD pipelines, clear separation of concerns (test logic, data, objects), and often supports contributions from both technical and non-technical team members.
	* **Focus:** Providing a scalable, maintainable, and efficient ecosystem for developing, executing, and managing a large suite of automated tests.


### Model Based Testing
Evaluation of software testing
Manual testing -> Automated testing -> Model based testing
##### Model Based Testing
Involves creating models of the system under test, which can be used to generate test cases and test data automatically.
Can help to identify defects earlier in the development process
Models help us to understand the system’s behavior.

**What is Model?** 
- A model is a description of a system’s behavior
- They help us understand and predict the system’s behavior
- Model-based testing checks run time behavior of the software under test against predictions made by a model.
- Behavior can be described in terms of input sequences, actions, conditions, output, and flow of data from input to output

MBT can be represented by Finite State Machines helps testers to assess the result depending on the input selected. Various combinations of the inputs can result in a corresponding state of the system.

*Advantages* 
- Easy test case/suite maintenance
- Reduction in Cost
- Improved Test Coverage
- Can run different tests on n number of machines
- Early defect detection
- Increase in defect count
- Time savings
- Improved tester job satisfaction

*Disadvantages* 
- Necessary Skills required in testers
- Learning curve time will be more
- Difficult to understand the model itself
- Deployment of MBT in every organization obviously requires a high amount of investment and effort


### Pytest: A Modern Python Testing Framework
Pytest is a popular and powerful Python testing framework known for its simplicity and extensibility. It aims to make writing small, readable tests easy, while also scaling to support complex functional testing for applications and libraries.

#### Pytest vs. Unittest (Brief Comparison)
While Python's built-in `unittest` module is a capable testing framework, Pytest often offers a more concise and Pythonic experience:
* **Less Boilerplate:** Pytest typically requires less boilerplate code. You don't need to import `unittest`, inherit from `unittest.TestCase`, or call `super().__init__()`.
* **Simpler Assertions:** Pytest uses standard Python `assert` statements, making tests more readable. `unittest` requires specific assertion methods like `assertEqual()`, `assertTrue()`, etc.
* **Automatic Test Discovery:** Pytest automatically discovers tests (files starting with `test_` or ending with `_test.py`, and functions starting with `test_`). `unittest` requires a `TestLoader` or `main()` call.

#### Key Features of Pytest
1. **Simple Test Syntax:** Use plain functions for tests, prefixed with `test_`.
2. **Assert Rewriting:** Enhances standard `assert` statements, providing detailed introspection on assertion failures without special methods.
3. **Fixtures:** A powerful and flexible way to provide a fixed baseline for tests, manage setup and teardown, and inject dependencies. Fixtures are functions that can be requested by test functions or other fixtures.
```
@pytest.fixture
def data(): return 42

def test_val(data):
	assert data == 42
```
4. **Parametrization:** Easily run a single test function multiple times with different sets of input data.
	```
	@pytest.mark.parametrize("x, y", [(1, 1), (2, 2)])
	def test_eq(x, y):
	    assert x == y
	```
5. **Plugins:** A rich ecosystem of plugins extends Pytest's functionality (e.g., `pytest-cov` for coverage, `pytest-xdist` for parallel execution, `pytest-html` for reports).
6. **Extensible:** Highly extensible for custom needs, allowing developers to write their own plugins.

#### How to Use Pytest (Basic Example)
1.  **Installation:** 
```bash
pip install pytest
```

2.  **Create a test file** (e.g., `test_example.py`):
```python
# my_functions.py (Optional: file containing functions to test)
def add(a, b):
	return a + b

def subtract(a, b):
	return a - b

# test_example.py
from my_functions import add, subtract # if functions are in another file

def test_add_positive_numbers():
	assert add(2, 3) == 5

def test_subtract_numbers():
	assert subtract(5, 2) == 3

def test_add_negative_numbers():
	assert add(-1, -1) == -2
```

3. RUN `pytest` 
### ROBOT Framework
- Python-based open-source test automation and robotic process automation (RPA) ecosystem.
- Robot Framework provides a unified way to access target systems with library keywords that are easy to extend.
- The same tool can test a website front end and backend in one end-to-end run.

**What makes Robot Framework work?** 
1. *Integrations* - Hundreds of available integration libraries.
2. *Architecture* - Low barrier to entry, but high ceiling for mastery.
3. *Logging* - Unified model for test log output.
4. *Community* - Active global community of users and developers.
5. *Governance* - Controlled by an active foundation with 50+ member companies.

**Main points** 
- It is a generic test automation framework - uses keyword-driven testing approach
- implemented with python - can be extended using python or java
- opensource

**High level architecture** (top down)
Test data (top) (test data syntax)-> Robot framework (Test library API)-> Test Libraries -> Test tools  (APIs)-> System under test

*Basic example using built in keywords* 
```robotframework
***Settings***
Library    OperatingSystem    # A built-in library for OS-related tasks

***Test Cases***
Verify File Exists
    File Should Exist    ${CURDIR}/example.txt

Create And Delete File
    Create File    ${CURDIR}/temp_file.txt    This is a temporary file.
    File Should Exist    ${CURDIR}/temp_file.txt
    Remove File    ${CURDIR}/temp_file.txt
    File Should Not Exist    ${CURDIR}/temp_file.txt
    
***Variables***
${BROWSER}           chrome
${URL}               https://www.google.com
${SEARCH_TERM}       Robot Framework

//// external libraries
***Settings*** 
Library    SeleniumLibrary 
```

**Advantage** 
- It is convenient to use and install.
- It is an open-source framework, anyone with or without programming experience can drive.
- It is suited to various operating systems and external libraries such as the Selenium library.
- The Robot framework supports behavior-driven, keyword-driven, and data-driven styles of building test cases.
- We can use any Robot Integrated Development Environment (RIDE) or any text editor to write the test cases.

**Disadvantage** 
- Scarcity of parallel test execution.
- Customizing HTML reports is not straightforward.
- Robot lacks support for if-else, nested loops, which are required when the code gets complex.

# CH 7:  Web Testing – Advanced Testing Types

**Website vs. Web Application** 
*Website* 
- A collection of related web pages with multimedia content.
- Informational and identified by a common domain name.

*Web Application* 
- A client-server program running in a web browser.
- Interactive, like webmail or online retail sales.

**Web Testing** 
Testing websites or web applications for bugs before going live, to ensure proper functionality and user acceptance.
*Challenges* 
- Multiple OS, browsers, hardware, and protocols complicate testing.

*Web Testing Types*
- Functionality Testing - Check links, forms, cookies, HTML, CSS, and database.
- Usability Testing -  Assess user-friendliness, navigation, and content clarity.
- Interface Testing
- Compatibility Testing
- Performance Testing
- Security Testing

**Common Web Application Vulnerabilities**
  **SQL Injection (SQLi)** 
- Attackers exploit vulnerabilities in SQL queries, often through unsanitized input fields (e.g., search bars), to gain unauthorized access to databases.

**Cross-Site Scripting (XSS)** 
- Malicious scripts are injected into web pages and executed in the browsers of other users. A common example is injecting scripts into comment sections.

**Cross-Site Request Forgery (CSRF)**
- This attack tricks authenticated users into performing unintended actions on a web application, such as submitting unauthorized form requests on banking websites.

**Insecure Direct Object References (IDOR)**
- Attackers bypass authorization by manipulating input parameters (e.g., changing URL parameters) to directly access restricted resources or view other users' accounts.

**Security Misconfiguration** 
Arises from incorrect or insufficient security settings in an application, server, or database. Default credentials on a database still in use.

**Broken Authentication** 
**Broken Access Control** 

##### Vulnerability Metrics for Assessment
* **Vulnerability Density:** Vulnerabilities per unit of code (e.g., per 1 KLOC).
* **Time to Remediate:** Average time to fix vulnerabilities.
* **Severity Levels:** Classification by impact (critical, high, medium, low).
* **False Positive Rate:** Percentage of non-actual threats reported.

**Strategies for Effective Security Testing**
* **Regular Testing:** Implement scheduled security tests to proactively identify vulnerabilities.
* **Automated Tools:** Utilize tools like OWASP ZAP for efficient vulnerability detection.
* **Training & Awareness:** Provide education to developers and stakeholders on secure coding practices and the importance of security.
* **Integrate Security:** Embed security into the development lifecycle through DevSecOps principles.

**Active and Passive Scanning with OWASP ZAP** 
*Active Scanning* 
Simulates attacks by sending requests to identify vulnerabilities like SQLi and XSS.
Example: Initiate active scan after configuring ZAP to target the application.

*Passive Scanning*
Monitors traffic during normal use without probing, detecting misconfigurations or data exposure.
Example: ZAP captures HTTP requests and responses as users navigate the app.


### Performance Testing
Performance testing evaluates response times, load capacity, and stability through various methods like load, stress, spike, and endurance testing, despite challenges in creating realistic scenarios and managing complex architectures.

**Types of Performance Testing**
* **Load Testing:** Assesses how an application performs under normal, expected user loads to pinpoint bottlenecks and ensure it can manage concurrent users effectively.
* **Stress Testing:** Determines the system's breaking point by exceeding its normal capacity and observing its behavior and recovery capabilities during failure.
* **Endurance Testing:** Evaluates an application's performance over an extended period to uncover issues like memory leaks that may only appear during prolonged use.
* **Spike Testing:** Examines the system's reaction to sudden, dramatic increases in user load to gauge its ability to handle abrupt changes in traffic.

**More types of Performance testing** 
* **Volume Testing**: Tests application performance with large data volumes to assess behavior under heavy data loads.
* **Scalability Testing**: Evaluates the ability to scale up or down in response to varying loads, ensuring system growth capacity.
* **Configuration Testing**: Examines how different application configurations affect performance to find optimal settings.

**key metrics in performance testing** 
* **Response Time**: Time taken by the system to respond to a request; critical for user experience.
* **Throughput**: Number of transactions processed in a given time, indicating system capacity.
*  **Error Rate**: Percentage of requests resulting in errors; high rates signal performance issues.
* **Resource Utilization**: CPU, memory, disk, and network usage monitored to identify bottlenecks.
* **Latency**: Measures request travel time.
* **Concurrency**: The number of simultaneous users handled effectively.

*Latency example* 
Imagine you're requesting a webpage.
* **Network Time**: The time for your request to reach the server and the server's response to return to you. (e.g., 100ms)
* **Server Time**: The time the server takes to process your request and generate the page. (e.g., 50ms)
* **Overhead**: Any small extra delays (e.g., your browser rendering the page). (e.g., 20ms)

**Calculation:** 
* **Total Latency** = Network Time + Server Time + Overhead
* **Total Latency** = 100ms + 50ms + 20ms = 170ms

So, it takes 170 milliseconds for the webpage to load.


##### Locust, an open-source tool for performance testing
Three key features:
1. **Distributed Testing**: Locust can simulate a large number of users by spreading the load across multiple machines, making it scalable.
2. **Realistic User Behavior**: It allows users to define complex user scenarios using Python code, which leads to more accurate testing.
3. **Web-Based UI**: Locust offers an easy-to-use web interface for monitoring tests and viewing statistics in real-time.

Other popular performance testing tools, besides Locust:
* **Apache JMeter**: A common choice for load testing and measuring the performance of web applications.
* **Gatling**: Uses Scala for defining user scenarios in load testing.
* **LoadRunner**: A feature-rich tool that supports a wide range of applications and protocols.
* **BlazeMeter**: A cloud-based platform that works with JMeter and provides better scalability.

##### Procedures for performance testing
1. **Understand Testing Types**: Be aware of different kinds of performance tests like load, stress, endurance, spike, volume, scalability, and configuration testing.
2. **Monitor Key Metrics**: Keep an eye on important performance indicators such as response time, throughput, error rate, resource utilization, latency, and concurrency.
3. **Leverage Tools**: Use tools like Locust, along with others, to simulate user behavior realistically and analyze the performance data.
4. **Optimize and Scale**: Use the gathered information to improve system configurations and ensure the application can scale effectively.

##### Key challenges encountered in performance testing
* **Environment Setup**: Accurately replicating production environments is difficult because of hardware, software, and network variations that can affect test results.
* **Test Data Management**: Creating realistic test data is a significant challenge, as insufficient data can lead to inaccurate performance outcomes.
* **Tool Selection**: With numerous options available, selecting the most suitable performance testing tool can be overwhelming yet is crucial for the success of the testing effort.
* **Complex Applications**: The complexity of modern distributed systems makes it hard to pinpoint bottlenecks because of the many interconnected components and services.

More challenges
* **Intermittent Issues**: Performance problems that occur sporadically are hard to reproduce, leading to wasted effort.
* **Resource Constraints**: Limited time and budget can restrict the scope of testing, potentially leading to incomplete assessments and issues in production.
* **Stakeholder Communication**: Effectively communicating the importance and results of performance testing to stakeholders can be difficult without clear metrics.

**Strategies to address performance testing challenges**:
**Environment and Data Challenges:**
* **Environment Replication**: Use cloud services to create test environments that mirror production, reducing infrastructure costs.
* **Realistic Test Data**: Employ data generation and anonymization tools, and collaborate with stakeholders to simulate real user behavior.
* **Tool Evaluation**: Select tools based on ease of use, integration capabilities, and protocol support relevant to your application's needs.
* **Modular Testing**: Divide complex applications into components to isolate issues and simplify troubleshooting.

**Intermittent Issues and Resource Constraints:** 
* **Automated Testing**: Implement automated tests to run consistently at scale, which can help in detecting intermittent problems.
* **Resource Planning**: Ensure sufficient time and budget are allocated, prioritize critical areas, and integrate testing throughout the development lifecycle.

**Stakeholder Communication:** 
* **Clear Metrics and Reporting**: Define measurable performance metrics and utilize visual reports to effectively communicate findings to stakeholders.

##### LOCUST: A Scalable Load Testing Tool
* **What it is:** LOCUST is a user-friendly, Python-based tool for simulating user behavior and performing scalable load testing.

**Key Features:**
* **Developer-Friendly:** Define user actions using Python code.
* **Scalable:** Simulate thousands of concurrent users to test performance under heavy load.
* **Real-Time Monitoring:** A web UI provides live metrics like requests per second, response times, and failure rates.

**Core Concepts for Scripting:**
* **`HttpUser`:** A class to define a user's behavior.
* **`@task` Decorator:** Marks methods within `HttpUser` as actions to be performed during the test. Higher numbers indicate higher priority.
* **`wait_time`:** Specifies the random delay between user tasks, simulating realistic user behavior (e.g., `between(1, 5)` seconds).
* **`self.client`:** Used within tasks to make HTTP requests (e.g., `self.client.get`, `self.client.post`).
* **Event Listeners (e.g., `@events.test_start`):** Allow running code at specific points in the test lifecycle (like the start of the test).

**In essence, LOCUST allows you to:** 
1.  **Write Python code** to describe what your users do (e.g., visit pages, submit forms).
2.  **Run this code at scale** to simulate many users at once.
3.  **Monitor the performance** of your application in real-time.

```
from locust import HttpUser, task, between

class WebsiteUser(HttpUser):
    """
    User class that does requests to the website it is hovering over
    """
    wait_time = between(1, 5)  # Wait time between requests

    @task
    def index(self):
        self.client.get("/")

    @task(2)  # This task has higher priority
    def about(self):
        self.client.get("/about/")

    def on_start(self):
        # Code to run when a user is starting
        print("Started!")

    def on_stop(self):
        # Code to run when a user is stopping
        print("Stopped!")
```

- `Run locust -f your_test_script.py --host=http://yourwebsite.com `


# CH - 8: AI in Software Testing

AI Techniques in Software Testing

| Technique | Key Applications |
| --- | --- |
| **Machine Learning (ML)** | Defect prediction, automated test case generation, and test suite optimization. |
| **Deep Learning (DL)** | Automated test script generation and intelligent GUI testing. |
| **Natural Language Processing (NLP)** | Automated requirements analysis, generation of test cases from natural language, code reviews, bug detection/repair, oracle generation, documentation, and code recommendations. |

**ML Workflow** 
Training data -> ML algorithms -> Model -> Output
                                                        ↑
                                                      data

Challenges of ML -> Overfitting and Underfitting

**Why AI in Software Testing?** 
Pressures that make AI adoption necessary:
* Increasing software complexity outstrips manual testing capacity
* Shorter release cycles (daily/weekly deployments)
* Need for instant feedback in CI/CD pipelines
* Shift from "testing harder" to "testing smarter"

**Evolution of Testers** 
Manual Tester -> Test Automation Engineer -> AI

"Test automation engineers will be the Subject matter experts teaching AI to execute the tests"
70:30, 70% AI, 30% - questioning the system

**How can AI be applied to SE?** 
- Automation of Software development activities
- Recommendation systems to assist developers improve their performance. 
- problems such as optimization, classification, prediction

##### AI Impacts on Software Testing
* **Automation:** Auto-generates test cases, schedules executions, and creates reports.
* **Efficiency:** Predicts defects and suggests intelligent bug fixes.
* **Data Generation:** Uses reinforcement learning and algorithms to create test data.
* **Optimization:** Prioritizes and parallelizes test suites to speed up execution.

**NLP in Software Testing** 
has become a cornerstone of modern software applications, offering a wide range of functionalities from sentiment analysis to chatbots, and from language translation to content summarization.

**NLP in Software Testing** 
1. *Automating Test Case Creation*
NLP transforms requirements and user stories into test scenarios by analyzing text structure and meaning.

**Key Techniques:** 
* **Tokenization & POS Tagging:** Breaks down and categorizes text components.
* **Dependency Parsing:** Maps relationships between words.
* **NER:** Identifies specific entities (people, places, objects).
* **Semantic Analysis:** Interprets context and actions.

* **Benefit:** Reduces manual effort and ensures comprehensive scenario coverage.

2. *Automating Test Documentation* 
NLP extracts data from test cases and results to generate accurate, human-readable reports.

**Key Techniques:** 
* **Text Summarization:** Condenses findings into key highlights.
* **Text Classification:** Categorizes bugs or test statuses.
* **Sentiment Analysis:** Evaluates tone in user feedback or bug reports.
* **Document Clustering:** Organizes and groups related documentation.

* **Benefit:** Maintains consistent, up-to-date documentation and reduces miscommunication.

**NLP Challenges in Software Testing** 
* **Ambiguity:** Natural language requirements vary in clarity and structure, making it difficult for algorithms to consistently extract accurate information.
* **Data Scarcity:** High-quality, domain-specific training data is difficult and time-consuming to create, which limits algorithm accuracy.

##### Benefits and challenges of AI in Software Testing
**Benefits of AI in Software Testing** 
* Improved test coverage and efficiency
* Reduced testing time and effort
* Enhanced defect detection and root cause analysis
* Adaptive and self-healing testing capabilities

**Challenges in Applying AI to Software Testing** 
* **Data Quality:** High-quality, accurately labeled training data is scarce and costly to generate.
* **Explainability:** The "black-box" nature of many AI models makes it difficult to interpret why a test passed or failed.
* **Robustness:** AI systems may be unpredictable or vulnerable to adversarial inputs, raising concerns about reliability.
* **Integration:** Seamlessly embedding AI tools into legacy testing pipelines often presents complex deployment hurdles.

**Ethical & Future Challenges in AI Testing** 
* **Bias & Fairness:** Prevent demographic or systemic biases in models to ensure objective testing outcomes.
* **Explainability:** Shift from "black-box" models to transparent, interpretable systems where AI reasoning is auditable.
* **Privacy & Security:** Safeguard sensitive test data using advanced techniques like differential privacy and secure multi-party computation.
* **Enterprise Scaling:** Optimize AI for massive, complex systems through distributed and parallel computing architectures.

### Performance Metrics for Classification Models
These metrics are essential for evaluating how well a model categorizes data.

| Metric               | Definition                                     | Formula                                                                                   |
| -------------------- | ---------------------------------------------- | ----------------------------------------------------------------------------------------- |
| **Confusion Matrix** | A table layout summarizing prediction results. | N/A                                                                                       |
| **Accuracy**         | Proportion of total correct predictions.       | $\frac{TP + TN}{\text{Total}}$                                                            |
| **Precision**        | Accuracy of positive predictions.              | $\frac{TP}{TP + FP}$                                                                      |
| **Recall**           | Ability to find all positive instances.        | $\frac{TP}{TP + FN}$                                                                      |
| **F1 Score**         | Harmonic mean of Precision and Recall.         | $2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}$ |
* **TP (True Positive):** Correctly predicted positive.
* **TN (True Negative):** Correctly predicted negative.
* **FP (False Positive):** Incorrectly predicted positive (Type I error).
* **FN (False Negative):** Incorrectly predicted negative (Type II error).





 