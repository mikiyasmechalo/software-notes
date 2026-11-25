---
title: Artificial Intelligence
---
# CH1- Intro
### AI
Some define AI based on human intelligence and others on an abstract definition of rationality.
- Some also consider intelligence to be a property of a *thought process* and *reasoning* and others focus on intelligent *behavior*, an external characterization.
- From these two dimensions-human vs. rational and thought vs. behavior there are four possible combinations.

#### 1. Acting Humanly: The Turing test Approach
Programming a computer to pass a rigorously applied test (The Turing Test) provides plenty to work on. The computer would need the following capabilities:
- Natural Language Processing
- Knowledge Representation - Storing Knowledge
- Automated Reasoning
- Machine Learning - adapt to new circumstances and detect patterns.

Turing didn't feel vision and movement(robotics) necessary to demonstrate intelligence. however other researchers have proposed a **total Turing test** w/c includes those 2.

#### 2. Thinking Humanly: The cognitive modeling approach
To say that a program thinks like a human, we must know how humans think. We can learn about human thought in 3 ways:
- introspection - reflecting on our thoughts
- psychological experiments - observing people
- brain imaging - observing the brain.

The interdisciplinary field of *cognitive science* brings together computer models from AI and experimental Cognitive science techniques from psychology to construct precise and testable theories of the human mind.

####  3. Thinking rationally: The “laws of thought” approach
Aristotle's syllogism provided patterns for argument structure that always yielded correct conclusions when given correct premises. **Logic** studies these laws of thoughts.

Logic as conventionally understood requires knowledge of the world that is certain a condition that, in reality, is seldom(rarely) achieved. The theory of **probability** fills this gap.

In Probability principle, it allows the construction of a comprehensive model of rational thought, leading from raw perceptual information to an understanding of how the world works to predictions about the future. 
What it does not do, is generate intelligent behavior. For that, we need a theory of rational action. Rational thought, by itself, is not enough.

#### 4. Acting Rationally: The rational agent approach
An **agent** is just something that acts. They are expected to operate autonomously, perceive their environment, persist over a prolonged time period, adapt to change and create & peruse goals.

A **rational agent** acts as to achieve the best outcome, or the best expected outcome.
"Law of thought" approach to AI, (making correct inferences) is part of being rational agent (deducing that a given action is best and acting on that). 
But also other ways of acting rationally exist, example recoiling hand from stove is a reflex action.

The rational-agent approach is the best standard for AI because it's:
1.  **More General:** It focuses on **acting rationally** (achieving the best outcome), which is a broader goal than just using pure logic ("laws of thought").
2.  **Scientifically Easier:** **Rationality is mathematically defined,** allowing researchers to design and prove that an agent's design will work, which is something we can't do when trying to exactly imitate human thought or behavior.

 In a nutshell, AI has focused on the study and construction of agents that *do the right thing*. This general paradigm is so pervasive that we might call it the **standard model**.

We must refine the standard model to account for the fact that *Perfect rationality isn't practical* for AI in complex environments because the computational demands are too high. 

#### Beneficial machines
The standard model has been a useful guide for AI research since its inception, but it is probably not the right model in the long run.
The reason is that the standard model assumes that we will supply a fully specified objective to the machine.

Real world scenarios are too complex and doesn't have a a clear objective like artificial tasks like chess.
They are particularly problematic in the general area of human–robot interaction, of which the self-driving car is one example. (Too many questions)

The problem of achieving agreement between our true preferences and the objective we put into the machine is called the **value alignment problem**: e.g. "The paperclip maximizer".
Fixing these objective dis-agreements once they leave the lab is harder and risk increases with the intelligence of the system.

e.g. for a chess playing system, going outside the chessboard and using other ways to increase its chance of winning are not "unintelligent" but a logical consequence of defining "winning" as the sole objective.

Since it's impossible to perfectly code all human objectives into a machine, the standard AI model is inadequate.

We need a new model where the AI is **uncertain** about our exact goals. When an agent knows it doesn't know the full objective, it gains an incentive to:
* **Act Cautiously** 
* **Ask Permission** 
* **Learn** human preferences
* **Defer** to human control
The ultimate goal is to create agents that are **provably beneficial** to humans, not just agents that relentlessly pursue a fixed, possibly flawed, objective.

### Foundations of Artificial Intelligence

| Discipline                                | Core Contribution to AI                                                                                                           |
| :---------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------- |
| **Philosophy**                            | Posed the **original questions** about mind, logic, and reasoning, formalizing thought as **manipulable symbols**.                |
| **Mathematics**                           | Provided the **formal tools** (Logic, Computation, and Probability) to guarantee correct inference and handle **uncertainty**.    |
| **Psychology**                            | Modeled the **human mind** as an **information-processing system**, guiding early symbolic AI design.                             |
| **Economics**                             | Developed **Decision Theory**, which formalizes **rational action** as maximizing expected utility in complex situations.         |
| **Neuroscience**                          | Provided the **biological inspiration** (neurons and brain structure) for developing **neural networks** and deep learning.       |
| **Computer Engineering & Control Theory** | Delivered the **hardware, speed, and feedback loops** necessary for building and controlling autonomous agents.                   |
| **Linguistics**                           | Defined the **structure of human language** (grammar, meaning, syntax), which is essential for Natural Language Processing (NLP). |

Core Milestones in Artificial Intelligence (AI) History
1. Foundational Concepts and Symbolic AI (1943–1973)
	- 1943-1950: Neural Foundations-McCulloch/Pitts create the formal neuron model; Turing proposes the Turing Test (1950).
	- 1956: The Dartmouth Workshop officially coins the term "Artificial Intelligence" (John McCarthy) and sees the debut of the Logic Theorist (LT).
	- 1957-1969: Symbolic AI and Early Nets-Development of the General Problem Solver (GPS) and the Lisp language (McCarthy); early neural networks like Perceptrons emerge.
	- 1969-1973: First AI Winter-Research stalls due to computational limits (combinatorial explosion) and the mathematical limitations of early neural nets highlighted by Minsky and Papert.
2. Expert Systems Era (1970–1986)
	- Focus Shift: Moved away from general intelligence to knowledge-intensive, rule-based systems (Knowledge Engineering).
	- Key Systems: Programs like MYCIN (medical diagnosis) and DENDRAL (molecular structure) proved effective in narrow domains.
	- Commercial Success & Downturn: R1 (XCON) became commercially successful, but expert systems were too brittle and expensive to maintain, leading to a market collapse.
3. Modern AI, Statistics, and Deep Learning (1986–Present)
	- 1986: Connectionism Revived-The back-propagation algorithm is widely adopted, enabling the training of multilayer neural networks.
	- 1987–2000s: Probabilistic AI-Emphasis shifts to rigorous, statistical methods (e.g., Bayesian Networks by Judea Pearl) and reinforcement learning (Rich Sutton).
	- 2001–Present: Data and Hardware-The explosion of Big Data and advances in hardware (GPUs/TPUs) provides the resources necessary for scaling AI.
	- 2011–Present: Deep Learning Dominance-Breakthroughs in multi-layered neural networks revolutionize computer vision (ImageNet 2012) and game-playing (AlphaGo), marking the current AI acceleration.
	- 2017–Present: Generative AI & Transformers—Introduction of the Transformer architecture (2017) and models like GPT and BART, leading to the explosion of Large Language Models (LLMs) and advanced image generators (DALL-E, Imagen).
	- 2020–Present: Multimodality and Societal Impact—AI systems increasingly handle multiple data types (text, image, audio) simultaneously. Focus shifts to issues of safety, ethics, alignment, and the pursuit of Artificial General Intelligence (AGI).


What can AI do today?
Robotic vehicles, Legged locomotion, Autonomous planning and scheduling, Machine translation, Speech recognition, Recommendations, Playing games, Image understanding, Medicine, Climate science.

#### Risks and Benefits of AI
- Lethal autonomous weapons
- Surveillance and Persuasion
- Biased decision making
- Impact on employment
- Safety-critical applications
- Cybersecurity

The sense of unease with the idea of creating ASI or AGI can be called the **gorilla problem**.
Many cultures have myths of humans who ask gods, genies, magicians, or devils for some thing. Invariably, in these stories, they get what they literally ask for, and then regret it. The third wish, if there is one, is to undo the first two. We will call this the **King Midas problem**: "let everything I touch turn into gold".


General AI goals
- Replicate human intelligent
- Solve knowledge intensive/Sever/ task
- Make an intelligent connection between perception (insight, sense, become aware) and action
- Enhance human-computer interaction/ communication

Knowledge -> Declarative(facts) and Procedural(how)
- Procedural knowledge can be embedded in declarative knowledge


# CH1 PT. 2: Intelligent Agents
### Agents and Environments
An agent is anything that perceives it's environment through sensors and acting upon that using actuators.

We use the term **percept** to refer to the agent’s perceptual inputs at any given instant. *Percept sequence* is history of everything the agent has perceived.
An agent's decision can only be depend on the percept sequence and nothing else. an agent's behavior is like a math function (*agent function*) that maps percept sequence to an action and is implemented by an agent program.

### Good Behavior: Rationality
Generally AIs moral philosophy is *consequentialism*, the consequences of it's action determine it's behavior.
The desirability of action is captured by a *performance measure* that evaluate any given sequence of environment states. but here we also run into the *King Midas problem*.

**Rationality** 
depends on 4 things:
- the performance measure ('clean floor' for a vacuum robot)
- the agent's knowledge of the environment
- the actions the agent can perform
- the action's percept sequence to date

*Definition of a rational agent*: for each percept sequence, a rational agent maximizes performance measure given the evidence given by the percept sequence and the built in knowledge.

