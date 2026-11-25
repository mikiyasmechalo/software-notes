---
title: Simulation and Modeling
teacher: Mr. Addisu Mandefro
---
Resource: [Teacher's Medium Note](https://medium.com/@tesfaygidey21/simulation-and-modeling-07b875eeb2d1)
# CH 1: Basics in SIM
A **simulation** is the imitation of the operation of a real-world system over time. an attempt to duplicate the features, appearance, and characteristics of a real system.
It involves:
- the generation of an artificial history of a system.
- the observation of the artificial history to draw inference on operating characteristics of the system.

The model helps to investigate a variety of "what if" questions about the real-world system.
- "what would be the impact of a change in the system's performance?"

Some models are simple and can be solved by just mathematical models like probability theory or differential calculus.
But many real-world systems are complex - and the problems of those systems can be solved with computer simulation models.

Simulation modeling can be used both as an analysis tool and a design tool. 
- *Analysis Tool*: To predict the effect of changes to the existing systems.
- *Design Tool*: To predict the performance of new systems under varying sets of circumstances.

**When is Simulation Not Appropriate?** 
According to Banks and Gibson(1997):
- when the problem can be solved by common sense or analytical solution.
- It is less expensive to implement direct experiments instead
- The costs exceed expected savings after the simulation project.
- The necessary resource or time is unavailable.
- The simulation is not validated./ when there isn’t the ability to verify and validate the model.
- The system's behavior is too complex to model.

**Advantages of Simulation** 
- New policies (procedures, decision rules etc.) can be explored without disrupting the real system.
- New system designs (physical layout, hardware design, etc.) can be tested without committing resources for their acquisition. 
- When formulating hypotheses about the causes or mechanisms behind certain phenomena, these hypotheses can be evaluated to see if they are plausible or testable.
- As we observe the system behavior, the time of the simulation can be compressed or expanded for a speed-up or a slow-down of the simulated process.
- Bottleneck analysis can be performed to discover where resource is being delayed excessively.
- A simulation helps us to understand how the system actually operates rather than how individuals think the system operates.
- “What if” questions can be answered in the design of new systems.

**Disadvantages of Simulation** 
- Building a simulation model of a system requires special training.
- The model conceptualization of a system can be subjective.
	- making assumptions, simplifications, and choices depends on the modeler's perspective.

- The performance outputs of a simulation are hard to interpret. may require additional analysis, such as statistical methods or comparison to known benchmarks, for meaningful insights.
- The randomness in the inputs cause the outputs to be random as well.
- Simulation outputs are either estimates or approximations of the performance measures that are considered. Even with rigorous validation, there will always be some degree of uncertainty in the results.
- Simulation modeling and analysis can be time-consuming and expensive.

**Areas of Application** 
- Manufacturing Applications 
- Construction Engineering and Project Management
- Military Applications 
- Logistics, Supply Chain and Distribution Applications 
- Transportation Modes and Traffic 
- Business Process Simulation

**Simulation in Software Engineering** 
1. *Software testing*: simulate user interactions and system behavior.
2. *System Design*: modeling architectures to evaluate performance, scalability and reliability.
3. *Network Simulation*: analyzing data flow and congestion in network systems.
4. *Algorithm Simulation*: to understand their behavior and efficiency.
5. *Game Development*: creating realistic environments and behaviors for NPCs and physics simulation.
6. *Performance Modeling*: to predict performance under different loads and identify bottlenecks.
7. VR and AR: simulating real world environments for immersive experiences.
8. Training and Education

### System
A system is defined as a group of objects that are joined together in some regular interaction or interdependence toward the accomplishment of some purpose.
A system is often affected by the changes happening outside the system. (system environment)
- The *system boundary* separates the system from its environment.

**Components of A system** 
1. **Entity**: an object of interest in the system.
2. **Attribute**: property of entities
3. **Activity**: a time period of specific length,
4. **State Variable**: The collection of variables necessary to describe the system at any time(snapshot).
5. **Event**: an instantaneous occurrence that might change the state of the system.

A complete list of components cannot be developed unless the purpose of the simulation study is known.

**Discrete and Continuous Systems** 
- *Discrete System*: state variables change at a discrete set of time points. e.g. banks, car parks
- *Continuous System*: state variables change at a continuous set of points. e.g. Water Dam, stock-market

**The Need for a Model** 
*Direct Experimentation Limitations*: Studying a system through direct experimentation is often not feasible.
- The system might not exist yet. 
- Even if the system exists, it may be impractical to experiment with it.

*Importance of modeling* 
- Most studies require a model of the system to understand its behavior and dynamics.

### Model
Is a representation of a system for the purpose of studying the system.
- it should only consider the aspects of the real system that affect the problem under investigation.
- it should be sufficiently detailed to permit valid conclusions about the real system.
- If the purpose of the investigation changes, the model might change too.
- Different models of the same system could be required as the purpose of investigation changes.

**Types of Models** 
- *A physical model* - larger or smaller version of an object.
- *A mathematical model* - uses symbolic notations, mathematical equations and inequalities to represent a system.
- *A simulation model* - a particular type of mathematical model of a system.

**Types of Simulation Models** 
*Static vs. Dynamic* 
- Static - represent a system at a particular point in time.
- Dynamic - represents systems as they change over time.

*Deterministic vs. Stochastic* 
- Deterministic - contains no random variables and have a known set of inputs(variables) which will result in a unique set of outputs. Given the same inputs, it produces the exact same output every single time.
- Stochastic - has one or more random variables as inputs. "Random inputs lead to random outputs" (structure),  "The same input can lead to different output" (behavior)

*Discrete vs. Continuous* 
- If there is at least one state variable that changes at continuous set of time points, then the model is continuous.
- Most simulation models are discrete, stochastic, and dynamic.

### Discrete-Event System Simulation
The modeling of systems where state variables change at discrete points in time.
They focus on specific events that trigger changes in the system’s state.

**Analysis methods**:
- Analytical methods - use deductive reasoning to solve a model
- Numerical methods - utilize computational procedures to solve a model.

Numerical techniques are often preferred for complex systems where analytical solutions are not feasible.

> [!note]
> - In discrete-event system simulation, models are run rather than solved.
> - An artificial history of the system is generated from the model assumptions.
> - Collected observations are analyzed to estimate the performance measures of the true system.

#### Steps of Discrete-Event System Simulation
5 main steps:
1. Problem formulation
2. Model Construction
3. Model Translation
4. Experimental design
5. Implementation

Detail:
- **Problem formulation** 
	- Problem must be clearly understood by the analyst from those who have the problem. The policy maker/analyst must understand and agree with the formulation.
	- Stakeholders define what they need, the analyst confirms how (and whether) it can be done.
- **Setting of objectives and overall project plan**
	- The objectives indicate the questions to be answered by the simulation.
	- At this point, a determination should be made concerning whether simulation is the appropriate methodology for the problem as formulated and the objectives as stated.
- **Model conceptualization** 
	- The art of modeling is enhanced by an ability to abstract the essential features of a problem, to select and modify basic assumptions that characterize the system.
- **Data collection** 
	- As the model changes, the required data elements can also change.
	- Data collection takes a large portion of time, hence it is necessary to begin as early as possible.
- **Model translation** 
	- The model must be entered into a computer recognizable format (GPSS/SIMSCRIPT or special-purpose simulation software).
- **Verification** 
	- Is the computer program performing properly?
	- Debugging for correct input parameters and logical structure.
- **Validation** 
	- The determination that a model is an accurate representation of the real system.
	- Validation is achieved through the calibration of the model.
- **Experimental design** 
	- Decision on the length of the initialization period, the length of simulation runs, and the number of replications to be made of each run.
- **Production runs and analysis** 
	- To estimate measures of performances.
- **More runs?** 
	- After the run is completed, the analyst determines whether additional runs are needed and what design those additional experiments should follow.
- **Documentation and reporting** 
	- Program documentation: for the relationships between input parameters and output measures of performance, and for a modification.
	- Progress documentation: the history of a simulation, a chronology of work done and decision made.
- **Implementation** 
	- Finalize the model and ensure it meets all requirements.
	- Deploy the simulation in the intended environment.

**Phases** 
- Discovery and Orientation Phase (problem formulation & objective setting/ plan)
- Model Building Phase  (conceptualization, data collection, model translation, verification & validation)
- Run Phase (Experimental design & production run and analysis)
- Implementation Phase (documentation and reporting & Implementation)

# CH 2: System Simulation

System simulation is a powerful technique used across various fields, to model and analyze complex systems.
- It involves creating a digital model of a real-world system to study its behavior under various conditions.
- we can observe its performance, identify bottlenecks, and evaluate the impact of different variables without the cost and time associated with physical experimentation.

The simulations in this chapter are carried out by following three steps:
1. **Determine the characteristics of each of the inputs to the simulation.**
	- These are quite often modeled as probability distributions, either continuous or discrete.

2. **Construct a simulation table.**
	 - Each simulation table is different, since each is developed for the problem at hand.
	 - An example of a simulation table is shown in the Table below.
	 - In this example, there are `p` inputs, `x_ij`, `j = 1, 2, ..., p`, and one response, `y_i`, for each of the repetitions (or trials) `i = 1, 2, ..., n`.

| Repetition (i) | Input 1 (x_i1) | Input 2 (x_i2) | ... | Input p (x_ip) | Response (y_i) |
|---|---|---|---|---|---|
| 1 | x_11 | x_12 | ... | x_1p | y_1 |
| 2 | x_21 | x_22 | ... | x_2p | y_2 |
| ... | ... | ... | ... | ... | ... |
| n | x_n1 | x_n2 | ... | x_np | y_n |

3. **For each repetition `i`, generate a value for each of the `p` inputs, and evaluate the function, calculating a value of the response `y_i`.**
	- Input values may be computed by sampling values from the distributions chosen in step 1.
	- A response typically depends on the inputs and one or more previous responses.

### Simulating Randomness and Random Numbers

What is **Spreadsheet Simulation**? A spreadsheet simulation is the one that is carried out on a spreadsheet, works for relatively simple simulations.
Suitable examples for spreadsheet applications (e.g., queuing simulations, Monte Carlo simulations)

**How to simulate randomness?** 
- What is Spreadsheet Simulation? A spreadsheet simulation is the one that is carried out on a spreadsheet.
	- Banking system: Inter-arrival times, service times 
	- Restaurant system: Released orders 
	- Warehouse system: Size of the packages

**Random Numbers** 
Is a randomly generated quantity in the unit interval (0, 1).

A sequence of random-numbers with arbitrary length must conform two **statistical properties**: 
1. The numbers should be uniformly distributed between 0 and 1. 
2. Successive numbers generated should be statistically independent of all previous numbers generated.

**Generating Randomnes** 
- In discrete event simulation models, random variables act as inputs, influencing the model's outcomes.

- *Common Distributions*
	- **Exponential Distribution**: Often used to model inter-arrival times in systems (e.g., customer arrivals in a bank).
	- **Normal Distribution**: Commonly used for service times in various applications (e.g., restaurant orders).
	- **Bernoulli Distribution**: Suitable for binary outcomes (e.g., whether a customer places an order).

#### Queueing Simulation
In a simple single-server queue, we assume an infinite calling population from which people enter our system. We assume that the inter-arrival times of the customers and their service times (in minutes) are known (deterministic) and given in the following table for the first six customers.


| Customer | Inter-arrival Time | Service Time |
| -------- | ------------------ | ------------ |
| 1        | -                  | 2            |
| 2        | 2                  | 1            |
| 3        | 1                  | 3            |
| 4        | 1                  | 2            |
| 5        | 2                  | 1            |
| 6        | 6                  | 4            |
Due to its fairness, we assume a FIFO (first in, first out) service policy, i.e., the customers are served with respect to their arrival order.

(a) Create a simulation table that contains for each customer: *the arrival time*, *the time that service begins*, *the time that service ends* (the departure time), *the time spent in the queue*, and the *time spent in the system*. Then calculate the average time spent in the queue and in the system by customers.

| Customer    | Inter-A.T | Arrival Time | Service Begins | Service Time | Service Ends (D) | Time in Queue | Time in System |
| ----------- | --------- | ------------ | -------------- | ------------ | ---------------- | ------------- | -------------- |
| 1           | -         | 0            | 0              | 2            | 2                | 0             | 2              |
| 2           | 2         | 2            | 2              | 1            | 3                | 0             | 1              |
| 3           | 1         | 3            | 3              | 3            | 6                | 0             | 3              |
| 4           | 1         | 4            | 6              | 2            | 8                | 2             | 4              |
| 5           | 2         | 6            | 8              | 1            | 9                | 2             | 3              |
| 6           | 6         | 12           | 12             | 4            | 16               | 0             | 4              |
| **Average** |           |              |                |              |                  | **0.67**      | **2.83**       |

(b) Consider the number of customers in the system as the state variable. Then the events that change the state variable are arrivals and departures. Create a table that gives the chronological ordering of the events. The following table gives the chronological order of the events that  change the state variable.

| Time | Event     | Customer(entity) | State (Customers in System) |
| ---- | --------- | ---------------- | --------------------------- |
| 0    | Arrival   | 1                | 1                           |
| 2    | Departure | 1                | 0                           |
| 2    | Arrival   | 2                | 1                           |
| 3    | Departure | 2                | 0                           |
| 3    | Arrival   | 3                | 1                           |
| 4    | Arrival   | 4                | 2                           |
| 6    | Departure | 3                | 1                           |
| 6    | Arrival   | 5                | 2                           |
| 8    | Departure | 4                | 1                           |
| 9    | Departure | 5                | 0                           |
| 12   | Arrival   | 6                | 1                           |
| 16   | Departure | 6                | 0                           |

(C) Show the behavior of the state variable over a plot diagram where the horizontal axis represents the time and the vertical axis represents the state variable.

```
State L(t)
  ▲
2 ┼               ┌───────────────┐
  │               │               │
1 ┼───────────────┘       *       └───────┐               ┌───────────────┐
  │       *       *       *               │               │               │
0-┴───┬───*───┬───*───┬───*───┬───┬───┬───┴───┬───┬───┬───┴───┬───┬───┬───┴──► Time  0   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16
```


### Generating Random Quantities
To simulate real-world scenarios, we need to generate random numbers that follow specific probability distributions. This process begins with generating uniform random numbers:
- **Uniform Distribution**: A fundamental distribution where all outcomes are equally likely within a specified range (0 to 1).

**Excel Functions for Random Number Generation** 
1. `RAND()` Function:- Generates a random number between 0 and 1. Syntax: `=RAND()` 
2. `RANDBETWEEN()` Function:- Generates a random integer between two specified values. Syntax: `=RANDBETWEEN(x, y)`.

## Techniques in System Simulation

**1. Discrete Event Simulation (DES)** 
DES models systems where changes occur at distinct points in time, triggered by events.
- Commonly used in queuing systems, manufacturing processes, and network simulations.

*Characteristics* 
- Events represent changes in the system state (e.g., arrival of a customer).
- Time advances to the next event, making it efficient for handling systems with sporadic activities.
	- the simulation clock doesn't tick forward in fixed, uniform steps (like every 1 second). Instead, it jumps directly to the next scheduled event (e.g., a customer arriving).
	- keeps simulation fast when activity is sparse.

**2. Continuous Simulation** 
Models systems that change continuously over time, often described by differential equations.
- Used in fields like fluid dynamics, environmental modeling and population dynamics.

*Characteristics* 
- focuses on the behavior of the system over time than at discrete intervals.
- Typically requires numerical methods to solve the equations governing the system.

**3. Monte Carlo Simulation** 
A probabilistic technique that uses random sampling to estimate the behavior of a system.
- Widely used in finance, risk assessment, and project management.

*Characteristics* 
- It generates a large number of random inputs based on specified probability distributions.
- and analyzes the resulting outputs to derive statistical insights (e.g., mean, variance).

*Real-world use*: A project manager estimates task durations as ranges (e.g., 3–7 days). Run 10,000 random combinations → get "80% chance the project finishes within 45 days."

**4. Agent-Based Simulation** 
Models systems as a collection of autonomous agents that interact according to defined rules.
- Useful in social sciences, ecology, and economics.
- Agents = individual entities (people, animals, firms) each following simple local rules (e.g., "buy if price < X", "flee if neighbor panics").

*Characteristics* 
- Each agent represents an individual entity with its own behaviors and decision-making processes.
- Suitable for studying emergent phenomena from local interactions among agents.
	- Emergent phenomena = large-scale patterns that nobody programmed directly but arise from all those local interactions (e.g., traffic jams, market crashes, flocking birds, disease spread).

**5. System Dynamics** 
`A specific methodology within continuous simulation.` 
SD models a system as interconnected **stocks** (accumulations e.g., population) and **flows** (rates of change e.g. births/deaths), linked by **feedback loops** (positive reinforcing loop → growth; negative balancing loop → stabilization).

Instead of modeling individual agents, it models the aggregate behavior of the whole system over time using differential equations.
- Commonly used in policy analysis, organizational behavior, and resource management.

*Characteristics* 
- Focuses on the interaction between different components of a system.
- Utilizes differential equations to model continuous change and feedback effects.
- Contrast with Agent-Based: SD = top-down, continuous, aggregate; ABS = bottom-up, discrete, individual.

- Focus: understanding behavior patterns (growth, oscillation, collapse) and policy leverage points , not exact physical prediction.
- Typically uses simplified aggregate models rather than precise physical equations.


### Monte Carlo Simulation
Is a statistical technique that uses random sampling to model and analyze the behavior of complex systems or processes.
- It helps in understanding the impact of risk and uncertainty in prediction and forecasting models.

**Key Concepts** 
- **Random Variables** - the simulation involves generating random variables to represent uncertain parameter models.
- **Sampling** - Multiple scenarios are simulated by sampling from probability distributions, allowing for the exploration of various outcomes.
- **Iterations** - The process is repeated numerous times (often thousands or millions) to create a distribution of possible results.

**Applications** 
- **Finance**: Used for option pricing, risk assessment, and portfolio management. 
- **Engineering**: Helps in reliability analysis and project risk management. 
- **Operations Research**: Useful in supply chain management, queueing systems, and inventory control.

#### Steps in Monte Carlo Simulation
1. **Define the Problem**: Clearly outline the system or process to be studied.
2. **Model the System**: Create a mathematical model that includes all relevant variables and their relationships.
3. **Identify Input Distributions**: Determine the probability distributions for all uncertain inputs.
4. **Run Simulations**: Use random sampling to generate multiple scenarios and calculate outputs. 
5. **Analyze Results**: Assess the output distributions to make informed decisions, identifying potential risks and opportunities.

**Short example - Project completion time (3 tasks in series):** 
**1. Define the Problem:** Estimate when a project finishes. Three tasks run sequentially; each duration is uncertain.

**2. Model the System:** Total time T = D₁ + D₂ + D₃

**3. Identify Input Distributions:**
- D₁ (design): uniform between 3–7 days
- D₂ (build): triangular, min 4, mode 6, max 10
- D₃ (test): normal, mean 5, std 1.5

**4. Run Simulations:** Draw one random value from each distribution, sum them → one scenario. Repeat 10,000 times.

Sample runs:

| Run | D₁ | D₂ | D₃ | Total |
|-----|----|----|----|-------|
| 1   | 4.2 | 6.1 | 5.3 | 15.6 |
| 2   | 6.8 | 8.5 | 3.9 | 19.2 |
| 3   | 3.1 | 4.4 | 6.7 | 14.2 |

**5. Analyze Results:** Across 10,000 runs: e.g.
- Average total ≈ 16.5 days
- 80% chance done within 19 days
- 5% chance it exceeds 22 days (tail risk)

**Decision:** Quote the client 20 days to be safe, or add buffer. The *average* (16.5) alone would've been misleading.

**Advantages** 
- **Flexibility**: Can be applied to a wide range of problems across different fields.
- **Intuitive Visualization**: Provides visual representations of risk and uncertainty, making complex data more understandable.

**Challenges** 
- **Computationally Intensive**: Requires significant computational resources, especially for complex models. 
- **Accuracy and Reliability**: The results depend heavily on the quality of the input data and the model structure.

Monte Carlo system simulation is a powerful tool for decision-making under uncertainty, providing valuable insights into the potential variability of outcomes and the risks associated with different scenarios.

**Scenario: Software Development Project Time Estimation** 
You are managing a project to develop a new task management application.
The project consists of the following tasks: 
1. Requirements Gathering 
2. Design 
3. Development
4. Testing
5. Deployment

Step 1: Define Task Durations (weeks in this case)

| Task    | Minimum | Most Likely | Maximum |
| ------- | ------- | ----------- | ------- |
| Req. G. | 2       | 3           | 4       |
| Design  | 3       | 5           | 7       |
| Dev.    | 4       | 6           | 9       |
| Testing | 2       | 3           | 5       |
| Dep.    | 1       | 2           | 3       |

Step 2: Assign Probability Distributions Use a triangular distribution for each task based on the estimated ranges. `Parameters (min, mode, max)` 

Step 3: Set Up the Simulation - Python or Excel
```python
import numpy as np
import matplotlib.pyplot as plt
# Define the task durations using triangular distribution
def triangular_sample(minimum, most_likely, maximum):
	return np.random.triangular(minimum, most_likely, maximum)

# Number of simulations
num_simulations = 10000

# Store total project durations
total_durations = []

# Run the simulation
for _ in range(num_simulations):
	req_duration = triangular_sample(2, 3, 4) # Requirements Gathering
	design_duration = triangular_sample(3, 5, 7) # Design
	dev_duration = triangular_sample(4, 6, 9) # Development
	test_duration = triangular_sample(2, 3, 5) # Testing
	deploy_duration = triangular_sample(1, 2, 3) # Deployment
	# Calculate total duration for the project
	total_duration = req_duration + design_duration + dev_duration+test_duration + deploy_duration
	total_durations.append(total_duration)

# Analyze results
mean_duration = np.mean(total_durations)
std_dev_duration = np.std(total_durations)

# Plot the results
plt.hist(total_durations, bins=50, alpha=0.75, color='blue')
plt.title('Distribution of Total Project Durations')
plt.xlabel('Total Duration (weeks)')
plt.ylabel('Frequency')
plt.grid(True)
plt.show()

# Output the results
print(f'Mean Project Duration: {mean_duration:.2f} weeks')
print(f'Standard Deviation: {std_dev_duration:.2f} weeks')

# Example Output results
# Mean Project Duration: 17.65 weeks
# Standard Deviation: 1.48 weeks
```

Step 4: Analyze the Results
- **Mean Project Duration**: This gives you the average time expected to complete the project. 
- **Standard Deviation**: This indicates the variability in the project duration. 
- **Histogram**: The histogram visualizes the distribution of project durations, allowing you to see how likely different completion times are.

### Continuous System Simulation
Models dynamic systems that change continuously over time, often described by **differential equations**.

**Key Concepts** 
- **Continuous variables**:  variables that can take on any value within a range.
- **State Variables**: a set of  variables that describe the system at any given time.
- **Differential Equations**: The behavior of the system is typically described by mathematical equations that relate the rates of change of state variables.

**Applications** 
- **Engineering**: Used in control systems, fluid dynamics, and process control. 
- **Biological Systems**: Models population growth, spread of diseases, and ecological interactions.
- **Economics**: Analyzes continuous processes like capital accumulation and economic growth.

Steps in Continuous System Simulation 
1. **Define the System**: Clearly identify the components and interactions of the system. 
2. **Develop Mathematical Models**: Formulate differential equations that represent the relationships between state variables. 
3. **Initial Conditions**: Specify the initial values of state variables to begin the simulation. 
4. **Numerical Methods**: Use numerical techniques (e.g., Euler's method, Runge-Kutta methods) to solve the differential equations over time. 
5. **Run Simulations**: Execute the simulation over a defined time period, collecting data on the state variables. 
6. **Analyze Results**: Evaluate the output data to understand system behavior, stability, and potential outcomes.

**Advantages**
- **Realism**: Captures the continuous nature of many physical and biological processes.
- **Dynamic Analysis**: Allows for the examination of transient behaviors and stability over time.

**Challenges**
- **Complexity**: Formulating and solving continuous models can be mathematically complex.
- **Computational Demand**: Requires significant computational resources, especially for high-dimensional systems.

**Key applications:**
1. **System Performance** - models response times and throughput under varying load; analyzes Resource(CPU/memory) utilization over time.
2. **Networks** - simulates data flow to understand congestion, optimize routing, and evaluate protocol performance in real time
3. **Control Systems** - models feedback systems (robotics, automation); analyzes dynamic response of software to inputs over-time for stability
4. **Software Testing** - load testing with simulated users to find bottlenecks; stress testing under extreme conditions for reliability
5. **Model-Driven Development** - visualizes system behavior before implementation; tools like MATLAB Simulink for software components that require continuous state changes.
6. **Embedded/IoT** - designs real-time embedded systems interacting with physical processes; models sensor data processing
7. **Game Dev** - physics engines for realistic movement/collision; real-time strategy agent interactions
8. **DevOps/CI** - simulates deployments across environments for performance/scaling; models infrastructure configurations before deployment

### Discrete System Simulation
Models systems where state changes occur at distinct points in time, often triggered by specific events.
Used to analyze and understand systems that can be represented as a series of events or transactions, rather than continuous changes.

**Key Concepts** 
- **Events**: The fundamental units in discrete simulation, representing a change in the state of the system (e.g., arrival of a customer, completion of a service). 
- **State Variables**: Variables that describe the system at a specific point in time, changing only when events occur. (e.g. number of customers in queue)
- **Event Scheduling**: A mechanism to manage future events, determining when they will occur and updating the system state accordingly.

**Applications** 
- **Queueing Systems**: scenarios like customer service lines, telecommunications, and computer networks. 
- **Manufacturing Systems**: Analyzes production lines, inventory management, and supply chain processes. 
- **Healthcare**: Simulate patient flow in hospitals to optimize resource allocation and reduce wait times. 
- **Transportation**: Models traffic flow, public transport systems, and logistics to improve efficiency.

**Steps in Discrete System Simulation** 
1. **Define the System**: Identify the components, processes, and interactions within the system.
2. **Develop a Model**: Create a conceptual model that includes events, state variables, and their relationships.
3. **Event List Creation**: Generate a list of future events that will affect the system and their scheduled times.
4. **Simulation Execution**: Process events in chronological order, updating the system state as each event occurs.
5. **Data Collection**: Gather data on system performance, such as wait times, resource utilization, and throughput (derived from discrete events).
6. **Analysis**: Evaluate the results to identify trends, bottlenecks, and opportunities for improvement.

**Advantages** 
- **Flexibility**: Can model a wide variety of systems with complex interactions and behaviors.
- **Event-Driven**: Efficiently simulates systems where changes occur at irregular intervals, focusing computational resources on active events.

**Challenges** 
- **Complexity of Model Building**: Creating accurate models can be complex, especially for systems with many interacting components.
- **Randomness**: Incorporating randomness and variability can complicate simulations and analysis.

**Key applications:**
1. **Queueing Systems** - model server performance, optimize resources/response times; load testing for peak loads
2. **Networks** - traffic management, packet switching, routing; protocol evaluation under varied loads
3. **Software Testing** - event-driven testing for user interactions; stress testing under extreme conditions
4. **Manufacturing/Process Control** - production line & inventory optimization; workflow & resource planning
5. **Healthcare** - patient admission/treatment flow; EHR system testing & optimization
6. **Game Dev** - discrete game mechanics (interactions, behaviors, resources); NPC AI via event-driven responses
7. **Logistics/Supply Chain** - inventory level & order simulation; delivery route optimization
8. **DevOps/CI** - deployment simulations across environments; infrastructure change impact testing.

# CH3: Random Numbers
**Random numbers** are numbers generated in a sequence where each number is equally likely to occur, without a discernible pattern.
- Are essential in simulation, modeling, cryptography, gaming, and various computational techniques such as Monte Carlo simulation.
- In computational contexts, random numbers are generated **algorithmically**, making them **pseudorandom**, as they rely on deterministic processes.

**Key properties of random numbers** 
- **Uniformity**: The numbers should be uniformly distributed over a specified range.
- **Independence**: The occurrence of one number should not affect the occurrence of others

### Generation of Random Numbers
Various techniques, ranging from physical methods (e.g., radioactive decay) to algorithmic pseudorandom methods.

#### Mid-Square Random Number Generator
One of the earliest pseudorandom number generation techniques.

Steps:
1. Start with an initial seed value (a positive integer).
2. Square the seed to produce a number with twice as many digits.
3. Extract the middle digits of the squared result to form the next random number.
4. Repeat the process using the newly generated number as the seed.

**Advantages**: Simple and easy to implement.
**Limitations**: The sequence may eventually fall into a loop or degenerate into zero for poorly chosen seeds.

***Example***:
- Seed: 1234
- Square: $1234^2$ = 1522756
- Middle digits: 227
- Next RN: 227

#### Linear Congruential Method (LCM)
One of the most popular algorithms for generating pseudo-random numbers.
It is defined by the recurrence relation:
$$X_{n+1}=(aX_n+c)\mod m$$
- a - the multiplier
- c - the increment
- m - the modulus
- $X_0$ - the initial seed (initial value)

**Advantage**: It is Fast and Efficient.
**Limitations**: the quality of randomness depends on the parameters. poor choices lead to short cycles or non-uniformity.

**Example:** 
Parameters: a = 5, c = 3, m = 16, seed X₀ = 7

| n   | Xₙ  | Xₙ₊₁ = (5·Xₙ + 3) mod 16           |
| --- | --- | ---------------------------------- |
| 0   | 7   | (35+3) mod 16 = 38 mod 16 = **6**  |
| 1   | 6   | (30+3) mod 16 = 33 mod 16 = **1**  |
| 2   | 1   | (5+3) mod 16 = 8 mod 16 = **8**    |
| 3   | 8   | (40+3) mod 16 = 43 mod 16 = **11** |
| 4   | 11  | (55+3) mod 16 = 58 mod 16 = **10** |

Sequence: 7, 6, 1, 8, 11, 10, ...

**Key points illustrated:**
- Each value is deterministic from the previous one (pseudo-random, not true random).
- The modulus m = 16 caps values to 0–15.
- With good parameters, the cycle length can be up to m (here 16). With bad parameters, it repeats early — e.g., if a and m share a factor, the sequence gets stuck in a short loop.

**Why parameters matter:** Hull-Dobell theorem says you get a full period (all m values before repeating) only if: $\gcd(c,m)=1$, a-1 divisible by all prime factors of m, and a-1 divisible by 4 if m is divisible by 4.


### Other methods for random numbers
- **Additive Congruential Method**: Combines two or more congruential sequences. *Example: mix LCM outputs from two different seeds for longer cycles.* 
- **Mersenne Twister**: Maintains an array of 624 integers; twists the state (bitwise shifts/XORs) then tempers one value into output. Period ≈ 2^19937−1. *Example: Python's `random` module default.* 
- **Cryptographic Random Generators**: Designed for secure applications; rely on cryptographic algorithms. *Example: AES-based DRBG for encryption keys.*
- **Hardware-based Generators**: Use physical phenomena (thermal noise, radioactive decay) for true randomness. *Example: Intel RDRAND instruction.* 

### Testing Random Numbers
Testing is crucial to ensure the generated numbers exhibit the properties of randomness. The tests commonly applied include:
- **Frequency Test**: Checks if the numbers are uniformly distributed over the range.
- **Runs Test**: Examines the sequence for patterns or streaks.
	- A run = a consecutive streak of similar outcomes (e.g., a run of heads, a run of numbers above the median).
- **Autocorrelation Test**: Ensures there is no correlation between successive numbers.

#### Uniformity Test
A specific test to verify that the random numbers are evenly distributed across the specified range:
1. **Divide the range**: split the range of possible values into equal intervals (bins).
2. **Count Occurrences**: Count the number of occurrences in each interval/ bin.
3. **Calculate Statistic**: Use statistical methods like the Chi-Square Test to compare observed frequencies with expected frequencies.
$$\text{Chi-square: }X^2=\sum\frac{(O_i-E_i)^2}{E_i}$$
	- $O_i$ is the observed frequency in each bin
	- $E_i$ is the expected frequency (total numbers divided by the number of bins.)

4. **Compare to critical Value**: use the Chi-square distribution table to determine if the statistic exceeds a critical value, indicating a deviation from uniformity.

# CH 4: Input Modeling and Output Analysis Methods