**Omniscience, learning and autonomy**
An omniscient agent knows the actual outcome of its actions and can act accordingly; but omniscience is impossible in reality. Rationality $\not =$ Omniscience. Rationality is not perfection.

Doing actions in order to modify future percepts-sometimes called *information gathering* - is an important part of rationality. (**Learning**)

A rational agent should be **autonomous**-it should learn what it can to compensate for partial or incorrect prior knowledge.

### The Nature of Environments
Before building rational agents we must think about the *task environment*, w/c are the 'problems' to w/c the rational agents are the solution.

**Specifying the task environment**
e.g. for the robot vacuum, the performance measure, the environment, and the agent’s actuators and sensors are under the *task environment*. AKA the **PEAS** (Performance, Environment, Actuators and Sensors) description.

Specifying the task environment should be the first task when building an agent.

**Properties of task environments**
1. *Fully observable vs. Partially observable*: does an agent's sensors give it access to the complete state of the environment at each point in time? complete state means all aspects relevant to the choice of the action, relevance in turn depends on the performance measure.
	- partiality may happen b/c of faulty or missing sensor data. e.g. a taxi cannot know what other drivers are thinking. This doesn't mean the agent's plight is hopeless.
2. *Single-agent and multiagent*: solving a crossword puzzle (1 agent) or playing chess (2 agents). In a single agent environment other things are treated as just objects but in multiagent environment aspects such as competition, co-operation and partiality come up.
3. *Deterministic vs. nondeterministic*: stochastic (based on probability) $\not =$ nondeterminism (e.g. there is a chance of rain tomorrow). mostly real world is non-D.
4. *Episodic vs. sequential*: atomic episodes where the next episode doesn't depend on the actions on previous episodes, e.g. an assembly robot. but in sequential, the previous decision can have long-term consequences. 
5. *Static vs. dynamic*: does the environment change while the agent is deliberating?, If the environment itself does not change with the passage of time but the agent’s performance score does, then we say the environment is *semi-dynamic*.
6. *Discrete vs. continuous*: applies to the state of the environment, to the way time is handled, and to the percepts and actions of the agent. e.g. a chess environment has a finite number of distinct states but a Taxi does not.
7. *Known vs. unknown*: refers not to the environment itself but to the agent’s (or designer’s) state of knowledge about the “laws of physics” of the environment. In "known" all outcomes (probabilities) are given for all actions.


### The Structure of Agents
 The job of AI is to design an agent program that implements the agent function- Agent program the mapping from percepts to actions.
 
We assume this program will run on some sort of computing device with physical sensors and actuators, we call this the *agent architecture*:
$$\text{Agent = Architecture + Program}$$ 
**Agent programs**
Agent Programs take the current percept as input from the sensors and return an action to the actuators. but Agent functions may depend on the entire percept history.
 
4 basic kinds of agent programs that embody almost all intelligent systems:
- Table Driven agents (included in ppt?)
- Simple reflex agents
- Model-based reflex agents
- Goal-based agents
- Utility-based agents

It is instructive to consider why the table-driven approach to agent construction is doomed to failure. it is just too much info to put in a table. (a) no storage, (b) no time to create table (c) no agent could learn all entries from its experience.

 Despite all this, TABLE-DRIVEN-AGENT does do what we want, assuming the table is filled in correctly: it implements the desired agent function.
 
**Simple Reflex Agents**
The simplest kind of agent, it selects actions on the basis of the current percept, ignoring history.
e.g. a simple vacuum cleaner, dirt? suck. push brake if the person in front also does.

```
 function SIMPLE-REFLEX-AGENT(percept) returns an action
 persistent: rules, a set of condition–action rules
 state←INTERPRET-INPUT(percept)
 rule←RULE-MATCH(state,rules)
 action←rule.ACTION
 return action
```

**Model-based reflex agents**
The most effective way to handle partial observability is for the agent to keep track of the part of the world it can’t see now. (maintain an internal state depending on the percept history).w

To update the internal state we need 2 kinds of knowledge: 1, info about how the world changes, b/c of and independent of the agent. we call this the *Transition model*, 2, how the state of the world is reflected in the agent's percepts, e.g. a wet camera producing a distorted image, we call this *Sensor model*.

An agent that uses such models is called is a model-based agents.

```
 function MODEL-BASED-REFLEX-AGENT(percept) returns an action
 persistent: state,  transition model,  sensor model, rules,  action,
 state←UPDATE-STATE(state,action,percept,transition model,sensor model)
 rule←RULE-MATCH(state,rules)
 action←rule.ACTION
 return action
```

**Goal-based agents**
The "current state" is not always enough to make a decision. e.g. a car in a crossroad can go 3 ways but the correct decision depends on where it is trying to go. GOAL.

The agent uses the model from model based and the goal to choose actions.

A goal-based action may be straightforward or complex and tricky, Search and Planning are the subfields of AI devoted to finding action sequences that achieve the agent's goals.

 The reflex agent brakes when it sees brake lights, period. It has no idea why. A goal-based agent brakes when it sees brake lights because that’s the only action that it predicts will achieve its goal of not hitting other cars.

Although less efficient, goal based agents are more flexible.

**Utility-based agents**
Goals alone are not enough to generate high-quality behavior in most environments. 
e.g. a taxi can get to the destination through many action sequences, but some are safer, cheaper...

Goals are binary, happy or unhappy. a more general performance measure should allow comparison of d/t world states according to exactly how happy they would make the agent.
We use 'utility' instead of 'happy' here.

An agent’s utility function is essentially an internalization of the performance measure.
 
Emphasis is needed that this is not the only way to be rational as we have seen with the simple vacuum robot, but as with goal-based agents, a utility-based agent has many advantages in terms of flexibility and learning.

Furthermore, in two cases, goals are inadequate but utility-based agent can still make a rational decision. 1, when there are conflicting goals and only one can be chosen, the utility-function specifies the appropriate tradeoff. 2, when there are several goals that the agent can aim for, none of which can be achieved with certainty, utility provides a way in which the likelihood of success can be weighed against the importance of the goals.

**Learning agents** 
- A learning agent improves itself over time.
- The performance element selects the actions (the core agent).
- The learning element makes improvements to the agent.
- The critic gives the learning element feedback on how well the agent is doing, using a fixed performance standard.
- The problem generator suggests trying new, potentially sub-optimal actions to gain useful experience (exploration).
- Learning works by modifying the agent's internal components to match the feedback and improve.

**How the components of agent programs work** 
Agent programs need to represent the world to decide what to do. These representations fall along an axis of increasing complexity:

Atomic Representation
* *Each state is indivisible*; it has no internal structure.
* The state is treated as a **single, black-box entity** (e.g., just the name of the current city).
* *Used by*: Search, game-playing, Hidden Markov Models.

Factored Representation
* Each state is broken down into a **fixed set of variables** or attributes, each with a value.
* Different states can **share some attributes** (e.g., GPS coordinates) but differ on others (e.g., gas level).
* *Used by*: Constraint satisfaction, propositional logic, and Bayesian networks.

Structured Representation
* The world is described using **objects and explicit relationships** between them.
* It's necessary for handling complex, novel situations (e.g., a "truck reversing into a driveway blocked by a cow").
* *Used by*: First-order logic, relational databases, and natural language understanding.

Summary of Expressiveness
* *Expressiveness* increases from Atomic to Factored to Structured.
* More expressive representations can describe complex situations **more concisely** (e.g., the rules of chess).
* However, *reasoning and learning become more complex* as expressiveness increases.


# CH2: Solving Problems by Searching

### Problem-Solving Agents
Type of goal-based agents.
e.g. an agent is in Romania in the city of Arad and wants to go to Bucharest.
- we assume the environment is *Known* with info such as a map.

*Goal Formulation*
- the agent adopts the goal of reaching Bucharest.

*Problem Formulation*
- description of the states and the actions necessary to reach the goal. (an abstract model of the relevant part of the world) 
- e.g. one good model could be to consider the actions of traveling one city to the next.

*Search*
- the agent first simulates sequences of action in its model, the one sequence that reaches the goal is called the *solution*. might also found no solution.

*Execution*
- execute the sequence of actions in the solution, one at a time.
- if the world is fully observable and deterministic, reaching the goal with the found solution is guaranteed so we can ignore the agents percepts. this is called an *Open-Loop system*
- if the world is non-deterministic or a chance to be wrong, we can monitor the percept. called *Closed-Loop system*.

##### Search problems and solutions
A search **Problem** can be defined as follows:
- *State space* - set of all possible states that the environment can be in.
- The *Initial state* the agent starts in.
- One or more *goal states*.
- *Actions* available to the agent. given a state *s*, `ACTIONS(s)` returns a finite set of actions that can be executed in *s*. we say these actions are *applicable* in s.
	- `ACTION(Arad) = {To Sibiu, To Timisoara, To Zerind}`
- A *Transition model*, w/c describes what each action does. `RESULT(s,a)` returns the result state.
	- `RESULT(Arad, To Zerind) = Zerind`
- A *Cost function* `ACTION-COST(s,a,s')` or `c(s,a,s')`, this gives the cost of applying action a in state s to reach state s'. 
- *Solution*  - correct/best path.

A sequence of actions forms a *path*, and a *solution* is a path from the initial state to a goal Path state.
An optimal solution has the lowest path cost among all solutions.
The state space can be represented as a graph in which the vertices are states and the Graph directed edges between them are actions.

##### Formulating problems
A *model* is an abstract mathematical description, we remove un-necessary details from the representation (abstraction).

The abstraction is useful if carrying out each of the actions in the solution is easier than the original problem;

### Example Problems
##### Standardized problems
e.g. a Vacuum robot in a simple grid, 
- *states* - says w/c objects are in which cells. here the objects are dirt and the agent.
	- in a simple 2 cell version we have 8 total states, n cells means $n * 2^n$ states.
- *initial state* - any of the states
- *Actions* - 2 cells means we have: suck, move left and right as actions. 
- *Transition model* - such removes dirt and the other 2 moves the agent if not facing a wall.
- *Goal states* - the states in w/c both cells are clean.
- *Action cost* - each action costs 1 (abstract unit).

*Sokoban puzzle* - is another example for grid world w/c the goal is to push boxes to their designated locations.

##### Real-world problems
Consider the airline travel problems that must be solved by a travel-planning Web site:
- *states* - each state with location and current time, fares (cost) that may depend on previous segments so we need to record record extra info about historical aspects. and status as domestic or international.
- *initial state* - home airport.
- *actions* - any flight from the home airport.
- *transition model* - the resulting destination and the arrival time.
- *goal state* - a destination city.
- *action cost* - monetary cost + waiting time + flight time + customs and immigration procedures, seat quality, ......

The *traveling salesperson problem* (TSP) is a touring problem in which every city on a map must be visited. The aim is to find a tour with cost <C (or in the optimization version, to find a tour with the lowest cost possible).

Other examples: VSI layout problem, Robot navigation problem, automatic assembly sequencing ...

### Search Algorithms
- Takes a search problem as an input and returns a solution or an indication of failure.

Each node in a search tree corresponds to a state in the state space and the edges in the search tree correspond to actions. the root node is the initial state.
- The **Frontier** in a search tree is the set of all nodes (states) that have been generated but not expanded.

##### Best-first search
Which we choose a node, n with minimum value of some evaluation function, `f(n)`. 
We check if n is a goal state and if not we apply *EXPAND* to generate child nodes.

A child node is added to the frontier if it has not been reached before or if the current path is cheaper than the previous ones.
The algorithm returns either an indication of failure, or a node that represents a path to a goal. 
The `f(n)` function determines the specific algorithm.


##### Search Data Structures
A node in a tree has 4 components:
- `node.state`, `node.parent`, `node.action`, `node.path-cost`(total cost from initial node).

to store the frontier we need a data structure: usually a *queue* with operations:
- `IS-EMPTY(frontier)`, `POP(frontier)`, `TOP(frontier)` (pop without remove), `ADD(node, frontier)`

there are 3 type of queues used in search algorithms:
- *priority queue* - minimum cost (best-first)
- *FIFI queue* - node added to the queue first, breadth first search
- *LIFO queue* - (stack) most recently added, depth first.

We call a search algorithm a *graph search* if it checks for redundant paths and a *tree-like search* if it does not check. Best-first search is a graph search.

##### Measuring problem-solving performance
**COMPLETENESS**: Is the algorithm guaranteed to find a solution when there is one, and to correctly report failure when there is not?
**COST OPTIMALITY**: Does it find a solution with the lowest path cost of all solutions?
**TIME COMPLEXITY**: How long does it take to find a solution? This can be measured in seconds, or more abstractly by the number of states and actions considered.
**SPACE COMPLEXITY**: How much memory is needed to perform the search?

To be complete, a search algorithm must be *systematic* in the way it explores an infinite state space, making sure it can eventually reach any state that is connected to the initial state. 

### Uninformed Search Strategies
##### Breadth-first search
- appropriate when all actions have the same cost.
- This is a *systematic* search strategy that is therefore **complete** even on infinite state spaces. and it gives the **optimal** solution if path cost is a non-decreasing function of the depth of the node.
- the same as a best-first-search where f(n) is the depth of the node, or number of actions taken.
- can be more efficient by using a FIFO queue than a priority queue.
- the reached is a set of states instead of a mapping b/c once we reach a state there will not be a better path to that state. we can do an *early goal test* (checking as soon as it is generated rather than when it is about to be expanded (late goal test)).

Both time and space complexity are $O(b^d)$.
- b: Maximum branching factor of the search tree (actions per state).
- d: Depth of the solution
- m: Maximum depth of the state space (may be ∞) (also noted sometimes D).

In general, exponential complexity search problems cannot be solved by uninformed search for any but the smallest instances.
e.g. a branching factor of 10, speed of 1 mil. nodes/s and 1 Kbyte/node. a search to depth 10 takes < 3 hours but 10 TB of memory and if we do 14 depth it would take 3.5 years.

##### Dijkstra’s algorithm or uniform-cost search
- best-first search where `f(n)` is the (path) cost of the path from the root to the current node.
- the worst-case space and time complexity is $O(b^{1+[c^*/\epsilon]})$, w/c can be much greater than $b^d$. b/c the this algorithm can explore large trees of action with low costs before exploring paths involving paths involving a high cost and perhaps useful actions.
	- $C^*$ - optimal cost
	- $\epsilon$ - lower bound on the cost of any edge
	- b - branching factor (average number of neighbors)
- Uniform-cost search is **complete** and is **cost-optimal**, because the first solution it finds will have a cost that is at least as low as the cost of any other node in the frontier.
- A uniform-cost search algorithm is implemented by the priority queue.

##### Depth-first search and the problem of memory
Always expands the deepest node in the frontier first.
- a best first search where the evaluation function *f(n)* is the negative of the depth.

However, it is usually implemented not as a graph search but as a tree-like search that does not keep a table of reached states.
Depth-first search is not cost-optimal; it returns the first solution it finds, even if it is not cheapest.

For *finite state* spaces that are trees it is efficient and complete; for acyclic state it might re-expand the same state, but will (eventually) *systematically* explore the entire space.

In *infinite* *state* spaces, depth-first search is *not systematic*: it can get stuck going down an infinite path, even if there are no cycles. Thus, depth-first search is incomplete.

Why DFS then? for problems where a tree-like search is feasible, depth-first search has much smaller needs for memory. no *reached* table needed and frontier is often small.

DFS has a memory complexity of `O(bm)` where *b* is the the branching factor and *m* is the max depth of the tree.

A variant of depth-first search called **backtracking search** uses even less memory. where only one successor is generated at a time. and successors are generated by modifying the current state and not allocating new memory. has complexity of `O(b)`.

It uses a stack for its implementation.

##### Depth-Limited Search Algorithm
A depth-first search with a predetermined limit.
It solves the drawback of the 'infinite path' problem in DFS.

The node at the depth limit will be treated as it has no successor nodes further.

Depth-limited search can be terminated with two Conditions of failure:
- *Standard failure value*: It indicates that problem does not have any solution.
- *Cutoff failure value*: It defines no solution for the problem within a given depth limit.

- It is DFS so needs less memory but it is incomplete (may not found the solution).
- it may not be optimal if the problem has more than one solution.

Time Complexity: Time complexity of DLS algorithm is O(bℓ).
- b - branching factor, ℓ - depth limit


##### Iterative Deepening Depth-First Search (IDDS)
Combination of DFS (memory) and BFS(speed), it finds the best depth limit and explores it by gradually increasing the limit until a goal is found.
Useful when search space is large and depth of the goal node is unknown.

The disadvantage is that it repeats all the work of the previous phase.

This algorithm is **incomplete** if the branching factor is infinite. but **complete** on infinite depth.
IDDFS is **optimal** if path cost is a non decreasing function of the depth of a node.

Time complexity `O(bd)`
Space complexity $O(b^d)$ 

##### Bidirectional Search Algorithm
Runs two simultaneous searches, one from initial state called as *forward-search* and the other from goal node called as *backward-search*.

Uses two small subgraphs in which one starts the search from an initial vertex and other starts from goal vertex.

BSA can use search techniques such as BFS, DFS, DLS ...

It is fast and requires less memory, But the implementation is difficult.

It is **complete** if we use BFS in both searches.
It is also **Optimal**.

Has a Time and Space complexity $O(b^d)$.



### Informed Search Algorithms
ISAs contain an array of knowledge such as how far we are from the goal, path cost, how to reach goal node(a rough direction), etc..

The informed search algorithm is more useful for large search space b/c it helps us explore less of the search space.
Informed search algorithm uses the idea of heuristic, so it is also called Heuristic search.

**Heuristics Function**: Heuristic is a function which is used in Informed Search, and it finds the most promising path.
It takes the current state of the agent as its input and produces the estimation of how close agent is from the goal.
- Might not give the BEST solution but it will give a good solution in a reasonable time.


##### Pure Heuristic Search
Simplest form of heuristic search algorithms.
It expands nodes based on their heuristic value h(n).
It maintains 2 lists: OPEN and CLOSED(expanded).

If we use both lists it is called Graph search and Tree Search if only use OPEN (might lead to infinite loops). not using might cause infinite loops as in greedy search below.

##### Best First Search Algorithm (Greedy Search)
Always selects the best (most promising) path at the moment.
- a combination of DFS and BFS.

We expand the node which is closest to the goal node and the closest cost is estimated by heuristic function.
- implemented by a priority queue.

It is more efficient than both BFS and DFS.
It is **not Optimal** and **Not Complete** as DFS because it can get stuck in a loop (here we say we are building a tree search but we are not assumed to be searching a tree b/c trees can't have loops instead we are searching a graph and we are building a tree in memory for the path as we explore it).

When we say "Tree Search," we do not mean "searching inside a tree." We mean "searching a graph as if it were a tree."

It is **incomplete** even in finite space and also **not optimal**. 
Time and Space complexity is $O(b^m)$.

Uses OPEN and CLOSED lists for tree search (if it uses CLOSED it is complete).

##### A* Search Algorithm
Most commonly known form of best-first search.
It uses the heuristic function `f(n)` and the *path cost* to reach the node n from the start state `g(n)`. 

It is a combination of UCS and greedy search.
A* algorithm is similar to UCS except that it uses `g(n)+h(n)` instead of `g(n)`.
- `g(n)+h(n)` - is called the *fitness number*.

It is the best algorithm than other search algorithms.
- It is *optimal* and *complete*.
- can solve very complex problems.

BUT:
- it does not always produce the shortest path as it is again based on heuristic/ approximations.
- is complex
- has large memory requirement for CLOSED, not practical for large-scale problems.

The efficiency of A* algorithm depends on the quality of heuristic.

A* algorithm is **complete** as long as:
- Branching factor is finite.
- Cost at every action is fixed.
A* search algorithm is **optimal** if it follows below two conditions:
- *Admissible*: h(n) should be an admissible(optimistic in nature) heuristic for A* tree search. 
- *Consistency*: Second required condition is consistency for only A* graph search.
	- In plain English: The estimated cost to reach the goal from here ($n$) must be no greater than the cost of taking one step to a neighbor ($n'$) plus the estimated cost from there.

Time and Space complexity is $O(b^d)$.


##### Hill Climbing Algorithm in Artificial Intelligence
A local search algorithm which continuously moves in the direction of increasing elevation/value to find the peak of the mountain or best solution to the problem.
One of the widely discussed examples of Hill climbing algorithm is Traveling-salesman Problem in which we need to minimize the distance traveled by the salesman.

Also called greedy local search as it only looks to its good immediate neighbor state and not beyond that.
A node has two components, state and value.

Hill climbing is used when a good heuristic is a value.
In this algorithm, we don't need to maintain and handle the search tree or graph as it only keeps a single current state.

Features:
- It is a variant of the `Generate and Test Method`.
- It is a greedy algorithm, it optimizes for cost.
- No backtracking, b/c it doesn't remember previous states.

**State-space Diagram for Hill Climbing**
The state-space landscape is a graphical representation of the hill-climbing algorithm which is showing a graph between various states of algorithm and Objective function/Cost.

Objective function(to find Global and local max) or cost function(to find Global and local min) on the Y-axis and state space on X-axis.

D/T regions in state space landscape
- Local Max
- Global Max
- Current state
- Flat local maximum: It is a flat space in the landscape where all the neighbor states of current states have the same value.
- Shoulder: It is a plateau region which has an uphill edge.
![[Pasted image 20251120153705.png]]

###### Types of Hill Climbing Algorithm
 **1. Simple Hill Climbing**

Most straightforward version. It's like climbing a hill in the dark, just find the first path that goes up.

It examines only **one** successor node at a time. If the successor's heuristic value (or objective function value) is better than the current node's, the algorithm immediately moves to that successor. It doesn't wait to compare it with other potential moves.

Steps
1.  **Evaluate** the current state ($n$).
2.  **Generate** a single successor state ($n'$).
3.  **Compare** the successor state ($n'$) with the current state ($n$).
4.  If the successor is **better** (e.g., lower cost or higher value), move to $n'$ and make it the new current state.
5.  If the successor is **not better**, generate another successor and repeat Step 3.
6.  If no better successor can be found after checking all options, the search terminates (a **local optimum** is found).

**2. Steepest-Ascent Hill Climbing**

We pause at every point on the hill to check all directions and then choose the path with the greatest upward slope.

It examines **all** successor nodes of the current state and then selects the one that provides the **largest improvement** (the "steepest ascent") over the current state. This makes it more computationally expensive per step than Simple Hill Climbing, but it often finds better paths.

Steps
1.  **Evaluate** the current state ($n$).
2.  **Generate** *all* possible successor states ($\{n'_1, n'_2, \dots\}$).
3.  **Calculate** the heuristic improvement (or change in objective value) for every successor: $\Delta(n, n'_i)$.
4.  **Select** the successor $n'_{best}$ that yields the maximum positive improvement.
5.  If the improvement $\Delta(n, n'_{best})$ is **positive**, move to $n'_{best}$.
6.  If no successor provides an improvement, the search terminates (a **local optimum** is found).

**3. Stochastic Hill Climbing**

Stochastic Hill Climbing is a randomized approach often used when the search space is too large to check every possible move.

Instead of systematically checking all neighbors (like Steepest-Ascent) or the first improving one (like Simple), it **chooses a successor randomly** from the available neighbors. The probability of choosing a successor is usually weighted by the quality of the improvement it offers (i.e., better moves have a higher chance of being selected, but suboptimal moves are still possible).

Steps
1.  **Evaluate** the current state ($n$).
2.  **Generate** a set of successor states ($\{n'_1, n'_2, \dots\}$).
3.  **Assign a probability** to each successor based on the quality of its improvement (e.g., a move that improves the value by 10 has a higher chance of being picked than one that improves it by 2).
4.  **Select** a successor $n'$ based on this probability distribution (a randomized choice).
5.  If the selected successor $n'$ is **better** than the current state, move to $n'$.
6.  If no better successor can be found, the search terminates.


###### Problems in Hill Climbing Algorithm

|                  | Description                                                                                                                                                                              | Solution                                                                                                                                                                                                |
| :--------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1. Local Maximum | The search gets **stuck on a peak** that is better than all immediate neighbors, but it is not the true highest peak (global maximum).                                                   | Use **Backtracking** to remember previously promising paths, allowing the algorithm to return and explore a different direction.                                                                        |
| 2. Plateau       | The algorithm reaches a **flat area** where all neighboring states have the exact same value, preventing it from finding a better direction to move.                                     | Take **large steps** or randomly jump to a distant state to potentially exit the flat region and find a new slope.                                                                                      |
| 3. Ridges        | The search encounters a **steep, narrow area** that slopes upward, but moving towards the optimal direction requires making two or more simultaneous moves that the algorithm can't see. | Use **bidirectional search** (searching from both the start and goal) or allow the algorithm to make **multiple moves** in different directions simultaneously (e.g., using a sequence of small steps). |


##### Simulated Annealing
A hill climbing algorithm w/c always goes up and never down is guaranteed to be incomplete b/c of a local maximum.
And if algorithm applies a random walk, by moving a successor, then it may complete but not efficient.

Simulated Annealing is an **informed search algorithm** that extends Hill Climbing by using **randomness** to escape local optimum solutions and find the **global optimum**.

It's inspired by the metallurgical process of **annealing**, where a material is slowly cooled.

The core idea is controlled risk-taking:
* **Temperature ($T$)**: SA introduces a control parameter called temperature.
* **High $T$ (Start)**: The algorithm behaves randomly, accepting **bad (downhill) moves** with a high probability to explore the search space broadly.
* **Low $T$ (End)**: The algorithm becomes highly selective(greedy), only accepting good moves. It converges to a stable solution like a greedy Hill Climber.

The probability of accepting a bad move decreases exponentially as the temperature drops, ensuring the search explores widely at the start but locks onto a good solution at the end.


### Means-Ends Analysis in Artificial Intelligence

Means-Ends Analysis is a powerful problem-solving strategy in AI that **combines both forward and backward search** to efficiently solve complex problems. It was first implemented in the **General Problem Solver (GPS)** program by Allen Newell and Herbert A. Simon.

The core principle is to repeatedly select an action (operator) that **reduces the most significant difference** between the current state and the desired goal state.

Steps
The MEA process is applied recursively until the current state matches the goal state. Let **CURRENT** be the current state and **GOAL** be the final state.

1.  **Compare and Check:**
    * Compare **CURRENT** to **GOAL**. If there are no differences, the problem is solved. Return **Success** and Exit.
2.  **Select Difference:**
    * If differences exist, select the **most significant difference** between the two states.
3.  **Choose Operator:**
    * Select a relevant **operator (O)** whose intended effect is to reduce that specific difference. If no such operator exists, signal Failure.
4.  **Evaluate Application (Sub0goaling):** 
    * Attempt to apply the operator **O** to **CURRENT**. If the preconditions for O are **not satisfied** at the current state, a **subproblem** is created. This technique is called **Operator Sub-goaling**.
5.  **Solve Subproblems:** 
    * **Backward Search (First Part):** Recursively call MEA to solve the subproblem: **MEA(CURRENT, O-Start)**. *(O-Start is the state where O's preconditions are met).* 
    * **Forward Search (Last Part):** If the first part succeeds, recursively call MEA to find the path from the result of the operator application to the goal: **MEA(O-Result, GOAL)**. *(O-Result is the state after O is applied).*
6.  **Combine and Return:**
    * If both the first part and the last part are successful, return **Success**, signaling the final solution is the combination of the **First Part, Operator O, and the Last Part**.


### Adversarial Search (Games)
Adversarial search examines problems where **multiple agents with conflicting goals** operate in the same search space, requiring each agent to **plan against the actions of the others**. This situation is typically modeled as a **Game**.

*Core Concept*:
Unlike single-agent search (which finds a sequence of actions), adversarial search requires considering the opponent's best possible response to every move, aiming to **maximize** one's own gain while assuming the opponent is trying to **minimize** it.

Types of Games in AI
Games are categorized based on two main factors:
1.  **Information (What agents know):** 
    * **Perfect Information:** Agents can see the complete state of the game (e.g., Chess, Go, Checkers).
    * **Imperfect Information:** Agents do not have full knowledge of the game state or the opponent's moves (e.g., Poker, Battleships).

2.  **Move (How the game changes state):** 
    * **Deterministic:** Games follow strict rules with no element of chance or randomness (e.g., Chess, Tic-Tac-Toe).
    * **Non-deterministic (Stochastic):** Games involve unpredictable events, such as dice rolls or card draws, introducing chance or luck (e.g., Backgammon, Monopoly).

### Zero-Sum Games

Zero-Sum Games are a specific type of **adversarial search** characterized by **pure competition**, where the agents' interests are perfectly opposed.

*Core Principles* 
* **Utility Balance:** The core definition is that one agent's gain in utility is exactly balanced by the other agent's loss, meaning the sum of utilities for all players is always zero.
    * *Example:* If Player A wins (+1), Player B must lose (-1), resulting in a sum of $1 + (-1) = 0$. 
* **Opposing Goals:** One player (often called **MAX**) attempts to **maximize** the utility function, while the opponent (often called **MIN**) attempts to **minimize** it.
* **Examples:** Classic games like Chess and Tic-Tac-Toe are common examples of Zero-Sum Games.
* **Ply:** Each move made by one player in the game is called a **ply**.

*Embedded Thinking* 
Solving Zero-Sum Games requires **embedded thinking** (or backward reasoning) because each player must account for the opponent's rational actions.
* **Recursion:** Each player must think: "If I make this move, what will my opponent do? And if they do that, what will I do next?"
* **Backward Reasoning:** This process typically involves solving the problem **backwards** from the terminal (end) states of the game, anticipating the opponent's best counter-move at every step.

*Formalization of a Game Problem* 
A game is formalized in AI as a search problem using the following components:

| Element              | Description                                                                                    |
| :------------------- | :--------------------------------------------------------------------------------------------- |
| **Initial State**    | The starting setup of the game.                                                                |
| **Player(s)**        | Identifies which player is currently making a move.                                            |
| **Action(s)**        | The set of legal moves available from the current state.                                       |
| **Result(s, a)**     | The transition model; the state resulting from action ($a$) in state ($s$).                    |
| **Terminal-Test(s)** | Checks if the game is over (ends in a terminal state).                                         |
| **Utility(s, p)**    | The **payoff function**; gives a final numeric value for player ($p$) in terminal state ($s$). |
* *Example (Chess):* Utility outcomes are typically $\mathbf{+1}$ (win), $\mathbf{0}$ (loss), or $\mathbf{1/2}$ (draw).




# CH3: Knowledge Representation and Reasoning
### Knowledge Representation
The part of AI concerned with how agents think and how thinking contributes to their intelligent behavior. it is responsible for representing real world information in a computer understandable way to solve real world problems.
- not just storing data but also allows an intelligent machine to learn from that knowledge and experiences.

**DIKW Pyramid** 
*DIKW Pyramid* (Data, Information, Knowledge, Wisdom), is a model used to describe the hierarchical relationship between different levels of understanding. Based on the adaptation of Russell Ackoff’s 1989 work, the pyramid breaks down as follows:
1. The Four Levels
	* **Data (Base):** Discrete, objective facts or observations (symbols/characters) with no inherent meaning. It represents "Nothing" in terms of context and involves "Collecting the parts."
	* **Information:** Data that has been related to other data through context to become useful. It answers the question **"What?"** and involves "Connecting the parts."
	* **Knowledge:** Information that is culturally understood to provide insight and understanding. It answers **"How?"** or **"Why is?"** and involves the "Formation of a whole."
	* **Wisdom (Apex):** The utilization of accumulated knowledge to make informed decisions. It answers **"Why do?"** or **"What is best?"** and involves "Joining the wholes."
2. Key Dimensions
	The pyramid is categorized by two primary axes shown on the sides:
	* **Temporal Focus:** The bottom three layers (Data, Information, Knowledge) are rooted in the **Past**, while Wisdom is oriented toward the **Future**.
	* **Context and Understanding:** As you move up the pyramid, you transition from having no context to understanding the full context.
	* **Left side:** Focuses on what questions are answered (from "Nothing" to "Why").
	* **Right side:** Focuses on the structural process (from "Collecting parts" to "Joining wholes").

3. Core Logic
	The progression represents a shift from **raw inputs** to **actionable insight**. While the base is broad and consists of many disconnected facts, the top is narrow, representing the refined ability to apply judgment and vision.
example:

| Level           | Example Element           | Transition Process   |
| --------------- | ------------------------- | -------------------- |
| **Data**        | 140                       | Gathering raw facts  |
| **Information** | 140 BPM (Resting)         | Adding context/units |
| **Knowledge**   | This is dangerously high. | Analyzing patterns   |
| **Wisdom**      | Administer medicine now.  | Exercising judgment  |

**What to Represent:** 
- Object: facts about objects in the real world.
- Events: actions in the real world.
- Performance: behavior w/c involves knowledge about how to do a thing.
- Meta-Knowledge: it knowledge about what we know.
- Facts: truths in the real world.
- Knowledgebase: the central component of knowledge based agents. KB - a group of sentences (sentences != English sentences)

**KRR** 
**Knowledge**: awareness or familiarity gained by experiences of facts, data, and situations.

**Types of Knowledge** 
1. *Declarative (descriptive) K.* - to know about something. - concepts, facts and objects.
2. *Procedural (imperative) K.* - knowledge about how to do something. - rules, strategies, procedures, agendas.
3. *Meta Knowledge* - knowledge about other types of knowledge.
4. *Heuristic K.* - knowledge in some experts in a field or subject. - rules of thumb based on previous experiences, awareness of approaches and w/c are good to work but not guaranteed.
5. *Structural K.* - basic knowledge for problem solving. **r/n ships** like "kind of", "part of", and groupings.


#### The relation between Knowledge and Intelligence
- K. plays an important role in demonstrating intelligent behavior in AI.
```
Sensing -> Decision Maker <- Knowledge
'                  ↓
'                Action
```

**AI Knowledge Cycle** 
AI has components for displaying intelligent behavior:
1. Perception
2. Learning
3. Knowledge Representation and Reasoning
4. Planning Execution
5. Execution
```
|             ↑ -> Learning
|Perception -->      |
|             |     ↓
|             ↓ --> KR ---> <- Rasoning
|                               ↓     |
|                         Planning    |
|                               ↓     ↓
|                              Execution
```
- In the complete cycle, the main components are knowledge representation and reasoning.
- Planning and Execution depend on KR and reasoning.

**Approaches to Knowledge Representation** 
1. *Simple Relational Knowledge* - each fact about a set of objects is set in columns. DB systems. has little opportunity for inference.
2. *Inheritable Knowledge* - data is stored into a hierarchy of classes. and we apply inheritance property. multi-inheritance. we also have instances of those classes. represented with Boxed Nodes and arrows for pointing to values.
3. *Inferential Knowledge* - knowledge in the form of formal logics. used to drive more facts. guaranteed to be correct.
4. *Procedural Knowledge* - small programs on how to do specific things. uses *If-Then* rules. LISP and Prolog use this style. can represent heuristic and domain specific knowledge but not All cases.

**Requirements for Knowledge Representation System** 
KR should have the ability to:
1. *Representational Accuracy* - to represent all kinds of knowledge.
2. *Inferential Adequacy* - to manipulate representational structures to produce new Knowledge.
3. *Inferential Efficiency* - to direct the inferential k. mechanism into most productive directions by storing appropriate guides.
4. *Acquisitional Efficiency* - to acquire the new knowledge easily using automated methods.


#### Techniques of Knowledge Representation
4 ways:
1. Logical Representation
2. Semantic Network R.
3. Frame R.
4. Production Rules

###### 1. Logical Representation
- a language with concreate rules to deal with propositions and has no ambiguity.
- drawing a conclusion based on various conditions.
- consists of syntax and semantics to support a sound inference.

**Syntax** - rules on how to construct a sentence, w/c symbols we can use and how to write them.
**Semantics** - rules by w/c we can interpret the sentence in the logic. assigning meanings to each sentence.

Two main logics in LR:
1. Propositional Logic
2. Predicate Logic

ADV:
- enables logical reasoning.
- is basis for programming languages
DIS:
- has restrictions and are challenging to work with.
- may not be very natural and inferences may not be so efficient.

###### 2. Semantic Network Representation
- an alternative of predicate logic for knowledge representation.
- We represent knowledge in graphical networks.
- This network consists of nodes representing objects and areas w/c describe their relationship.
- easy to understand.
Two types of relations:
- IS-A (inheritance)
- Kind-of-relation

DIS: 
- more computational time traversing trees. and in the worst case the solution may not exist.
- it tries to model human brain(1015 neurons) but it is not practical
- is inadequate as they don't have any equivalent quantifier. e.g. for all, some, none etc.
- Semantic networks do not have any standard definition for the link names.
- These networks are not intelligent and depend on the creator of the system.

ADV:
- are a more natural representation of knowledge.
- they convey meaning in a transparent manner.
- are simple and understandable.

###### 3. Frame Representation (slot-filter knowledge representation)
- Frame is a record like structure which consists of a collection of attributes and values to describe an entity in the world. SLOTS and Slot Values.
- divides knowledge into substructures by representing stereotypes situations.
- Slots have names and values w/c are called facets.
- *Facets*: aspects of a slot. enable us to put constraints on the frames.
- Frames are derived from semantic networks and later evolved into our modern-day classes and objects.  Frames are connected.
- Frames are used in NLP and machine vision.

ADV:
- makes programming easier by grouping related data
- is flexible
- easy to add slots for new attribute and relations
- is easy to include default data and to search for missing values.
- frame representation is easy to understand and visualize.

DIS:
- inference is not easily processed
- frame representation has a much generalized approach

###### 4. Production Rules
- Consists of `(condition, action)` pairs, *"If condition then action"*.
3 Parts:
- set of production rules
- working memory
- the recognize-act-cycle

DIS:
- PR does not exhibit any learning capabilities as it doesn't store results of actions.
- During execution, many rules may be active and hence they are inefficient



### Knowledge-Based Agents in Artificial Intelligence
KB agents have capability of maintaining an internal state of knowledge, reason on the K. and update their KB after observation and taking action.
They can represent the world with some formal representation and act intelligently.

Knowledge-based agents are composed of two main parts:
1. Knowledge-base and 
2. Inference system.

A knowledge-based agent must able to do the following:
- able to represent states, actions, etc.
- able to incorporate new percepts
- update the internal representation of the world
- deduce the internal representation of the world
- deduce appropriate actions

```
Environment -> Inference Engine -> Output
.               ↓          ↑ <------------ Learning (KB update)
.              Knowledge Base (KB)
```

**Knowledge Base**: is a collection of sentences (not English). - Expressed in a language KR. language.
**Inference**: deriving new sentences from Old ones. adding new sentences to KB.
**Sentence**: a proposition about the world. Inference system uses logical rules to deduce new info.

An inference system works mainly in two rules given as **Forward Chaining** and **Backward Chaining**.

###### Operations Performed by KBA
To show intelligent behavior
1. **TELL** - tell the KB what it perceives from the environment.
2. **ASK** - asks the KB what action it should perform.
3. **Perform** - perform selected action.

###### Various Levels of KBAs
1. **Knowledge Level** - the first level, we specify what the agent knows and its goals.
	- with the specifications we FIX its behaviors. e.g. a taxi knows the way to get from A to B

2. **Logical Level** - we understand how the KR of Knowledge is stored. sentences are encoded into different logics.
	- we expect the automated taxi to reach the destination B.
3. **Implementation Level** - physical representation of logic and knowledge.
	- an agent performs actions per logical and knowledge levels.
	- an automated taxi agent actually implement his knowledge & logic so that it can reach the Destination.

###### Approaches to Designing a Knowledge based Agent
Two:
1. **Declarative Approach** - we create KBA by starting with empty KB and telling all the sentences we want to start with.
2. **Procedural Approach** - we directly encode desired behavior as a program code. w/c means we just need to write a program that encodes the desired behavior.

We can combine both approaches, and declarative knowledge can often be compiled into more efficient procedural code.


### Propositional logic in Artificial Intelligence
**PL** is the simplest form of logic where all the statements are made by propositions.
- Proposition is a declarative statement w/c is either true or false.

Facts about **PL**:
- also called Boolean Logic (0 and 1).
- it consists of an object, relations or function and logical connectives (operators).
- a propositional formula that is always true is a `Tautology` and is a valid sentence. if always false it is a `Contradiction`.

There are two types of propositions:
1. Atomic Propositions - simple, with single proposition symbol. are either true or false. 
	- e.g. `2+2=3` or `The sun is cold.`
2. Compound Propositions - combined atomic propositions using parenthesis and connectives.

**Limitations of PL** 
- We can't represent relations like ALL, Some or None.
- PL has limited expressive power. we can't describe statements based on their properties.

##### Rules of Inference in AI
Inference rules are the templates for generating valid arguments. 
- **Implication**: It is one of the logical connectives which can be represented as $P → Q$. It is a Boolean expression.
- **Converse**: The converse of implication, which means the right-hand side proposition goes to the left-hand side and vice-versa. It can be written as $Q → P$.
- **Contrapositive**: The negation of converse is termed as contrapositive, and it can be represented as $\neg Q → \neg P$.
- **Inverse**: The negation of implication is called inverse. It can be represented as $\neg P → \neg Q$.

**Types of Inference Rules**
1. *Modes Pones*: if P and P → Q is true, then we can infer that Q will be true.$$\frac{P, \quad P \rightarrow Q}{\therefore Q}$$ 
2. *Modes Tollens*: if p → Q is true and ¬ Q is true then ¬P will also be true.$$\frac{P \rightarrow Q, \quad \neg Q}{\therefore \neg P}$$
3. *Hypothetical Syllogism*: P→R is true whenever P→Q is true, and Q→R is true.$$\frac{P \rightarrow Q, \quad Q \rightarrow R}{\therefore P \rightarrow R}$$
4. *Disjunctive Syllogism*: if P∨Q is true, and ¬P is true, then Q will be true.$$\frac{P \vee Q, \quad \neg P}{\therefore Q}$$ 
5. *Addition*: that If P is true, then P∨Q.$$\frac{P}{\therefore P \vee Q}$$
6. *Simplification*: if P∧ Q is true, then Q or P will also be true.$$\frac{P \wedge Q}{\therefore P} \quad \text{or} \quad \frac{P \wedge Q}{\therefore Q}$$
7. *Resolution*: if P∨Q and ¬ P∧R is true, then Q∨R will also be true.$$\frac{P \vee Q, \quad \neg P \vee R}{\therefore Q \vee R}$$


### First-Order Logic in Artificial intelligence
Overcomes the shortcomings of Propositional logic.
- FOL is an extension to propositional logic.
- AKA Predicate Logic.
- FOL develops information about the objects in a more easy way and can also express the relationship between those objects.

First-Order Logic (like natural language) does not only assume that the world contains **facts** like propositional logic but also assumes the following things in the world:
- **Objects**: A, B, people, numbers, colors, wars, theories, squares, pits, `wumpus`, ......
- **Relations**: It can be unary relation such as: red, round, is adjacent, or n-any relation such as: the sister of, brother of, has color, comes between
- **Function**: Father of, best friend, third inning of, end of,...

FOS also has Syntax and Semantics.
**Syntax** 
- Constants: 1, 2...
- Variables: x, y, ...
- Predicates: Brother, Father, >
- Function: `sqrt`, `LeftLegOf` 
- Connectives: ∧, ∨, ¬ => <=>
- Equality: ==
- Quantifier: ∀, ∃


**Atomic sentences** - formed from a predicate symbol followed by a parenthesis with a sequence of terms.
Example: 
- Abebe and Taye bare brothers: => Brothers(Abebe, Taye).
- statement: "Socrates is a man. 
	- "Subject: Socrates 
	- Predicate: Man(x) 
	- FOL: $Man(socrates)$ 

**Complex Sentences**:  are made by combining atomic sentences using connectives.
FOL statements can be divided into two parts:
- *Subject*: Subject is the main part of the statement.
- *Predicate*: A predicate can be defined as a relation which binds two atoms together in a statement
E.g. X is an integer.
- "X" - subject
- "is an integer" - predicate


| English Sentence                                | FOL Representation                       |
| ----------------------------------------------- | ---------------------------------------- |
| **"If it is raining, then the ground is wet."** | $Raining(today) \rightarrow Wet(ground)$ |
| **"John is a student and he is smart."**        | $Student(john) \wedge Smart(john)$       |
| **"Alice is not a teacher."**                   | $\neg Teacher(alice)$                    |
| **"It is either Monday or Tuesday."**           | $Day(monday) \vee Day(tuesday)$          |

##### Quantifiers in First-order logic
Symbols that permit to determine or identify the range and scope of the variable in the logical expression. 
2 Types:
A. Universal Quantifier (for all, everyone, everything) 
B. Existential Quantifier (for some, at least one)

**Universal Quantifier (∀)**: specifies that the statement within its range is true for everything or every instance of a particular thing.
- The main connective for universal quantifier ∀ is implication →.

**Existential Quantifiers (∃)**: express that the statement within its scope is true for at least one instance of something. 
- The main connective for existential quantifier ∃ is and ∧.

Properties of Quantifiers:
- In universal quantifier, `∀x∀y` is similar to `∀y∀x`.
- In Existential quantifier, `∃x∃y` is similar to `∃y∃x`.
- `∃x∀y` is not similar to `∀y∃x`.

Example:
- All birds fly. `∀x bird(x) →fly(x)`.
- Every man respects his parent. $\forall x (Man(x) \rightarrow Respects(x, Parent(x)))$.
- Some boys play cricket. $\exists x (Boy(x) \wedge Play(x, Cricket))$.
- Not all students like both Mathematics and Science. `¬∀ (x) [ student(x) → like(x, Mathematics) ∧ like(x, Science)].`
- Only one student failed in Mathematics. $\exists x (Student(x) \wedge Failed(x, Math) \wedge \forall y ((Student(y) \wedge Failed(y, Math)) \rightarrow y=x))$.

**Free and Bound Variables** 
The quantifiers interact with variables which appear in a suitable way. 
There are two types of variables in First-order logic which are given:
- **Free Variable**: A variable is said to be a free variable in a formula if it occurs outside the scope of the quantifier.  Example: $∀x ∃(y)[P (x, y, z)]$, where z is a free variable.
- **Bound Variable**: A variable is said to be a bound variable in a formula if it occurs within the scope of the quantifier.  Example: $∀x [A (x) B(y)]$, here x and y are the bound variables.

##### Knowledge Engineering in First-order logic
KE is the process of constructing a KB in FOL.

**The Knowledge-Engineering Process** 
1. Identify the task
2. Assemble the Relevant Knowledge
3. Decide on Vocabulary
4. Encode general knowledge about the domain
5. Encode a description of the problem instance
6. Pose queries to the inference procedure and get answers
7. Debug the knowledge base

##### Inference in First-Order Logic
Inference is used to deduce new facts or sentences from existing sentences. 
**Terminologies**:
- Substitution - `F[a/x]`, refers to substitute a constant "a" in place of variable "x".
- Equality - Brother (Abebe) = Kebede, the object referred by the Brother (Abebe) is similar to the object referred by Kebede.

**Inference Rules** 
1. **Universal Generalization** - states that if premise P(c) is true for any arbitrary element c in the universe of discourse, then we can have a conclusion as $∀ x P(x)$.
	- x must not appear as a free variable.
	- *Example*: Let's represent, P(c): "A byte contains 8 bits", so for $∀ x P(x)$ "All bytes contain 8 bits.", it will also be true.
2. **Universal Instantiation** / U. elimination - can be applied multiple times to *add* new sentences.
	- new KB is equivalent to old KB.
	- rule state that we can infer any sentence P(c) by substituting a ground term c (a constant within domain x) from ∀ x P(x) for any object in the universe of discourse.
	- If "Every person like ice-cream"=> ∀x P(x) so we can infer that "John likes ice-cream" => P(c)
3. **Existential Instantiation** / E. Elimination - can be applied only once to *replace* the existential sentence.
	- The new KB is not logically equivalent to old KB, but it will be satisfiable if old KB was satisfiable.
	- states that one can infer P(c) from the formula given in the form of ∃x P(x) for a new constant symbol c.
	- The restriction with this rule is that c used in the rule must be a new term for which $P(c)$ is true.
	- e.g. "Greedy Kings are evil", so we will find some x such that x is king, and x is greedy so we can infer that x is evil.
4. **Existential Introduction** - If we know that a specific instance 𝑃(𝑐) is true for some constant 𝑐, we can conclude that there exists at least one element in the universe of discourse for which 𝑃(𝑥) is true.
	- Formally: from 𝑃(𝑐), infer ∃𝑥𝑃(𝑥).
	- Restriction: The constant 𝑐 must be a valid term in the domain. This rule generalizes from a specific case to an existential statement.
	- Example: Premise: "John likes ice-cream" → 𝑃(John). 
		- Conclusion: "There exists someone who likes ice-cream" → ∃𝑥𝑃(𝑥).



| Rule                          | Symbolic Form                            | Key Idea                                     | Example                                               |
| ----------------------------- | ---------------------------------------- | -------------------------------------------- | ----------------------------------------------------- |
| **Universal Generalization**  | From $(P(c)) →$ infer $(\forall x P(x))$ | If true for arbitrary element, true for all  | "A byte contains 8 bits" → "All bytes contain 8 bits" |
| **Universal Instantiation**   | From $(\forall x P(x))$ → infer $(P(c))$ | Apply universal statement to any constant    | "Everyone likes ice-cream" → "John likes ice-cream"   |
| **Existential Instantiation** | From $(\exists x P(x)) →$ infer $(P(c))$ | Replace existential with a new constant      | "Some king is greedy" → "King\_1 is greedy"           |
| **Existential Introduction**  | From $(P(c)) →$ infer $(\exists x P(x))$ | Generalize from a specific case to existence | "John likes ice-cream" → "Someone likes ice-cream"    |

##### Resolution in FOL
Resolution is a single inference rule which can efficiently operate on the Conjunctive Normal Form(CNF) or Clausal Form.
- **Clause**: Disjunction of literals (an atomic sentence) is called a clause. It is also known as a unit clause.
- **Conjunctive Normal Form**: A sentence represented as a conjunction of clauses is said to be conjunctive normal form or CNF.

*The Resolution Inference Rule* 
- a lifted version of the propositional rule. 
- Resolution can resolve two clauses if they contain complementary literals, which are assumed to be standardized apart so that they share no variables.
This rule is also called the binary resolution rule because it only resolves exactly two literals.
**Example**: We can resolve two clauses which are given below:
`[Animal (g(x) V Loves (f(x), x)]` and `[￢ Loves(a, b) V ￢Kills(a, b)]` 
Where the two complimentary literals are: `Loves (f(x), x)` and `￢ Loves (a, b)` 

These literals can be unified with unifier `θ= [a/f(x), and b/x]` , and it will generate a resolvent clause:
`[Animal (g(x) V ￢ Kills(f(x), x)]`.

Steps for Resolution:
1. Conversion of facts into first-order logic.
2. Convert FOL statements into CNF
3. Negate the statement which needs to prove (proof by contradiction)
4. Draw resolution graph (unification).

Skolemization - removing  existential quantifier ∃ and Universal quantifiers when changing FOL to CNF

**Example:** 
- John likes all kind of food.
- Apple and vegetable are food
- Anything anyone eats and not killed is food.
- Anil eats peanuts and still alive
- Harry eats everything that Anil eats.
Prove by resolution that: John likes peanuts.

We first need to convert the English sentences into **First-Order Logic (FOL)** and then into **Clausal Form** (also known as Conjunctive Normal Form). Once we have the clauses, we use resolution to prove the goal by contradiction.

1. Conversion to Logic
First, we define our predicates: $Food(x)$, $Likes(John, x)$, $Eats(person, x)$, $Killed(person)$, and $Alive(person)$.

* **S1:** John likes all kind of food. $\forall x (Food(x) \rightarrow Likes(John, x))$
**Clause 1**: $[\neg Food(x) \lor Likes(John, x)]$ 
* **S2:** Apple and vegetable are food. $Food(Apple)$, $Food(Vegetable)$
**Clause 2**: $[Food(Apple)]$
**Clause 3**: $[Food(Vegetable)]$ 
* **S3:** Anything anyone eats and is not killed is food.$\forall x \forall p (Eats(p, x) \land \neg Killed(p) \rightarrow Food(x))$
**Clause 4**: $[\neg Eats(p, x) \lor Killed(p) \lor Food(x)]$ 
* **S4:** Anil eats peanuts and is still alive. $Eats(Anil, Peanuts)$, $Alive(Anil)$ (Note: $Alive(p) \equiv \neg Killed(p)$)
**Clause 5**: $[Eats(Anil, Peanuts)]$
**Clause 6**: $[\neg Killed(Anil)]$ 
* **S5:** Harry eats everything that Anil eats.$\forall x (Eats(Anil, x) \rightarrow Eats(Harry, x))$
**Clause 7**: $[\neg Eats(Anil, x) \lor Eats(Harry, x)]$ 

2. The Proof (Resolution)

To prove **"John likes peanuts"** ($Likes(John, Peanuts)$), we assume the **negation** is true and look for a contradiction (an empty clause).

**Goal (Negated):** $[\neg Likes(John, Peanuts)]$ (Clause 8)

| Step  | Resolve Clause...                          | With Clause...                                  | Unifier ()    | Resulting Resolvent                            |
| ----- | ------------------------------------------ | ----------------------------------------------- | ------------- | ---------------------------------------------- |
| **1** | 8: $\neg Likes(John, Peanuts)$             | 1:$\neg Food(x) \lor Likes(John, x)$            | $[Peanuts/x]$ | **9: $\neg Food(Peanuts)$**                    |
| **2** | 9: $\neg Food(Peanuts)$                    | 4:$\neg Eats(p, x) \lor Killed(p) \lor Food(x)$ | $[Peanuts/x]$ | **10:$\neg Eats(p, Peanuts) \lor Killed(p)$ ** |
| **3** | 10: $\neg Eats(p, Peanuts) \lor Killed(p)$ | 5:$Eats(Anil, Peanuts)$                         | $[Anil/p]$    | **11: $Killed(Anil)$**                         |
| **4** | 11:$Killed(Anil)$                          | 6:$\neg Killed(Anil)$                           | none          | **[ ] (Contradiction)**                        |

e.g. `∃(x) CSIT(x)->Easy(x)` to CNF

| Step     | Action               | Result               |
| -------- | -------------------- | -------------------- |
| Original | Given formula        | ∃x(CSIT(x)→Easy(x))  |
| Rule 1   | A→B⇒¬A∨B,∃x          | ∃x(¬CSIT(x)∨Easy(x)) |
| Rule 2   | Skolemization (∃x⇒A) | ¬CSIT(A)∨Easy(A)     |

##### Forward Chaining and Backward Chaining in AI
**Horn Clause and Definite clause:** 
Horn clause and definite clause are the forms of sentences, which enables knowledgebase to use a more restricted and efficient inference algorithm. 

*Definite clause* aka *strict horn clause*: A clause which is a disjunction of literals with exactly one positive literal.
*Horn clause*: A clause which is a disjunction of literals with at most one positive literal. Hence all the definite clauses are horn clauses.

Logical inference algorithms use forward and backward chaining approaches, which require KB in the form of the first-order definite clause.

Example: $(¬ p V ¬ q V k)$. It has only one positive literal k.
It is equivalent to $p ∧ q → k$.

**A. Forward Chaining** aka data-driven 
Starts with atomic sentences in the knowledgebase and applies inference rules (Modus Ponens) in the forward direction to extract more data until a goal is reached. 
- It is a bottom-up approach, as it moves from bottom to top.
- It is a process of making a conclusion based on known facts or data, by starting from the initial state and reaches the goal state.
- used in the expert system, such a business, and production rule systems.

**B. Backward Chaining** aka goal-driven approach - top down
Starts with the goal and works backward chaining through rules to find known facts that support the goal.
- top-down approach.
- based on modus ponens inference rule.
- the goal is broken into sub-goals to prove the facts true.
- used in game theory, automated theorem proving tools, inference engines, proof assistants, and various AI applications.
- used a depth-first searching strategy for proof.

### Reasoning in Artificial intelligence
Is the mental process of deriving logical conclusion and making predictions from available knowledge, facts, and beliefs. 
- "Reasoning is a way to infer facts from existing data." 
- It is a general process of thinking rationally, to find valid conclusions. 

**Types of Reasoning** 
1. *Deductive reasoning* - top-down R
	- Moves from **general rules** to a **specific conclusion**. If the premises are true and the logic is valid, the conclusion is guaranteed to be true.
	- Is the foundation of most formal logic and First-Order Logic (FOL).
	-  **Example:** *Rule:* All humans are mortal.
		* *Fact:* Socrates is human.
		* *Conclusion:* Socrates is mortal.
	* **Use in AI:** Expert systems and theorem provers.
2. *Inductive reasoning* - aka cause-effect reasoning / bottom-up R
	- Moves from **specific observations** to a **general conclusion**. It looks for patterns and trends. Unlike deduction, the conclusion is "probable" rather than "certain."
	* **e.g.** *Observation:* All of the pigeons we have seen in the zoo are white. 
		* *Conclusion*: Therefore, we can expect all the pigeons to be white.
	* **Use in AI:** Machine Learning and Neural Networks.
3. *Abductive reasoning* - 
	- starts with single or multiple observations then seeks to find the most likely explanation or conclusion for the observation.
	- an extension of deductive reasoning, but here, the premises do not guarantee the conclusion.
	- **e.g.** *Observation:* The grass is wet.
		* *Possible Causes:* It rained, or the sprinklers turned on.
		* *Abduction:* Since the sky is cloudy, the best explanation is 'it rained'.
	* **Use in AI:** Medical diagnosis systems and troubleshooting software.
4. *Common Sense Reasoning* 
	- an informal form of reasoning gained through experience.
	- simulates the human ability to make presumptions about events which occurs on every day. 
	* **Example:** "If you drop a glass, it will break." (You don't need a physics engine to know this).
5. *Monotonic Reasoning* 
	- Once a conclusion is reached, it **remains true** even if you add more information. The set of "known truths" only grows.
	* **Logic:** Adding  to your knowledge base never invalidates .
	- not useful for the real-time systems as in real time, facts get changed
	- **Example:** Example: Earth revolves around the Sun. It is a true fact, and it cannot be changed even if we add another sentence in knowledgebase like, "The moon revolves around the earth" Or "Earth is not round," etc.
	* **Use in AI:** Traditional logic systems and mathematical proofs.
6. *Non-monotonic Reasoning* 
	- In non-monotonic reasoning, a conclusion can be **invalidated** if new, contradictory information is introduced. 
	- deals with incomplete and uncertain models. This mimics how humans think in the real world.
	* **Logic:** A conclusion is held "by default" until a counter-example is found.
	* **Example:** * *Initial Thought:* Tweety is a bird, so Tweety can fly.
		* *New Fact:* Tweety is a penguin.
		* *Revised Conclusion:* Tweety cannot fly.
	* **Use in AI:** Knowledge representation where defaults and exceptions exist (e.g., common-sense reasoning).


**Summary Table** 

| Type | Reliability | Direction | Best Use Case |
| --- | --- | --- | --- |
| **Deductive** | Certain | General  Specific | Mathematical Proofs |
| **Inductive** | Probable | Specific  General | Machine Learning |
| **Abductive** | Plausible | Result  Cause | Medical Diagnosis |
| **Monotonic** | Permanent | Linear growth | Geometry/Formal Logic |
| **Non-Monotonic** | Revisable | Dynamic updates | Real-world navigation |

**Probabilistic Reasoning**: is a way of knowledge representation where we apply the concept of probability to indicate the uncertainty in knowledge.
- we combine probability theory with logic to handle the uncertainty.




# CH4: Expert Systems
ES - a research domain of AI. It is introduced by researchers at Stanford.
ES is a computer program that is designed to solve complex problems in *a particular domain* at the level of *extra-ordinary human intelligence*, expertise and to provide *decision-making* ability like a human expert.
It performs this by extracting knowledge from its knowledgebase (KB).
ES is concerned with concepts and methods of symbolic inference or reasoning by a computer, and how the *knowledge* used to make those inferences *will be represented*.

ES = Knowledge Based Systems.

The area of human intellectual endeavor to be captured in an expert system is called the **task domain**.
Typical *tasks* are diagnosis, planning, scheduling, configuration and design the reasoning and inference rules according to the user queries.
ES helps in decision making using both **Facts** and **Heuristics** like humans.
- Heuristic knowledge is the less rigorous, more experiential, more judgmental knowledge of performance.  the "art of good guessing."

Building an expert system is known as **knowledge engineering** and its practitioners are called **knowledge engineers**. 
- selects the knowledge representation. and provides the actual knowledge.
- also selects a reasoning method to utilize the knowledge efficiently.
```
Users	-> UI -> Inference Engine
'	        ↑       ↓          ↑ 
Devs------↑     Knowledge Base (KB)
```

#### Characteristics of Expert System
- **High Performance**: for solving complex problems in a domain with high efficiency and accuracy.
- **Understandable**: responds in a way easily understandable by the user. human language input.
- **Reliable**: much reliable for generating an efficient and accurate output.
- **Highly responsive**: provides the result for any complex query within a very short period of time.

#### Capabilities of Expert System
- **Advising**: advising the human being for the query of any domain from the particular ES.
- **Provide decision-making capabilities**: the capability of decision making in its domain.
- **Demonstrate advice**: demonstrating any new products such as its features, specifications, how to use that product, etc.
- **Problem-solving**
- **Explaining a problem**: providing description of an input problem. - making sense of a diagnosed issue. explaining the response.
- **Interpreting the input**: interpreting the input given by the user. understanding what the user is trying to communicate.
- **Predicting results**: It can be used for the prediction of a result.
- **Diagnosis**: e.g. diagnosing a disease without using multiple components as it already contains various inbuilt medical tools.
- *Instructing and assisting human in decision making* 
- *Justifying the conclusion* 
- *Suggesting alternative options to a problem* 

**ES is Incapable of**:
- Substituting human decision makers - but assist in difficult ones.
- Possessing human capabilities
- Producing accurate output for inadequate knowledgebase
- Refining their own knowledge
- No capabilities of thinking and work on the basis of the knowledgebase of the domain.


#### Components of Expert System
3 components
1. **User Interface**
	- How users interact with the ES. 
	- Takes in queries in a readable format and passes it to the inference engine. and show output.

2. **Inference Engine (Rules of Engine)**
	- brain of the ES.
	- it applies *inference rules* to the *KB* to derive a *conclusion* or deduce *new* information.
	Two types of Inference engines:
	1. *Deterministic Inference Engine*: conclusions by this engine are assumed to be true as they are based on *Facts* and *Rules*.
	2. *Probabilistic Inference Engine*: conclusions contain uncertainty in conclusions and based on probability.

	Mods of Inference Engines:
	- *Forward Chaining*: starts from known facts and rules and applies inference rules to add their conclusion to the known facts.
	- *Backward Chaining*: starts from the goal and works backward to prove the known facts.
	
	The Good and the Bad
	- FC allows to conclude anything
	- FC is expensive.
	- BC requires known goals.
	- Premises of B.C directs w/c facts are needed.
	- Rule trace provides explanation.

3. **Knowledgebase** 
	- Storage for knowledge acquired from d/t experts of the particular domain.
	- more knowledge = more precise the ES is.
	- often represented as Facts and Rules.
	- can also be viewed as a collection of objects and their attributes. 

	Components of KB
	- Factual and Heuristic knowledges.
	*Knowledge Representation* - used to formalize the Knowledge stored in KB using If-else rules.
	*Knowledge Acquisition* - extracting, organizing and structuring domain knowledge. rule of acquiring knowledge from domain experts and storing that knowledge in KB.


#### Development of Expert Systems
ES should be fed with expert knowledge. - gathered from experts in the field. is then tested by the experts.

**Participants in the development of ES** 
3 main participants:
- *Experts*: main contributors to the success of ES.
- *Knowledge Engineer*: who gathers knowledge and codifies it/ formalizes it.
- *End-User*: may not be experts


#### Why Expert Systems?
- **No memory Limitations**: can store and memorize as much data and use it at the time of its application.
- **High Efficiency**: If the knowledgebase is updated with the correct knowledge, then it provides a highly efficient output, which may not be possible for a human.
- **Expertise in a domain**: combines different human experiences, and different skills, it provides an efficient output by mixing all the facts and knowledge.
- **Not affected by emotions**: These systems are not affected by human emotions such as fatigue, anger, depression, anxiety, etc.. Hence the performance remains constant.
- **High security**: These systems provide high security to resolve any query.
- **Considers all the facts**: it checks and considers all the available facts and provides the result. 
- **Regular updates improve the performance**: we can improve the performance of the system by updating the knowledge base. for issues or improvements.


#### Advantages of Expert Systems
- These systems are highly reproducible.
- They can be used for risky places where the human presence is not safe.
- Error possibilities are less if the KB contains correct knowledge.
- The performance of these systems remains steady as it is not affected by emotions, tension, or fatigue.
- They provide a very high speed to respond to a particular query.


#### Limitations of Expert Systems
- The response of the expert system may get wrong if the knowledgebase contains the wrong information.
- Like a human being, it cannot produce a creative output for different scenarios.
- Its maintenance and development costs are very high.
- Knowledge acquisition for designing is much difficult.
- For each domain, we require a specific ES, which is one of the big limitations.
- It cannot learn from itself and hence requires manual updates.

#### Applications of Expert Systems
- **In designing and manufacturing domain**: designing and manufacturing physical devices such as camera lenses and automobiles.
- **In the knowledge domain**: primarily used for publishing the relevant knowledge to the users 
- **In the finance domain**: it is used to detect any type of possible fraud, suspicious activity, and advise bankers that if they should provide loans for business or not.
- **In the diagnosis and troubleshooting of devices**: In medical diagnosis, it was the first area where these systems were used.
- **Planning and Scheduling**:- some particular tasks for achieving the goal of that task.

#### When Not to Use Expert Systems
Expert systems are not suitable for all types of domains and tasks: When -

Efficient conventional algorithms are known
- E.g. Sorting is more efficient using conventional algorithms like Quick Sort than using an ES.
The main challenge is computation but not knowledge 
- E.g. Simulating the weather or solving complex mathematical equations primarily involves computational power rather than knowledge-based reasoning.
Knowledge cannot be captured efficiently or used effectively
- E.g. Predicting the outcome of an art contest relies on subjective judgments and aesthetics, which are difficult to capture as explicit rules in an expert system.
Users are reluctant to apply an expert system (e.g., criticality of the task, risk, or security demands): 
- E.g. Pilots may not fully trust an ES to make decisions during critical flight emergencies.



















