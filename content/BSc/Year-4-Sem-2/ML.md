---
title: Machine Learning
---
# CH 1: Overview
Machine learning is a growing technology which enables computers to learn automatically from past data.
For tasks such as image recognition, speech recognition, email filtering, Facebook auto-tagging, recommender system, and many more.

### What is Machine Learning?
Computers or machines work on our instructions. But can a machine also learn from experiences or past data like a human does?
**ML** is said to be a subset of **AI** that is mainly concerned with the development of algorithms which allow a computer to learn from the data and past experiences on their own.

AI is used to make intelligent machines/robots, whereas machine learning helps those machines to train for predicting the outcome without human intervention.

The term *machine learning* was first introduced by Arthur Samuel in 1959 while at IBM. 
- He defined machine learning as “the field of study that gives computers the ability to learn without being explicitly programmed.” 
- However, there is no universally accepted definition for machine learning. 
	1. Tom Mitchell (1998): a computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E.
	2. Machine learning is programming computers to optimize a performance criterion using example data or past experience. model may be predictive or descriptive.
	3. ML is concerned with the question of how to construct computer programs that automatically improve with experience.
	4. ML is the study of computer algorithms for automatically constructing computer software through past experience and training data.
	5. It is a branch of AI and CS that helps build a model based on training data and make predictions and decisions without being constantly programmed.

With the help of sample historical data, which is known as *training data*, machine learning algorithms build a mathematical model that helps in making predictions or decisions without being explicitly programmed. 
The more we will provide the information, the higher will be the performance. 

**Why ML?** 
A) It is very hard to write programs that solve problems like recognizing a face. 
- We don’t know what program to write because we don’t know how our brain does it. 
- Even if we had a good idea about how to do it, the program might be very complicated. 
B) Instead of writing a program by hand, we collect lots of examples that specify the correct output for a given input.
C) A ML algorithm then takes these examples and produces a program that does the job. 
- The program produced by the learning algorithm may look very different from a typical hand-written program. It may contain millions of numbers. 
- If we do it right, the program works for new cases as well as the ones we trained it on.

Some more examples of tasks that are best solved by using a learning algorithm. 
A) **Recognizing Patterns**: 
- Facial identities or facial expressions
- Handwritten or Spoken words 
- Medical images 
B) **Generating Patterns**: 
- Generating images or motion sequences
C) **Recognizing Anomalies**: 
- Unusual sequences of credit card transactions 
- Unusual patterns of sensor readings in a nuclear power plant or unusual sound in your car engine. 
D) **Prediction**: 
- Future stock prices or currency exchange rates 

##### How does Machine Learning Work? 
Machine Learning systems use historical data to build predictive models. Whenever the system receives new information, it uses these models to predict an outcome. A fundamental rule of ML is that accuracy scale with volume: **more data → more accurate predictions.** 

$$\text{Input Past Data} \xrightarrow{\text{Training}} \text{ML Algorithm} \rightarrow \text{Logical Model} \xrightarrow{\text{New Data}} \text{Output}$$

**The Data Process** 
Machine learning utilizes massive datasets through a process called **data pre-processing**. This allows the system to handle different types of information:
* **Structured:** Highly organized (like spreadsheets or CSV).
* **Semi-structured:** Partially organized (like XML or JSON files).
* **Unstructured:** Raw data (like images or text).
Once processed, this data is fed into specific algorithms. The machine analyzes previous trends within that data to automatically predict future outputs.

**Features of ML** 
* **Pattern Detection:** Uses data to identify complex relationships within a dataset.
* **Self-Improvement:** Learns from past experiences to improve its own performance automatically.
* **Data-Driven:** Operates based on evidence and facts found in the data rather than static programming.
* **Big Data Focus:** Similar to data mining, it is designed to manage and extract value from huge amounts of information.

##### Need for Machine Learning
Machine Learning is essential for tasks that are too complex or vast for humans to handle directly. While we have physical and cognitive limitations in processing massive datasets manually, ML algorithms thrive on scale. 
By providing these algorithms with huge amounts of data, they can explore, model, and predict outputs automatically.

**Real-World Applications** 
* **Self-driving cars** and **Face recognition**.
* **Cyber fraud detection** in banking.
* **Recommendation engines** used by Netflix and Amazon.
* **Social media suggestions** (e.g., Facebook friend suggestions).

**Key Importance of ML** 
* **Data Growth:** Manages the rapid increment in global data production.
* **Complexity:** Solves problems that are too difficult for manual human implementation.
* **Decision Making:** Provides accurate, automated choices in sectors like finance.
* **Hidden Insights:** Finds patterns and extracts useful information from raw data.

##### History of Machine Learning 
The following are some milestones which have occurred in the history of machine learning: 
The Early History of Machine Learning (Pre-1940).
* **1834:** Charles Babbage conceived the first programmable device using punch cards.
* **1936:** Alan Turing theorized how machines determine and execute instructions.

The Era of Stored Program Computers
* **1940:** ENIAC, the first electronic general-purpose computer, was invented.
* **1943:** Scientists first modeled human neural networks using electrical circuits.

Computer Machinery and Intelligence
* **1950:** Alan Turing published his seminal paper asking, "Can machines think?"

Machine Intelligence in Games
* **1952:** Arthur Samuel created a checkers program that improved through play.
* **1959:** Arthur Samuel officially coined the term "Machine Learning."

The First "AI" Winter
* **1974-1980:** Funding and interest collapsed due to failed machine translation goals.

Machine Learning from Theory to Reality
* **1959:** Neural networks were first applied to remove echoes on phone lines.
* **1985:** `NETtalk` taught itself to correctly pronounce 20,000 words in one week.
* **1997:** IBM’s Deep Blue became the first computer to beat a human chess champion.

Machine Learning at 21st Century
* **2006:** Geoffrey Hinton rebranded neural net research as "Deep Learning."
* **2012:** A Google network learned to recognize humans and cats in YouTube videos.
* **2014:** The chatbot `Eugen Goostman` convinced 33% of judges it was human.
* **2014:** Facebook’s `DeepFace` achieved human-level precision in facial recognition.
* **2016:** AlphaGo defeated world-class Go players `Lee Sedol` and `Ke Jie`.
* **2017:** Alphabet's Jigsaw system learned to identify and stop online trolling.

**Machine Learning at Present**:
Self-driving cars, Amazon Alexa, Catboats, recommender system, and many more. Modern machine learning models can be used for making various predictions, including weather prediction, disease prediction, stock market analysis, etc.

### Classification of Machine Learning
At a broad level, machine learning can be classified into three types:
1. **Supervised learning** 
2. **Unsupervised learning** 
3. **Reinforcement learning** 

##### 1) Supervised Learning
Supervised learning is a type of machine learning method in which we provide sample labeled data to the machine learning system in order to train it, and on that basis, it predicts the output.

Supervised learning uses labeled datasets to train a model to map inputs to specific outputs, much like a student learning under a teacher's guidance. Once processed, the model is tested with sample data to verify its predictive accuracy, with spam filtering serving as a primary example.

Supervised learning can be grouped further in two categories of algorithms: 
- Classification 
- Regression

##### 2) Unsupervised Learning 
Unsupervised learning uses unlabeled data to find hidden patterns or structures without human guidance or predetermined results. Its goal is to group similar data or extract new features, primarily through two methods: 
- Clustering
- Association.

##### 3) Reinforcement Learning 
Reinforcement learning is a feedback-based learning method, in which a learning agent gets a reward for each right action and gets a penalty for each wrong action. The agent learns automatically with these feedbacks and improves its performance. 
The agent interacts with the environment and explores it. The goal of an agent is to get the most reward points, and hence, it improves its performance. The robotic dog, which automatically learns the movement of his arms, is an example of Reinforcement learning.

### Applications of Machine learning 
1. **Image Recognition:** Facebook’s "Deep Face" uses recognition algorithms to auto-tag people in photos.
2. **Speech Recognition:** Converts voice instructions into text for assistants like Siri and Alexa to follow.
3. **Traffic Prediction:** Google Maps uses real-time GPS data and history to predict congestion and routes.
4. **Product Recommendations:** Amazon and Netflix analyze your activity to suggest relevant shopping or viewing content.
5. **Self-Driving Cars:** Tesla utilizes unsupervised learning to train models to detect and avoid obstacles.
6. **Email Spam/Malware Filtering:** Algorithms like Naive Bayes automatically sort inbox mail and block potential threats.
7. **Virtual Personal Assistants:** Tools like Google Assistant use ML to execute tasks based on voice commands.

### Machine learning Life cycle
Machine learning has given the computer systems the abilities to automatically learn without being explicitly programmed. 
Machine learning life cycle is a cyclic process to build an efficient machine learning project. The main purpose of the life cycle is to find a solution to the problem or project.

Machine learning life cycle involves about seven major steps. 
- Gathering Data 
- Data preparation 
- Data Wrangling 
- Analyze Data 
- Train the model 
- Test the model 
- Deployment 

Before starting the life cycle, we need to understand the problem because the good result depends on the better understanding of the problem.

In the complete life cycle process to solve a problem, we create a machine learning system called
"model", and this model is created by providing "training". But to train a model, we need data. Hence, life cycle starts by collecting data.

##### 1. Gathering Data
To identify and obtain all data-related to the problem. 
Data can be collected from various sources such as files, database, Internet, or mobile devices. The quantity and quality of the collected data will determine the efficiency of the output. The more data, the more accurate will be the prediction. 
This step includes the following tasks: 
- Identify various data sources 
- Collect data 
- Integrate the data obtained from different sources 

By performing the above task, we get a coherent set of data, also called as a **dataset**.

##### 2. Data Preparation 
Data preparation is a step where we put our data into a suitable place and prepare it to use in our machine learning training. 
In this step, first, we put all data together, and then *randomize* the ordering of data. 
This step can be further divided into two processes: 
- *Data exploration*: It is used to understand the nature of data that we have to work with. The characteristics, format, and quality of data. 
	- A better understanding of data leads to an effective outcome. 
	- In this, we find Correlations, general trends, and outliers. 
- *Data pre-processing*: Now the next step is preprocessing of data for its analysis. 

##### 3. Data Wrangling 
The process of cleaning and converting raw data into a useable format. The process of cleaning the data, selecting the variable to use, and transforming the data in a proper format to make it more suitable for analysis in the next step. 
Cleaning of data is also required to address the quality issues. 
In real-world applications, collected data may have various issues, including: 
- Missing Values 
- Duplicate data 
- Invalid data 
- Noise 
So, we use various filtering techniques to clean the data. It is mandatory to detect and remove the above issues because it can negatively affect the quality of the outcome.

##### 4. Data Analysis 
This step involves: 
- Selection of analytical techniques 
- Building models 
- Review the result 
The aim of this step is to build a machine learning model to analyze the data using various analytical techniques and review the outcome. 
It starts with the determination of the type of the problems, where we select the machine learning techniques such as Classification, Regression, Cluster Analysis, Association, etc. then build the model using prepared data, and evaluate the model. 
Hence, in this step, we take the data and use machine learning algorithms to build the model. 

##### 5. Train Model
In this step we train our model to improve its performance for better outcome of the problem. We use datasets to train the model using various machine learning algorithms. Training a model is required so that it can understand the various patterns, rules, and, features of the data.

##### 6. Test Model 
Once our machine learning model has been trained on a given dataset, then we test the model. 
We check for the accuracy of our model by providing a test dataset to it. Testing the model determines the percentage accuracy of the model as per the requirement of project or problem.

##### 7. Deployment 
We deploy the model in the real-world system. If the above-prepared model is producing an accurate result as per our requirement with acceptable speed, then we deploy the model in the real system. 
But, before deploying the project, we will check whether it is improving its performance using available data or not. The deployment phase is similar to making the final report for a project.

### Data Science Vs. Machine Learning
Data Science is the study of data cleansing, preparation, and analysis, while machine learning is a branch of AI and subfield of data science. 

D.S and ML are closely related to each other but have different functionalities and different goals. At a glance, Data Science is a field to study the approaches to find insights from the raw data. Whereas, Machine Learning is a technique used by the group of data scientists to enable the machines to learn automatically from the past data.

**What is Data Science?** 
"A field of deep study of data that includes extracting useful insights from the data, and processing that information using different tools, statistical models, and Machine learning algorithms." 
It is a concept that is used to handle big data that includes data cleaning, data preparation, data
analysis, and data visualization. 
A data scientist collects the raw data from various sources, prepares and pre-processes the data, and applies machine learning algorithms, predictive analysis to extract useful insights from the collected data. 

Skills required to be become a Data Scientist 
- An excellent programming knowledge of Python, R, SAS, or Scala. 
- Experience in SQL database Coding. 
- Knowledge of Machine Learning Algorithms. 
- Deep Knowledge of Statistics concepts. 
- Data Mining, cleaning, and visualizing skills. 
- Skills to use Big data tools such as Hadoop. 

**What is Machine Learning?** 
ML is a part of AI and the subfield of Data Science. 
It enables machines to learn from past data and perform a given task automatically. 
ML uses statistical methods to improve the performance and predict the output without being explicitly programmed. 

Skills Needed for the ML Engineer: 
- Understanding and implementation of Machine Learning Algorithms. 
- Natural Language Processing. 
- Good Programming knowledge of Python or R. 
- Knowledge of Statistics and probability concepts. 
- Knowledge of data modeling and data evaluation.

**Where is Machine Learning used in Data Science?** 
The use of machine learning in data science can be understood by the development process or life cycle of Data Science. 
The different steps that occur in Data science lifecycle are as follows:
1. *Business Requirements*: Define the specific problem and goals, such as "increasing sales through recommendations".
2. *Data Acquisition*: Gather the necessary data, including user ratings, comments, and purchase history.
3. *Data Processing*: Clean and transform raw data into a format suitable for analysis.
4. *Data Exploration*: Analyze data patterns to uncover useful insights and trends.
5. *Modeling*: Train and test ML algorithms to build and refine a high-performing model.
6. *Deployment & Optimization*: Launch the model into production and continuously monitor its performance.

**Data Science vs. Machine Learning** 

| Feature        | Data Science                                        | Machine Learning                                  |
| :------------- | :-------------------------------------------------- | :------------------------------------------------ |
| **Main Goal**  | Discovering hidden patterns for business decisions. | Enabling machines to learn and predict from data. |
| **Scope**      | A broad field covering the entire data lifecycle.   | A subfield of Data Science focused on modeling.   |
| **Output**     | Actionable insights and data discovery.             | Predictions and classifications for new data.     |
| **Data Type**  | Works with raw, structured, and unstructured data.  | Primarily requires structured data to function.   |
| **Key Skills** | Big data tools (Hadoop), stats, and programming.    | Algorithms, CS fundamentals, and probability.     |
| **Focus**      | Heavy emphasis on data cleansing and analysis.      | Focus on algorithmic and mathematical complexity. |

### AI vs. ML vs. Deep Learning
**Artificial Intelligence (AI)** 
* **Definition:** The science of creating machines that mimic human intelligence; founded by John McCarthy.
* **Capabilities:** Includes visual perception, speech recognition, decision-making, and translation.
* **Applications:** Spans healthcare, finance, astronomy, gaming, robotics, and data security.

**Machine Learning (ML):** A subfield of AI that uses algorithms to teach machines how to learn and build data-driven applications.

**Deep Learning (DL)** 
* **Definition:** A sub-branch of ML and AI based on multi-layered neural networks inspired by the human brain. "Deep" refers to the the number of layers in a neural network.
* **Mechanism:** Uses massive datasets and neural layers to predict results from structured or unstructured data.
* **Self-Correction:** Automatically fixes prediction errors, whereas standard ML models often require manual adjustment.
* **Applications:** Powers self-driving cars, fraud detection, NLP, photo tagging, and pixel restoration.

# CH 2: Fundamentals of Machine Learning 
Different algorithms can be used in machine learning for different tasks, such as simple linear regression that can be used for prediction problems like stock market prediction, and the KNN algorithm can be used for classification problems. 

### I. Types of Machine Learning Algorithms
Machine Learning Algorithms can be broadly classified into three types: 
1. Supervised Learning Algorithms 
2. Unsupervised Learning Algorithms 
3. Reinforcement Learning algorithm 

##### 1. Supervised Machine Learning
Machines are trained using well "labeled" training data (some input data is already tagged with the correct output), and on basis of that data, machines predict the output. 
Here, the training data provided to the machines work as the supervisor that teaches the machines to predict the output correctly. 
The aim of a supervised learning algorithm is to find a mapping function to map the input `variable(x)` with the output `variable(y)`. 
In the real-world, supervised learning can be used for Risk Assessment, Image Classification, 
Fraud Detection, Spam filtering, etc. 

**How Supervised Learning Works?** 
Models are trained using labeled dataset, where the model learns about each type of data. Once the training process is completed, the model is tested on the basis of test data (a subset of the training set), and then it predicts the output.

Steps Involved in Supervised Learning: 
- First determine the type of training dataset 
- Collect the labeled training data. 
- Split the dataset into training dataset, test dataset, and validation dataset. 
- Determine the input features of the training dataset, which should have enough knowledge so that the model can accurately predict the output. 
- Determine a suitable algorithm for the model, such as SVM, decision tree, etc. 
- Execute the algorithm on the training dataset. 
- Evaluate the accuracy of the model by providing the test set. If the model predicts the correct output, which means our model is accurate.

**Types of Supervised Machine learning Algorithms:** 
*A. Regression* 
Regression algorithms are used if there is a relationship between the input variable and the output variable. It is used for the prediction of continuous variables, such as weather forecasting, Market Trends, etc. Popular regression algorithms which come under supervised learning: 
- Linear Regression 
- Regression Trees 
- Non-Linear Regression 
- Bayesian Linear Regression 
- Polynomial Regression 

*B. Classification* 
Classification algorithms are used when the output variable is categorical, which means there are classes such as Yes-No, Male-Female, True-false, Low-Middle-High etc. e.g. Spam Filtering, 
- Decision Trees 
- Random Forest 
- Logistic Regression 
- Support Vector Machines 

**Advantages of Supervised learning:** 
- With the help of supervised learning, the model can predict the output on the basis of prior experiences. 
- In supervised learning, we can have an exact idea about the classes of objects. 
- Supervised learning model helps us to solve various real-world problems such as fraud detection, spam filtering, etc.
 
**Disadvantages of Supervised learning:** 
- Supervised learning models are not suitable for handling the complex tasks. 
- Supervised learning cannot predict the correct output if the test data is different from the training dataset. 
- Training required lots of computation times. 
- In supervised learning, we need enough knowledge about the classes of object. 

##### 2. Unsupervised Machine Learning
There may be many cases in which we do not have labeled data and need to find the hidden patterns from the given dataset. 
It can be compared to learning which takes place in the human brain while learning new things.

Unsupervised learning is a type of machine learning in which models are trained using unlabeled 
dataset and are allowed to act on that data without any supervision. 

Unsupervised learning cannot be directly applied to a regression or classification problem because unlike supervised learning, we have the input data but no corresponding output data. The goal of unsupervised learning is to find the underlying structure of dataset, group that data according to similarities, and represent that dataset in a compressed format. 

*Example*: Suppose the unsupervised learning algorithm is given an input dataset containing images of different types of cats and dogs. The algorithm is never trained upon the given dataset, which means it does not have any idea about the features of the dataset. The task of the unsupervised learning algorithms is to identify the image features on their own. Unsupervised learning algorithm will perform this task by clustering the image dataset into the groups according to similarities between images. 

**Why?** 
The importance of Unsupervised Learning: 
- Unsupervised learning is helpful for finding useful insights from the data. 
- Unsupervised learning is much similar as a human learns to think by their own experiences, which makes it closer to the real AI. 
- Unsupervised learning works on unlabeled and uncategorized data which make unsupervised learning more important. 
- In real-world, we do not always have input data with the corresponding output so to solve such cases, we need unsupervised learning

**Working of Unsupervised Learning** 
$$\text{Unlabled Data} \xrightarrow{\text{Interpretaion}} \text{Algorithm} \xrightarrow{\text{Processing}} \text{Classified Data}$$
We take an unlabeled input data (not categorized) and corresponding outputs are also not given. Now, this unlabeled input data is fed to the machine learning model in order to train it.
Firstly, it will interpret the raw data to find the hidden patterns from the data and then will apply suitable algorithms such as k-means clustering, Principle Component Analysis...
Once it applies the suitable algorithm, the algorithm divides the data objects into groups according to the similarities and difference between the objects. 

**Types of Unsupervised Learning Algorithm:** 
- *Clustering*: a method of grouping the objects into clusters such that objects with most similarities remains into a group and has less or no similarities with the objects of another group. Cluster analysis finds the commonalities between the data objects and categorizes them as per the presence and absence of those commonalities. 
- *Association*: an unsupervised learning method which is used for finding the relationships between variables in the large database. It determines the set of items that occurs together in the dataset. Association rule makes marketing strategy more effective. Such as people who buy X item (suppose a bread) are also tend to purchase Y (Butter/Jam) item. A typical example of Association rule is Market Basket Analysis. 

The following is the list of some popular unsupervised learning algorithms: 
- K-Means Clustering 
- Hierarchal Clustering 
- Anomaly Detection 
- Neural Networks 
- Principle Component Analysis 
- Independent Component Analysis 
- Apriori Algorithm 
- Singular Value Decomposition 

**Advantages of Unsupervised Learning** 
- Unsupervised learning is used for more complex tasks as compared to supervised learning because, in unsupervised learning, we don't have labeled input data. 
- Unsupervised learning is preferable as it is easy to get unlabeled data in comparison to labeled.

**Disadvantages of Unsupervised Learning** 
- Unsupervised learning is intrinsically more difficult than supervised learning as it does not have corresponding output. 
- The result of the unsupervised learning algorithm might be less accurate as input data is not labeled, and algorithms do not know the exact output in advance. 

##### Difference between Supervised and Unsupervised Learning

| Feature         | Supervised Learning                              | Unsupervised Learning                         |
| :-------------- | :----------------------------------------------- | :-------------------------------------------- |
| **Data Type**   | Uses **labeled** data (input + output).          | Uses **unlabeled** data (input only).         |
| **Feedback**    | Receives direct feedback to correct predictions. | No feedback mechanism; finds hidden patterns. |
| **Goal**        | Map inputs to outputs to predict new data.       | Discover insights and structures in raw data. |
| **Supervision** | Requires constant human/labeled guidance.        | Learns independently without supervision.     |
| **Categories**  | **Classification** and **Regression**.           | **Clustering** and **Association**.           |
| **Accuracy**    | Generally produces high-accuracy results.        | Results may be less accurate or subjective.   |
| **AI Concept**  | Further from "True AI" (uses pre-taught data).   | Closer to "True AI" (learns from experience). |
| **Algorithms**  | Linear Regression, SVM, Decision Trees..         | K-Means Clustering, KNN, Apriori.             |

##### 3. Reinforcement Learning (RL)
Reinforcement Learning is a feedback-based Machine learning technique in which an agent learns to behave in an environment by performing the actions and seeing the results of actions. For each good action, a positive, and for each bad action, the agent gets negative feedback or penalty. 
- In RL, the agent learns automatically using feedbacks without any labeled data. 
- Since there is no labeled data, so the agent is bound to learn by its experience only. 
- RL solves a specific type of problem where decision making is *sequential*, and the goal is *long-term*, such as game-playing, robotics, etc. 
- The agent interacts with the environment and explores it by itself.
- The agent learns with the process of hit and trial, and based on the experience, it learns to perform the task in a better way. How a Robotic dog learns the movement of his arms is an example of Reinforcement learning. 
- It is a core part of Artificial intelligence, and all AI agent works on the concept of reinforcement learning. Here, we do not need to pre-program the agent, as it learns from its own experience without any human intervention. 

**Terms Used in Reinforcement Learning** 
- `Agent()`: An entity that can perceive/explore the environment and act upon it. 
- `Environment()`: A situation in which an agent is present or surrounded by. In RL, we assume the *stochastic* environment, which means it is *random in nature*. 
- `Action()`: Actions are the moves taken by an agent within the environment. 
- `State()`: a situation returned by the environment after each action taken by the agent. 
- `Reward()`: A feedback returned to the agent from the env., to evaluate the action of the agent.
- `Policy()`: is a strategy applied by the agent for the next action based on the current state. 
- `Value()`: It is expected long-term retuned with the discount factor and opposite to the short-term reward. 
- `Q-value()`: It is mostly similar to the value, but it takes one additional parameter as a current action (a).

**Key Features of Reinforcement Learning** 
- In RL, the agent is not instructed about the environment and what actions need to be taken. 
- It is based on the *hit and trial* process. 
- The agent takes the next action and changes states according to the feedback of the previous action. 
- The agent may get a delayed reward. 
- The environment is stochastic, and the agent needs to explore it to reach to get the maximum positive rewards.

**Approaches to Implement Reinforcement Learning** 
1. **Value-based**: is about finding the optimal value function, which is the maximum value at a state under any policy. Therefore, the agent expects the long-term return at any state(s) under policy π.
2. **Policy-based**: is about finding the optimal policy for the maximum future rewards without using the value function. In this approach, the agent tries to apply such a policy that the action performed in each step helps to maximize the future reward. 
	There are mainly two types of policy-based approach: 
	- *Deterministic*: The same action is produced by the policy (π) at any state.
	- *Stochastic*: In this policy, probability determines the produced action.

3. **Model-based**: a virtual model is created for the environment, and the agent explores that environment to learn it. There is no particular solution or algorithm for this approach because the model representation is different for each environment.

**Elements of Reinforcement Learning** 
There are four main elements of Reinforcement Learning. 
1. *Policy*: The agent's strategy or rulebook for deciding actions based on the current state. It defines the agent's behavior and can be a simple lookup table or a complex search process.
2. *Reward Signal:* Immediate feedback from the environment (positive or negative) based on an action. The agent's primary goal is to maximize the cumulative reward over time.
3. *Value Function*: A prediction of long-term success. While a reward is immediate, the `value()` estimates the total reward an agent can expect to gather starting from a specific state.
4. *Model*: A representation of the environment's behavior. It allows the agent to predict the next state and reward, helping it plan actions before actually performing them.

**How does Reinforcement Learning Work?** 
We need to consider two main things: 
- *Environment*: It can be anything such as a room, maze, football ground, etc. 
- *Agent*: An intelligent agent such as AI robot. 

**Types of Reinforcement learning** 
There are mainly two types of reinforcement learning, which are: 
* **Positive Reinforcement:** Adding a rewarding stimulus after a desired behavior to increase the likelihood of it happening again. While it creates long-term behavioral changes, excessive reinforcement can lead to state overload and diminished effectiveness.
* **Negative Reinforcement:** Strengthening a specific behavior by removing or avoiding a negative condition. It can be highly effective depending on the context, but typically only encourages enough effort to meet the minimum required behavior.

**Difference between Reinforcement Learning and Supervised Learning** 
The RL agents interact with the environment, explore it, take action, and get rewarded. Whereas supervised learning algorithms learn from the labeled dataset and, on the basis of the training, predict the output.

| Feature              | Reinforcement Learning (RL)                                 | Supervised Learning                                    |
| :------------------- | :---------------------------------------------------------- | :----------------------------------------------------- |
| **Data Source**      | Interacts dynamically with an **environment**.              | Works with a pre-existing, static **dataset**.         |
| **Learning Style**   | Mimics how a brain makes autonomous decisions.              | Mimics a student learning under a guide's supervision. |
| **Dataset Type**     | No labeled dataset is present.                              | A labeled dataset is mandatory.                        |
| **Initial Training** | No previous training; the agent learns via trial and error. | Training is provided upfront to enable predictions.    |
| **Decision Process** | Helps in taking **sequential** decisions over time.         | Decisions are made instantly based on specific inputs. |

**Reinforcement Learning Applications** 
1. *Robotics*: RL is used in Robot navigation, Robo-soccer, walking, juggling, etc. 
2. *Control*: RL can be used for adaptive control such as Factory processes, admission control in telecommunication, and Helicopter pilot is an example of reinforcement learning. 
3. *Game Playing*: RL can be used in Game playing such as tic-tac-toe, chess, etc. 
4. *Chemistry*: RL can be used for optimizing the chemical reactions. 
5. *Business*: RL is now used for business strategy planning. 
6. *Manufacturing*: In various automobile manufacturing companies, the robots use deep reinforcement learning to pick goods and put them in some containers. 
7. *Finance Sector*: The RL is currently used in the finance sector for evaluating trading strategies. 

## II. Popular Machine Learning Algorithms
##### 1. Linear Regression
Popular and used for predictive analysis (prediction of something), and linear regression makes predictions for continuous numbers such as salary, age, etc.

It shows the linear relationship between the dependent and independent variables, and shows how the dependent variable (y) changes according to the independent variable (x).

It tries to best fit a line between the dependent and independent variables, and this best fit line is known as the *regression line*.

The equation for the regression line is: $y= a_0+ a*X$ 
Here, y= dependent variable, X= independent variable, $a_0$ = Intercept of line. 

Linear regression is further divided into two types: 
- *Simple Linear Regression*: In simple linear regression, a single independent variable is used to predict the value of the dependent variable. 
- *Multiple Linear Regression*: In multiple linear regression, more than one independent variables are used to predict the value of the dependent variable. 

##### 2. Logistic Regression 
A supervised learning algorithm which is used to predict the *categorical variables* or *discrete values*. It can be used for the classification problems in machine learning, and the output of the logistic regression algorithm can be either Yes or NO, 0 or 1, Red or Blue, etc. 

Logistic regression is similar to the linear regression except how they are used, Linear regression is used to solve the *regression problem* and predict *continuous* values, whereas Logistic regression is used to solve the *Classification problem* and used to predict the *discrete* values. 

Instead of fitting the best fit line, it forms an *S-shaped curve* that lies between 0 and 1. The S-shaped curve is also known as a *logistic function* that uses the concept of the *threshold*. Any value above the threshold will tend to 1, and below the threshold will tend to 0.

##### 3. Decision Tree Algorithm 
A supervised learning algorithm that is mainly used to solve the classification problems but can also be used for solving the regression problems. It can work with both categorical variables and continuous variables. 
The internal node is used to represent the features of the dataset, branches show the decision rules, and leaf nodes represent the outcome of the problem. 
Some real-world applications of decision tree algorithms are identification between cancerous and non-cancerous cells, suggestions to customers to buy a car, etc.

- *Pruning*: is the process of removing the unwanted branches from the tree.
- *Splitting*: is the process of dividing the decision node/root node into sub-nodes according to the given conditions.
	- **Pure Split:** All samples in a node or resulting subsets are homogeneous, belonging to the same class (classification) or having the same value (regression).
	- **Impure Split:** Resulting subsets contain samples from different classes, meaning they are not homogeneous with respect to the target variable.

##### 4. Support Vector Machine Algorithm 
SVM is a supervised learning algorithm used for *classification* and *regression* problems. However, it is primarily used for classification problems. The goal of SVM is to create a hyperplane or decision boundary that can segregate datasets into different classes. 
The data points that help to define the hyperplane are known as support vectors, and hence it is named as support vector machine algorithm. 
Some real-life applications of SVM are face detection, image classification, Drug discovery, etc. Consider the following diagram: 
![[Pasted image 20260422165710.png]]

##### 5. Naïve Bayes Algorithm
Naïve Bayes classifier is a supervised learning algorithm, which is used to make predictions based on the probability of the object. The algorithm named as Naïve Bayes as it is based on Bayes theorem, and follows the naïve assumption that says' *variables are independent of each other*. 

The Bayes theorem is based on the conditional probability; it means the likelihood that event(A) will happen, when it is given that event(B) has already happened. The equation for Bayes theorem is given as:
$$P(A|B)=\frac{P(B|A)P(A)}{P(B)}$$
- P(A|B) is called as *posterior*, which we need to calculate. It is defined as updated probability after considering the evidence.
- P(B|A) is called the *likelihood*. It is the probability of evidence when hypothesis is true.
- P(A) is called the *prior probability*, probability of hypothesis before considering the evidence
- P(B) is called *marginal probability*. It is defined as the probability of evidence under any consideration.
**Advantages** 
- A Naïve-Bayes classifier algorithm is better than all other models where assumption of independent predictors holds true.
- Easy to implement than other models.
- It requires small amount of training data to estimate the test data which minimize the training time period.
- It can be used for Binary as well as Multi-class Classifications.

**Disadvantages** 
The main disadvantage of using Naïve Bayes classifier algorithms is, it limits the assumption of independent predictors because it implicitly assumes that all attributes are independent or unrelated but in real life it is not feasible to get mutually independent attributes.

##### 6. K-Nearest Neighbor (KNN) 
A supervised learning algorithm used for both **Classification** and **Regression**.
* **Core Principle:** It assumes similarity between new and available data, placing new points into the most similar existing category.
* **"Lazy Learner":** It doesn't learn a model during training; instead, it stores the entire dataset and performs computations only when a new case needs classification.
* **Distance Metrics:** It uses functions like **Euclidean**, **Manhattan**, **`Minkowski`**, or **Hamming** to measure proximity between data points.
* **K-Value:** The "K" represents the number of nearest neighbors checked to determine the majority class for the new data point.

##### 7. K-Means Clustering
A simple unsupervised learning algorithm used to solve clustering problems by grouping data into **K** distinct clusters.
* **Core Logic:** It groups data points based on similarities; items within a cluster share many commonalities, while there are few or no commonalities between different clusters. 
* **Centroid-Based:** Each cluster is defined by a **centroid** (the mean position of all points in that cluster). The algorithm's goal is to minimize the distance between data points and their respective centroids.
* **Iterative Process:** It begins with randomly selected centroids and iteratively shifts them to optimize their positions until the clusters are stable.
* **Use Cases:** spam detection, filtering, and the identification of fake news.

##### 8. Random Forest Algorithm 
A supervised learning algorithm used for both *classification* and *regression* problems. 
* **Ensemble Technique:** It improves model performance by combining predictions from multiple individual classifiers (decision trees).
* **Core Logic:** It builds 64–128 decision trees on different subsets of the data. Each tree "votes" on the classification, and the algorithm selects the **majority vote** as the final output.
* **Accuracy:** A higher number of trees generally leads to higher predictive accuracy and prevents overfitting.
* It is fast, robust, and handles missing or incorrect data more efficiently than single decision trees.

##### 9. `Apriori` Algorithm 
An unsupervised learning algorithm that is used to solve the *association* problems. 
- **Core Logic:** It identifies frequent item sets to generate rules that determine the strength of the connection between different objects.
* **Efficiency:** Uses a **breadth-first search** and **Hash Tree** structure to navigate and calculate item sets iteratively from large datasets.
- The algorithm process iteratively for finding the frequent item sets from the large dataset. 
* **History:** Developed by **R. Agrawal and Srikant in 1994**.
* **Use Cases:** 
	* *Market Basket Analysis*: Identifying products frequently bought together (bread and butter).
	* *Healthcare*: Detecting potential drug reactions in patients based on historical data.

##### 10. Principle Component Analysis 
An unsupervised learning technique, which is used for dimensionality reduction. 
* **Core Logic:** It simplifies datasets with many correlated features by using **orthogonal transformation** to convert them into a smaller set of linearly uncorrelated features (Principal Components).
* It is one of the popular tools that are used for exploratory data analysis and predictive modeling. 
* **Mechanism:** PCA focuses on **variance**. High variance indicates significant information and a better split between classes; by capturing the directions of maximum variance, it can discard less important dimensions without losing the dataset's essence.
* **Primary Uses:** 
	* *Exploratory Data Analysis*: Visualizing high-dimensional data in 2D or 3D.
	* *Preprocessing*: Speeding up other ML algorithms by reducing the number of input variables.
* **Real-World Applications:** Image processing, movie recommendation systems, and optimizing power allocation in communication channels.


### III. Machine Learning Glossary 
* **Sample / Input / Data Point:** A single instance from your dataset (e.g., one specific image in a collection).
* **Prediction / Output:** The value generated by the algorithm (e.g., the machine guessing "0" for a cat).
* **Target / Label:** The "ground truth" or actual correct answer for a specific sample.
* **Loss Value / Prediction Error:** The mathematical distance between the prediction and the target. Lower loss equals higher accuracy.
* **Classes:** The set of possible labels in a dataset (e.g., "Cat" and "Dog").

***Classification & Regression Types*** 
* **Binary Classification:** Choosing between exactly two exclusive categories (e.g., Spam or Not).
* **Multi-class Classification:** Choosing one category from more than two options (e.g., classifying an image as a Dog, Cat, or Bird).
* **Multi-label Classification:** Assigning multiple labels to one sample (e.g., a restaurant tagged as both "Italian" and "Romantic").
* **Scalar Regression:** Predicting a single continuous number (e.g., a house price).
* **Vector Regression:** Predicting multiple continuous numbers simultaneously (e.g., the four coordinates of a bounding box around an object).

***Training Terminologies*** 
* **Batch:** A small group of samples (usually 2 to 256) processed together. The model updates its weights after each batch to learn faster and more efficiently.
* **Epoch:** One full pass of the entire training dataset through the algorithm. Models are typically trained over many epochs to improve accuracy.

### IV. Regression Analysis
Regression analysis is a supervised learning method used to model the relationship between a **dependent variable** (target) and one or more **independent variables** (predictors). It focuses on predicting **continuous/real values** like price, temperature, or salary.
*Key Concepts* 
* **Objective:** To find the "best-fit" line or curve that minimizes the vertical distance (error/ residual) between the actual data points and the predicted line.
* **Correlation vs. Causality:** It identifies how the target variable changes when one predictor is modified while others are held constant, helping determine causal-effect relationships.
* **Applications:** 
	* **Forecasting:** Predicting future trends (e.g., sales growth).
	* **Time Series Modeling:** Analyzing data points collected over time.
	* **Optimization:** Determining which marketing channels yield the highest ROI.

*The Best-Fit Line* 
The strength of a regression model is determined by the distance between the data points and the regression line. A smaller total distance indicates a model that has captured a strong relationship, resulting in higher predictive accuracy.

**Regression Terminologies** 
* *Dependent Variable*: The target you want to predict.
* *Independent Variable*: The predictor used to determine the target.
* *Outliers*: Extreme values that can distort the model's accuracy.
* *Multicollinearity*: When predictors are too highly correlated, making it hard to rank their importance.
* *Underfitting*: Model is too simple; performs poorly on all data.
* *Overfitting*: Model is too complex; excels on training data but fails on new data.

**Why?** 
* *Relationship Estimation*: It quantifies how much the target variable changes in response to specific predictors.
* *Trend Identification*: It surfaces patterns and movements within historical data to forecast future outcomes.
* *Predictive Accuracy*: It is the standard tool for predicting real-world, continuous values like temperature or market prices.
* *Factor Prioritization*: It allows you to determine which variables have the most significant impact on your goal and which can be ignored.

#### Types of Regression 
##### Linear Regression
is a statistical method for predictive analysis that establishes a linear relationship between a dependent variable ($Y$) and an independent variable ($X$). 

***Simple vs. Multiple Regression:*** 
* **Simple Linear Regression** involves only one input variable ($X$).
* **Multiple Linear Regression** involves two or more input variables.

***Mathematical Equation:*** 
**$Y = aX + b$ 
* **$Y$**: Dependent variable (target). 
* **$X$**: Independent variable (predictor). 
* **$a$** and **$b$**: Linear coefficients representing the slope and intercept. 

***Popular Applications:*** 
* **Analyzing trends** and sales estimates.
* **Salary forecasting** based on experience.
* **Real estate prediction** for housing prices.

##### Logistic Regression
is a supervised learning algorithm specifically designed for **classification problems**. Unlike linear regression, which predicts continuous values, logistic regression predicts categorical outcomes in a binary or discrete format, such as 0 or 1, Yes or No, or Spam or Not Spam.
***Core Mechanism:***
* **Probability-Based:** It functions as a predictive analysis algorithm that calculates the probability of a data point belonging to a specific category.
* **Sigmoid Function:** To map any real-valued number into a range between 0 and 1, it uses the **Sigmoid (Logistic) Function**:
$$f(x) = \frac{1}{1 + e^{-x}}$$
* **Thresholding:** It applies a threshold level (commonly **0.5**). Values above this point are rounded to **1**, and values below are rounded to **0**.
* In Logistic regression, instead of fitting a regression line, we fit an *"S" shaped logistic function*, which predicts two maximum values (0 or 1).
* Logistic Regression can be used to classify the observations using different types of data and can easily determine the most effective variables used for the classification.

***Types of Logistic Regression:*** 
* **Binary:** Used when there are only two possible outcomes (e.g., Pass/Fail).
* **Multinomial:** Used when there are more than two unordered categories (e.g., Cats, Dogs, Lions).
* **Ordinal:** Used when categories have a structured order or ranking (e.g., Low, Medium, High).

##### Polynomial Regression
is a type of regression used to model non-linear datasets. While it uses a linear model framework, it fits a non-linear curve to the data points, making it ideal for datasets where a straight line (linear regression) would result in poor accuracy.

***Core Mechanism:*** 
* **Non-Linear Mapping:** It captures relationships where the dependent variable changes at a varying rate relative to the independent variable.
* **Feature Transformation:** Original features are converted into polynomial features of a specific degree (e.g., squaring or cubing the input $x$) before being processed by a linear model.
* **Model Linearity:** Although the resulting curve is non-linear, the model is still considered "linear" because the regression coefficients ($b_n$) are linear.

***Mathematical Equation:*** 
The standard linear equation is expanded into a polynomial form:
$$Y = b_0 + b_1x + b_2x^2 + b_3x^3 + \dots + b_nx^n$$
* **$Y$**: Predicted/target output.
* **$x$**: Independent/input variable.
* **$b_0, b_1, \dots, b_n$**: Regression coefficients.

##### Support Vector Machine (SVM)
* **Primary Use:** Classification tasks. SVM is designed to categorize data points into distinct classes.
* **Goal:** To find an optimal hyperplane (a decision boundary) that best separates data points belonging to different classes in a high-dimensional space. The key is to maximize the *margin* between the hyperplane and the nearest data points (called support vectors) from each class.
* **Output:** Predicts discrete, categorical labels (e.g., "spam" or "not spam," "cat" or "dog," "positive" or "negative sentiment").
* **How it Works:**
    * For linearly separable data, it finds a straight line (or hyperplane in higher dimensions) that divides the classes.
    * For non-linearly separable data, it uses the "kernel trick" to implicitly map the data into a higher-dimensional space where it becomes linearly separable. This allows SVMs to handle complex, non-linear relationships.
* **Key Concepts:**
    * **Hyperplane:** The decision boundary.
    * **Margin:** The area between the hyperplane and the support vectors. Maximizing this margin leads to better generalization.
    * **Support Vectors:** The data points closest to the hyperplane that dictate its position.
    * **Kernel Trick:** A technique to efficiently compute transformations into higher dimensions without explicitly calculating the coordinates in that space.
* **Applications:** Image recognition, spam detection, text classification, facial recognition, bioinformatics.

##### Support Vector Regression (SVR)
is an adaptation of the Support Vector Machine (SVM) algorithm used for continuous variables. While standard SVM finds a line to separate classes, SVR seeks a hyperplane that encompasses the maximum number of data points within a defined margin.

* **Primary Use:** Regression tasks. SVR is used when you want to predict a continuous numerical value.
* **Goal:** To find a hyperplane that best fits the data points, but with a different objective. Instead of maximizing the margin between classes, SVR aims to find a hyperplane that has *at most* a certain margin of error (epsilon, ε) from the actual target values. It tries to fit as many data points as possible within this margin.
* **Output:** Predicts continuous, ordered values (e.g., temperature, stock prices, house prices, sales figures).
*   **How it Works:**
    * SVR works similarly to SVM in that it uses hyperplanes and support vectors. However, the objective function is modified.
    * It defines an *epsilon-tube* around the hyperplane. Data points falling within this tube do not contribute to the error cost. Errors are only penalized if they fall outside this tube.
    * It also utilizes the kernel trick to handle non-linear relationships, allowing it to model complex trends in continuous data.

***Key Terminologies:*** 
* **Kernel:** A mathematical function that maps lower-dimensional data into a higher-dimensional space to find non-linear patterns.
* **Hyperplane:** In SVR, this is the "best-fit" line used to predict continuous values.
* **Boundary Lines:** Two lines situated on either side of the hyperplane that define the **margin**.
* **Support Vectors:** The specific data points that reside closest to the hyperplane or outside the boundary lines, influencing the shape and orientation of the margin.
	![[Pasted image 20260422194733.png|600]]
***Core Objective:*** 
The goal of SVR is to ensure the hyperplane contains the maximum number of data points within the boundary lines (the $\epsilon$-insensitive tube). Unlike other regression models that try to minimize error for every point, SVR ignores errors as long as they are smaller than a specific threshold defined by the boundary lines.

**Core Differences Summarized:** 

| Feature          | Support Vector Machine (SVM)                      | Support Vector Regression (SVR)                   |
| :--------------- | :------------------------------------------------ | :------------------------------------------------ |
| **Problem Type** | Classification                                    | Regression                                        |
| **Objective**    | Maximize the margin between classes               | Minimize error within a specified margin (ε-tube) |
| **Output**       | Discrete class labels                             | Continuous numerical values                       |
| **Error Focus**  | Penalizes misclassifications beyond the margin    | Penalizes predictions outside the ε-tube          |
| **Goal**         | Find optimal separating hyperplane                | Find optimal fitting hyperplane within tolerance  |
In essence, SVR is a adaptation of the SVM algorithm tailored for regression problems. It retains the core ideas of support vectors and hyperplanes but modifies the loss function and objective to predict continuous values rather than discrete classes.

##### Decision Tree Regression
is a supervised algorithm for predicting continuous outcomes using both categorical and numerical data. It organizes information into a hierarchical structure to reach a final value.

***Structure:*** 
* **Root Node:** The starting dataset.
* **Internal Nodes:** Decision points that test specific attributes/ features of the data.
* **Branches:** The paths taken based on test results.
* **Leaf Nodes:** The final predicted result (no further splitting).

***Terms*** 
- *Splitting*: is the process of dividing the decision node/root node into sub-nodes according to the given conditions.
- *Pruning*: Pruning is the process of removing the unwanted branches from the tree in order to get the optimal decision tree. (too-large tree risks overfitting)
	- two types of pruning: - Cost Complexity Pruning - Reduced Error Pruning.

***Process:***
The model repeatedly splits parent nodes into child subsets. This partitioning continues until the data is grouped into final leaves that provide the predicted output.
In order to build a tree, we use the *CART* algorithm, which stands for Classification and Regression Tree algorithm.

**disadvantage** 
 - contains lots of layers, which makes it complex.
- It may have an overfitting issue
- For more class labels, the computational complexity of the decision tree may increase.

***How does the algorithm work?*** 
- Step-1: Begin the tree with the root node, says S, which contains the complete dataset.
- Step-2: Find the best attribute in the dataset using Attribute Selection Measure (ASM).
- Step-3: Divide the S into subsets that contains possible values for the best attributes.
- Step-4: Generate the decision tree node, which contains the best attribute.
- Step-5: Recursively make new decision trees using the subsets of the dataset created in step - 3. Continue this process until a stage is reached where you cannot further classify the nodes and called the final node as a leaf node.

###### A.	Entropy in Machine Learning
Entropy is defined as the randomness or measuring the disorder of the information being processed in Machine Learning.
Entropy is the machine learning metric that measures the unpredictability or impurity in the system.
Entropy is a useful tool in machine learning to understand various concepts such as feature selection, building decision trees, and fitting classification models, etc.
When all observations belong to the same class; then entropy will always be 0. E=−(1log21) = 0.
When entropy becomes 0, then the dataset has no impurity. Datasets with 0 impurities are not useful for learning. Further, if the entropy is 1, then this kind of dataset is good for learning.

###### B.	Attribute Selection Measures (ASM)
Solves "How to select the best attribute for the root node and for sub-nodes.".
Two popular techniques for ASM:
1. *Information Gain* - the measurement of changes in entropy after the segmentation dataset based on an attribute.
	- It calculates how much information a feature provides us about a class.
	- A decision tree algorithm always tries to maximize the value of information gain, and a node/attribute having the highest information gain is split first. 
	- $\text{Information Gain}= \text{Entropy(S)}- [\text{(Weighted Avg)} \times \text{Entropy(each feature)}]$ 
	- $\text{Entropy}(S)= -P(\text{yes})\log_2 P(\text{yes})- P(\text{no}) \log_2 P(\text{no})$ Where, 
		- S= Total number of samples, P(yes)= probability of yes, P(no)= probability of no
2. *Gini Index* - a measure of impurity or purity used while creating a decision tree in the CART (Classification and Regression Tree) algorithm.
	- An attribute with the low Gini index should be preferred as compared to the high Gini index.
	- It only creates binary splits, and the CART algorithm uses the Gini index to create binary splits.
	- $Gini Index= 1- ∑_jP_j^2$ 

**Implementation** 
```
from sklearn.tree import DecisionTreeClassifier
model=DecisionTreeClassifier(criterion="entropy", splitter="best", max_depth=10, random_state=0)
```

##### Random Forest Regression
is a powerful ensemble learning method that combines multiple decision trees to predict a final continuous output.
- Capable of performing both Classification and Regression tasks. but suitable more for classification.
- Capable of handling large datasets with high dimensionality.
- It enhances the accuracy of the model and prevents the overfitting issue.

***Mechanism:*** 
* **Ensemble Learning:** It aggregates the predictions of multiple "base models" (decision trees) and calculates the final output based on the **average** of their results.
* **Bagging (Bootstrap Aggregation):** Trees run in parallel using random subsets of the data. They do not interact with one another during training.
* **Overfitting Prevention:** By training on random data subsets and averaging multiple results, it significantly reduces the risk of overfitting compared to a single decision tree.

***Formal Representation:*** 
The final prediction $g(x)$ is the combined result of all individual tree functions: 
$$g(x) = f_0(x) + f_1(x) + f_2(x) + \dots$$

**Implementation** 
```
from sklearn.ensemble import RandomForestClassifier
model = RandomForestClassifier(criterion="entropy", n_estimators=10)
```
##### Ridge Regression
is a robust version of linear regression that introduces a small amount of bias to improve long-term predictive accuracy. Known as **L2 regularization**, it is specifically designed to handle models with high complexity or multicollinearity.
* **Ridge Penalty:** Calculated by multiplying a regularization parameter ($\lambda$) by the square of the weights of the features.
* **Collinearity Solution:** It excels when independent variables are highly correlated, a scenario where standard linear models typically fail.
* **Complexity Reduction:** It helps stabilize models when the number of parameters exceeds the number of samples.
* **Formula:** $Cost = \sum(y_i - \hat{y}_i)^2 + \lambda \sum w_j^2$

##### Lasso Regression
is a regularization technique known as **L1 regularization**. While similar to Ridge, it uses a different penalty structure that allows for simpler, more interpretable models.
* **Lasso Penalty:** Uses the **absolute value** of the weights rather than their squares.
* **Feature Selection:** Unlike Ridge, which only shrinks weights toward zero, Lasso can shrink weights **exactly to zero**. This effectively removes unimportant features from the model.
* **Formula:** $Cost = \sum(y_i - \hat{y}_i)^2 + \lambda \sum |w_j|$ 

### Perceptron in Machine Learning
Perceptron is a building block of an Artificial Neural Network.
Perceptron is a Machine Learning algorithm for supervised learning of various binary classification tasks. Further, Perceptron is also understood as an Artificial Neuron or neural network unit that helps to detect certain input data computations in business intelligence. 
This algorithm enables neurons to learn elements and processes them one by one during preparation.
Perceptron model is also one of the best and simplest types of *Artificial Neural Networks* (ANNs).
However, it is a supervised learning algorithm of binary classifiers. Hence, we can consider it as a single-layer neural network with four main parameters, i.e., *input values*, *weights* and *Bias*, *net sum*, and an *activation function*.

**Basic Components of Perceptron:** 
- **Input Nodes or Input Layer**: is the primary component of Perceptron which accepts the initial data into the system for further processing. Each input node contains a real numerical value.
- **Weight and Bias**: Weight parameter represents the strength of the connection between units. Weight is directly proportional to the strength of the associated input neuron in deciding the output. Further, Bias can be considered as the line of intercept in a linear equation.
	- The bias in a neural network is an **additional, learnable parameter** that is added to the weighted sum of inputs before the activation function is applied.
- **Activation Function**: These are the final and important components that help to determine whether the neuron will fire or not. Activation Function can be considered primarily as a step function.
	Types of Activation functions:
	- Sign function
	- Step function, and
	- Sigmoid function (s-shaped)

*How does Perceptron Work?* 
The perceptron model begins with the multiplication of all input values and their weights, then adds these values together to create the weighted sum.
Then this weighted sum is applied to the activation function 'f' to obtain the desired output. This activation function is also known as the *step function* and is represented by 'f'.
**Step-1**: In the first step first, multiply all input values with corresponding weight values and then add them to determine the weighted sum. Mathematically, we can calculate the weighted sum as follows: $∑wi*xi = x1*w1 + x2*w2 +…wn*xn$, then add a special term called bias 'b' to this weighted sum to improve the model's performance. 
$∑w_i*x_i + b$ 
**Step-2**: In the second step, an activation function is applied with the above-mentioned weighted sum, which gives us output either in binary form or a continuous value as follows:
$Y = f(∑w_i*x_i + b)$ 

*Types of Perceptron Models* 
Based on the layers, Perceptron models are divided into two types. These are as follows:
1. **Single-layer Perceptron Model:** A basic neural network that can classify linearly separable data using a single layer of output units.
	- can learn only linearly separable patterns.
2. **Multi-layer Perceptron Model:** A more complex neural network with one or more hidden layers between the input and output layers, capable of learning non-linear relationships.

*Perceptron Function* 
Perceptron function ''f(x)'' can be achieved as output by multiplying the input 'x' with the learned weight coefficient 'w'. Mathematically:
$f(x)=1;$ if $w\cdot x+b>0$  (dot product, equivalent to $∑w_i*x_i + b > 0$)  
otherwise, $f(x)=0$ 
- 'w' represents real-valued weights vector
- 'b' represents the bias, 'x' represents a vector of input x values.

*Characteristics of Perceptron* 
1. Perceptron is a machine learning algorithm for supervised learning of binary classifiers.
2. In Perceptron, the weight coefficient is automatically learned.
3. Initially, weights are multiplied with input features, and the decision is made whether the neuron is fired or not.
4. The activation function applies a step rule to check whether the weight function is greater than zero.
5. The linear decision boundary is drawn, enabling the distinction between the two linearly separable classes +1 and -1.
6. If the added sum of all input values is more than the threshold value, it must have an output signal; otherwise, no output will be shown.

*Limitations* 
- The output of a perceptron can only be a binary number (0 or 1) due to the hard limit transfer function.
- Perceptron can only be used to classify the linearly separable sets of input vectors. If input vectors are non-linear, it is not easy to classify them properly.

### Activation Functions in Neural Networks
**What is Activation Function?** 
It's a function (also known as a Transfer Function) used to get the output of a node in a neural network.

**Why we use Activation functions with Neural Networks?** 
They determine the output of the neural network (e.g., yes/no) and map resulting values within a specific range (e.g., 0 to 1 or -1 to 1). They introduce non-linearity, which is crucial for handling complex data and enabling the model to learn and differentiate outputs effectively.

**Types of Activation Functions:** 
1. **Linear Activation Function** 
	* **Description:** A straight line function where `f(x) = x`.
	* **Range:** (-infinity to infinity).
	* **Limitation:** Does not help with the complexity or various parameters of typical neural network data, as it only produces linear transformations.

2. **Non-linear Activation Functions** 
	* **Description:** These functions introduce non-linearity, allowing the model to generalize and adapt to a variety of data, and differentiate between outputs.
	* **Key Terminology:**
		* **Derivative/Differential:** Slope; change in y-axis with respect to change in x-axis.
		* **Monotonic function:** Either entirely non-increasing or non-decreasing.

**Types of Non-linear Activation Functions:** 
*   **Sigmoid or Logistic Activation Function** 
    *   **Formula:** $\sigma(z) = \frac{1}{1 + e^{-z}}$ 
    *   **Shape:** S-shaped curve.
    *   **Range:** (0 to 1).
    *   **Use Case:** Ideal for models predicting probability as output.
    *   **Properties:** Differentiable, monotonic (but its derivative is not).
    *   **Limitation:** Can cause neural networks to get stuck during training. Softmax is a generalized version for multiclass classification.

*   **Tanh or hyperbolic tangent Activation Function** 
    *   **Formula:** $\text{tanh}(z) = \frac{e^z - e^{-z}}{e^z + e^{-z}}$ 
    *   **Shape:** S-shaped (sigmoidal), similar to logistic sigmoid but maps to (-1 to 1).
    *   **Advantage:** Maps negative inputs strongly negative and zero inputs near zero, generally performing better than sigmoid.
    *   **Properties:** Differentiable, monotonic (but its derivative is not monotonic).
    *   **Use Case:** Mainly used for classification between two classes. Both tanh and sigmoid are used in feed-forward networks.

*   **ReLU (Rectified Linear Unit) Activation Function** 
    *   **Formula:** $f(z) = \max(0, z)$
    *   **Shape:** Half-rectified; `f(z) = 0` if `z < 0`, and `f(z) = z` if `z >= 0`.
    *   **Range:** (0 to infinity).
    *   **Widespread Use:** Most common activation function, especially in convolutional neural networks and deep learning.
    *   **Properties:** Both the function and its derivative are monotonic.
    *   **Limitation (Dying ReLU):** All negative values become zero, which can reduce the model's ability to learn from data appropriately.

*   **Leaky ReLU**
    *   **Formula:** $f(z) = \begin{cases} z & \text{if } z \geq 0 \\ az & \text{if } z < 0 \end{cases}$ (where 'a' is a small constant, often 0.01)
    *   **Purpose:** Addresses the "dying ReLU" problem.
    *   **Mechanism:** Allows a small, non-zero gradient for negative inputs (`f(z) = az` for `z < 0`, where 'a' is a small constant, often 0.01).
    *   **Range:** (-infinity to infinity).
    *   **Variation:** If 'a' is not 0.01, it's called Randomized ReLU.
    *   **Properties:** Both the function and its derivative are monotonic.

*   **Softmax Activation Function**
    *   **Formula:** $\text{Softmax}(z_i) = \frac{e^{z_i}}{\sum_{j=1}^{K} e^{z_j}}$ for $i=1, \dots, K$
    *   **Shape:** Converts a vector of arbitrary real values into a probability distribution.
    *   **Range:** (0 to 1) for each element, and the sum of all elements equals 1.
    *   **Use Case:** Primarily used in the output layer of a neural network for multi-class classification problems, where it assigns probabilities to each class.
    *   **Properties:** Differentiable. Each output is dependent on all inputs, making it suitable for mutually exclusive classes.

# CH-3: ML Common Issues 
### I. Data Set, Training and Test Data set 
To improve **generalization** and avoid **information leaks**, it is standard practice to split a primary dataset into three distinct parts. Testing an algorithm on the same data used for training is poor practice, as it fails to measure how the model will perform on new, unseen data.
* **Training Set:** The largest subset used to actually build the model and adjust its internal weights.
* **Validation Set:** Used during the training phase to **fine-tune hyperparameters** and monitor performance. This set acts as an independent check to help identify and prevent **overfitting** before the final evaluation.
* **Test Set:** A "holdout" subset used only once the model is fully trained. It provides the final, unbiased measure of the model's performance and its true power to generalize to the real world.

##### Training, Validation and Test split
***Holdout Best Practices:*** 
* **Iterative Training:** Train on the training set and tune hyperparameters using the validation set. Repeat this until performance targets are met.
* **Information Leakage:** Avoid splitting into only two parts; a three-way split prevents the model from "seeing" the test data during tuning, ensuring true **generalization**.
* **Independence:** Never test on training data; it provides no insight into how the model handles new information.

***Popular Holdout Strategies:*** 
* **Simple Holdout:** A fixed fraction of data is set aside for testing. The specific ratio depends on the total volume of data available.
* **K-Fold Validation:** 
	* The data is divided into **$K$** equal blocks (folds).
	* The model trains $K$ times; each time, a different block is used for validation while the others are used for training.
	* **Final Score:** The average of all $K$ iterations.
	* *Note:* This is computationally expensive due to the repeated training cycles.
* **K-Fold with Shuffling:** The dataset is randomly shuffled before splitting. This is critical if the data has an inherent order (e.g., sorted by category) that might bias the folds.

***Split Considerations:***
* **Data Representativeness:** Ensure all subsets accurately reflect the overall distribution of the data.
* **Time Sensitivity:** If data is chronological, ensure the training set precedes the test set to avoid "predicting the past."
* **Data Redundancy:** Remove duplicate samples to prevent them from appearing in both training and testing sets, which inflates accuracy.

### II. Feature Engineering and Data Preprocessing
- ML process depends on feature engineering, which mainly contains two processes; which are Feature Selection and Feature Extraction.
- Feature selection is a way of selecting the subset of the most relevant features from the original features set by removing the redundant, irrelevant, or noisy features.
	- Irrelevant features may negatively impact and reduce the overall performance and accuracy of the model
	- ML model depends on Garbage In Garbage Out principle.
	
##### Feature Engineering and Data Preprocessing
Feature engineering is a critical phase of the machine learning pipeline, focused on the **Garbage In, Garbage Out** principle: the quality of the output is directly dictated by the quality of the input data. It primarily consists of two processes: **Feature Selection** and **Feature Extraction**.

***Feature Selection:***
This involves choosing a subset of the most relevant features from the original dataset. It focuses on identifying and keeping only the variables that contribute to the model's predictive power while discarding:
* **Redundant features:** Variables that provide the same information.
* **Irrelevant features:** Data points that have no relationship with the target.
* **Noisy features:** Data that contains errors or random fluctuations.

***Benefits of Feature Selection:*** 
* **Avoiding the Curse of Dimensionality:** Prevents the model from becoming overwhelmed by too many variables, which can degrade performance.
* **Model Simplification:** Makes the resulting model easier for researchers to interpret and explain.
* **Efficiency:** Significantly reduces the computational power and time required for training.
* **Generalization:** By removing noise and irrelevant data, it reduces **overfitting**, allowing the model to perform better on new, unseen data.

**Feature Selection Techniques** 
*Feature Selection* is divided into supervised and unsupervised categories, depending on whether the target variable is used to evaluate feature importance.

*Supervised Feature Selection* 
These methods use the relationship between input features and the target variable to decide what to keep.
* ***Filter Methods:*** These act as a preprocessing step by using statistical measures to score each feature.
	* **Missing Value:** Removing features that have too much missing data to be useful.
	* **Information Gain:** Measures how much "information" a feature provides about the target.
	* **Gini Index** (`gini` impurity): is a measure of impurity used while creating a decision tree in the CART(uses gain index for splitting ) `low gini` index is preferred
	* **Chi-Square Test:** Used for categorical data to see if the occurrence of a feature and the target are independent.
	* **Fisher's Score:** Ranks features based on how well they discriminate between different classes.

* ***Wrapper Methods:*** These use a specific ML model as a "black box" to evaluate feature subsets by training and testing multiple times.
	* **Forward Selection:** Starts with zero features and adds them one by one based on performance.
	* **Backward Selection:** Starts with all features and removes the least significant ones one by one.
	* **Exhaustive Selection:** Tests every possible combination of features (very expensive).
	* **Recursive Feature Elimination (RFE):** Repeatedly builds a model and removes the weakest feature until the desired number is reached.

* ***Embedded Methods:*** These perform feature selection *during* the model training process itself.
	* **Regularization (L1/L2):** As seen in Lasso (L1), it can penalize unimportant features by shrinking their coefficients to zero.
	* **Random Forest Importance:** Uses the internal structure of trees to rank which features reduce "impurity" the most.

*Unsupervised Feature Selection* 
These techniques evaluate features based on the structure of the data itself, without using a target label. They look for patterns, variance, or redundancy within the input variables. A common example is removing features with very low variance (meaning the value stays almost the same for every row and provides no useful pattern).

##### How to choose a Feature Selection Method?
The choice of feature selection method depends on whether your inputs and outputs are **Numerical** or **Categorical**.
![[Pasted image 20260422211853.png]]

***1. Numerical Input, Numerical Output (Regression)*** 
* **Pearson’s Coefficient:** For linear relationships.
* **Spearman’s Rank:** For non-linear relationships.

***2. Numerical Input, Categorical Output (Classification)*** 
* **ANOVA:** For linear relationships between groups.
* **Kendall’s Rank:** For non-linear associations.

***3. Categorical Input, Numerical Output (Regression)*** 
* **ANOVA & Kendall’s:** Used to determine if categorical groups significantly impact numerical outcomes.

***4. Categorical Input, Categorical Output (Classification)***
* **Chi-Squared Test:** Measures independence between variables.
* **Information Gain:** Measures how much an input reduces uncertainty about the target.

##### Data Pre-processing Fundamentals
- In most cases, the data that we receive may not be in a format that can be readily used.
- Most of the feature engineering techniques are domain-specific.

Data preprocessing transforms raw data into a clean, numerical format that machine learning models can process effectively.

***Vectorization*** 
This process converts non-numeric data into numerical vectors.
* **Text Data:** Words or documents are converted into numbers (e.g., Word2Vec or TF-IDF).
* **Categorical Data:** Techniques like **Label Encoding** assign a unique number to each category (e.g., Red=1, Blue=2).

***Normalization / Scaling*** 
It is standard practice to ensure all features are on a similar scale so that one feature doesn't dominate others due to its sheer magnitude.
* **Standardization:** Rescales data so the **mean is 0** and the **standard deviation is 1**.
* **Min-Max Scaling:** Compresses data into a specific range, typically **0 to 1**.

***Handling Missing Values*** 
Real-world data often has gaps that must be addressed to avoid model errors.
* **Deletion:** Removing rows or columns with missing data.
* **Imputation:** Filling gaps using statistical measures like the **mean, median, or mode**.
* **`SimpleImputer`:** A common tool used to automate these replacement strategies.

***Feature Engineering*** 
This involves creating new, meaningful variables from existing data to boost model performance.
* **Extraction:** For example, in house price prediction, if you have *total price* and *square footage*, you can create a new feature: **`price_per_sqft`**. This often provides more insight than the raw numbers alone.

### Over-fitting and Under-fitting 
Poor model performance is generally caused by an imbalance between **Bias** and **Variance**. Understanding these concepts is essential for building a model that can achieve strong **Generalization** (the ability to predict unseen data accurately).

***Core Concepts:***
* **Noise:** Random, meaningless, or irrelevant data points that can distract a model during training.
* **Bias:** Error caused by oversimplifying the algorithm. High bias leads to **Underfitting**, where the model misses the underlying patterns in the data.
* **Variance:** Error caused by the model being overly sensitive to small fluctuations in the training set. High variance leads to **Overfitting**.

***The Overfitting/Underfitting Dynamic:*** 
* **Underfitting:** Occurs when the model is too simple to learn the data. It has **high bias** and performs poorly on both training and test sets.
* **Overfitting:** Occurs when the model "memorizes" the training data, including the noise. It has **low bias** but **high variance**.

**How to Detect Overfitting:** 
The most effective way to detect overfitting is to compare the model's accuracy on the **training set** versus the **test set**.
* **The "Gap" Test:** If your model has **85% accuracy** on training data but drops to **50% accuracy** on the test dataset, it is overfitted. It has learned the specific quirks of the training data rather than the general patterns needed for new data.

##### Techniques to solve overfitting 
focus on simplifying the model or increasing the diversity of the data so the algorithm doesn't "memorize" the training set.
* **Early Stopping:** Training is paused before the model begins learning noise. By measuring performance at each iteration, you can stop at the **"sweet spot"** where test error is lowest. Stopping too early, however, can lead to underfitting.
* **Train with More Data:** Increasing the dataset size helps the model discover true underlying relationships between variables rather than focusing on random fluctuations in a small sample.
* **Feature Selection:** Identifying and keeping only the most important features. Removing redundant or irrelevant data simplifies the model and reduces the chance of learning noise.
* **Cross-Validation:** Dividing the dataset into $k$ equal-sized **folds**. The model trains on different combinations of these folds, ensuring it learns to generalize across various subsets of the data.
* **Data Augmentation:** Instead of collecting new data, you create slightly modified copies of existing data (e.g., flipping or rotating an image). This makes the sample look different every time the model processes it.
* **Regularization:** A set of methods (like **L1 and L2**) that adds a penalty to the model’s complexity, forcing the algorithm to stay as simple as possible.

##### Methods to Reduce Underfitting
**Underfitting Problem** 
Occur when model trained with fewer amounts of data
Underfitting occurs when our model is too simple to understand the base structure of the data.

Methods to Reduce Underfitting:
- Increase model complexity
- Remove noise from the data
- Trained on increased and better features
- Reduce the constraints
- Increase the number of epochs to get better results.

### Errors in Machine Learning
In Machine Learning, an **error** is a metric that quantifies how accurately an algorithm predicts outcomes for data it has never seen before. Total error is composed of two main types:

***Reducible Errors***
These are errors that can be minimized to improve model accuracy by choosing better algorithms or refining data. They are divided into two categories:
* **Bias:** Error originating from overly simplistic assumptions in the learning algorithm.
* **Variance:** Error originating from the model's sensitivity to small fluctuations in the training set.

***Irreducible Errors***
These errors will always remain in the model, no matter which algorithm is used or how much you tune it. 
* **Source:** They are caused by unknown variables, inherent noise in the data, or natural variations that cannot be captured by the features provided.
* **Impact:** They define the "ceiling" of a model's accuracy; you cannot reduce these errors through better engineering.

##### Bias and Variance Errors
The performance of a model is often a tug-of-war between bias and variance. Balancing these two is the key to building an accurate and reliable system.

**Bias: The "Assumption" Error**
Bias measures how much a model’s predictions differ from the actual values due to oversimplification.
* **Low Bias:** The model makes fewer assumptions about the data. It is flexible and closely follows the data points.
	* *Examples:* Decision Trees, k-Nearest Neighbors (k-NN), and Support Vector Machines (SVM).
* **High Bias:** The model makes heavy assumptions, often missing important patterns. This leads to **underfitting**, where the model performs poorly on both training and new data.
	* *Examples:* Linear Regression and Logistic Regression.
	* *Solution:* Use more complex models or add more relevant features.

**Variance: The "Sensitivity" Error**
Measures how much the model's predictions change when it is trained on a different set of data.
* **Low Variance:** Predictions are stable. Changing the training data slightly does not significantly change the model's output.
  * *Examples:* Linear Regression and Logistic Regression.
* **High Variance:** The model is highly sensitive to small fluctuations in training data. It "memorizes" the specific dataset (including noise), leading to **overfitting**.
  * *Examples:* Non-linear algorithms like Decision Trees or Deep Neural Networks.
  * *Solution:* Use regularization, cross-validation, or more training data to simplify the model.

**Bias-Variance Combinations** 
The relationship between bias and variance determines the overall success of a model. We can visualize this using a target analogy:
* **Low-Bias, Low-Variance:** The **Ideal Case**. Predictions are both consistent and accurate.
* **Low-Bias, High-Variance:** The **Overfitting Case**. The model is flexible but overly sensitive to training data, leading to inconsistent predictions on new data.
* **High-Bias, Low-Variance:** The **Underfitting Case**. The model is consistent but consistently wrong because it is too simple to capture the data's complexity.
* **High-Bias, High-Variance:** The **Worst Case**. Predictions are both inaccurate and inconsistent.

**The Bias-Variance Trade-off** 
In practice, decreasing bias usually increases variance, and vice versa. The "Trade-off" is the process of finding the optimal point of complexity where the **Total Error** (Bias + Variance + Irreducible Error) is minimized.

### The Confusion Matrix 
A **Confusion Matrix** (or Error Matrix) is a table used to evaluate the performance of a classification model by comparing predicted values against actual "ground truth" labels.
**The Four Quadrants:** 
* **True Positive (TP):** You predicted Positive and it was Positive (Correct).
* **True Negative (TN):** You predicted Negative and it was Negative (Correct).
* **False Positive (FP):** You predicted Positive but it was Negative (Incorrect - Type I Error).
* **False Negative (FN):** You predicted Negative but it was Positive (Incorrect - Type II Error).

Some of the models in machine learning require more precision and some model requires more 
recall.
##### Precision, Recall, and F1-Score
These metrics are essential for evaluating **classification** models, especially when dealing with imbalanced datasets where accuracy alone can be misleading.

**Precision** 
Precision measures the accuracy of your positive predictions. It answers the question: *Of all the instances the model labeled as positive, how many were actually correct?* 
* **Focus:** Minimizing False Positives.
* **Formula:** $Precision = \frac{TP}{TP + FP}$ 

**Recall (Sensitivity)** 
Recall measures the model's ability to find and detect all actual positive samples. The higher the recall, the fewer positive cases the model misses.
* **Focus:** Minimizing False Negatives.
* **Formula:** $Recall = \frac{TP}{TP + FN}$

**F1-Score**
The F1-Score is the **harmonic mean** of precision and recall. It provides a single score that balances both metrics, making it very useful when you need to find a middle ground between precision and recall.
* **Benefit:** It penalizes extreme values. If either precision or recall is very low, the F1-Score will also be low.
* **Formula:** $F1 = 2 \times \frac{Precision \times Recall}{Precision + Recall}$


# CH 5: Advanced ML and Deep Learning Introduction
### Ensemble Learning ML
Ensemble techniques in machine learning involve combining multiple individual models (often referred to as base models or weak learners) to improve overall predictive performance.

Combining diverse models can often produce more accurate and robust predictions compared to using a single model.

3 main methods
##### 1. Bagging
Short for Bootstrap Aggregating, is an ensemble learning technique used to improve the stability and accuracy of machine learning algorithms.
It works by combining the predictions of multiple base models, each trained on a subset of the original dataset.

**How Bagging Works** 
- Bagging starts by creating multiple bootstrap samples from the original dataset.
- Bootstrap sampling involves randomly selecting samples from the original dataset with replacement. 
- This means that some instances may be selected multiple times, while others may not be selected at all
- Base Model Training: Once the bootstrap samples are created, a base model (e.g., decision tree, random forest, etc.) is trained on each bootstrap sample

**Voting or Averaging**: After training all the base models, bagging combines their predictions through a voting mechanism (for classification tasks) or averaging (for regression tasks).

Bagging helps to reduce overfitting by reducing the variance of the model.

##### 2. Boosting
Unlike bagging, which trains each base model independently, boosting trains base models sequentially, with each subsequent model focusing more on the instances that were misclassified by the previous models.
The succeeding models are dependent on the previous model. 

**How boosting works** 
A. *Base Model Training*: Boosting starts by training a base model (often a weak learner) on the original dataset.
B. *Instance Weighting*: After the first model is trained, the misclassified instances are given higher weights, while the correctly classified instances are given lower weights. This allows subsequent models to focus more on the difficult instances.
C. *Sequential Training*: The subsequent models are trained sequentially, with each model focusing more on the instances that were misclassified by the previous models. The weights of the instances are adjusted after each model is trained.
D. *Combining Predictions*: Finally, the predictions of all the models are combined through a weighted sum or voting to produce the final prediction.

**Example**: AdaBoost (Adaptive Boosting) and Gradient Boosting

These examples will:
1.  Generate a synthetic dataset.
2.  Split the data into training and testing sets.
3.  Train a Bagging Classifier.
4.  Train an AdaBoost Classifier.
5.  Evaluate the performance of both.

```python
from sklearn.ensemble import BaggingClassifier, AdaBoostClassifier
from sklearn.tree import DecisionTreeClassifier
from sklearn.datasets import make_classification
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

# 1. Generate a synthetic dataset
X, y = make_classification(n_samples=1000, n_features=20, n_informative=10, n_redundant=10, random_state=42)

# 2. Split data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

print("--- Bagging Example ---")

# 3. Bagging Classifier
# A Bagging Classifier often uses a Decision Tree as its base estimator.
# Here, we'll use 10 base estimators.
bagging_model = BaggingClassifier(
    estimator=DecisionTreeClassifier(random_state=42),
    n_estimators=10,
    random_state=42,
    n_jobs=-1 # Use all available CPU cores
)

# Train the Bagging model
bagging_model.fit(X_train, y_train)

# Make predictions
bagging_predictions = bagging_model.predict(X_test)

# Evaluate the model
bagging_accuracy = accuracy_score(y_test, bagging_predictions)
print(f"Bagging Classifier Accuracy: {bagging_accuracy:.4f}")

print("\n--- AdaBoost (Boosting) Example ---")

# 4. AdaBoost Classifier
# AdaBoost typically uses weak learners, often shallow decision trees (e.g., max_depth=1 is a common choice, called a "decision stump").
adaboost_model = AdaBoostClassifier(
    estimator=DecisionTreeClassifier(max_depth=1, random_state=42), # Decision stump as base estimator
    n_estimators=50, # Number of boosting stages
    learning_rate=1.0, # Contribution of each estimator
    random_state=42
)

# Train the AdaBoost model
adaboost_model.fit(X_train, y_train)

# Make predictions
adaboost_predictions = adaboost_model.predict(X_test)

# Evaluate the model
adaboost_accuracy = accuracy_score(y_test, adaboost_predictions)
print(f"AdaBoost Classifier Accuracy: {adaboost_accuracy:.4f}")

print("\n--- Comparison ---")
# Let's also train a single Decision Tree for comparison
single_tree = DecisionTreeClassifier(random_state=42)
single_tree.fit(X_train, y_train)
single_tree_predictions = single_tree.predict(X_test)
single_tree_accuracy = accuracy_score(y_test, single_tree_predictions)
print(f"Single Decision Tree Accuracy: {single_tree_accuracy:.4f}")
```

**Explanation:**
* **`make_classification`**: Creates a random n-class classification dataset, useful for quick examples.
* **`BaggingClassifier`**:
	* `estimator`: The base estimator to fit on random subsets of the dataset. If `None`, a `DecisionTreeClassifier` is used.
	* `n_estimators`: The number of base estimators in the ensemble. Each estimator is trained on a different bootstrap sample.
	* `n_jobs=-1`: Instructs `scikit-learn` to use all available processor cores for parallel training, which can speed up the process for bagging.
* **`AdaBoostClassifier`**:
	* `estimator`: The base estimator from which the boosted ensemble is built. Crucially, AdaBoost works best with *weak learners* (e.g., `DecisionTreeClassifier(max_depth=1)`).
	* `n_estimators`: The maximum number of estimators at which boosting is terminated.
	* `learning_rate`: Shrinks the contribution of each classifier. A higher learning rate increases the contribution of each classifier, but too high can lead to overfitting.


### Unsupervised Learning
Aims to find the underlying structure or the distribution of data. We want to explore the data to find some intrinsic structures in them.

Unsupervised learning cannot be directly applied to a regression or classification problem.
Unsupervised learning works on *unlabeled* and *uncategorized* data which make unsupervised learning more important.

**Core Unsupervised Learning Techniques** 
*Clustering*: Clustering is a method of grouping the objects into clusters such that objects with most similarities remains into a group.
*Association*: An association rule is an unsupervised learning method which is used for finding the relationships between variables in the large database. It determines the set of items that occurs together in the dataset.
*Dimensionality Reduction*: Reducing the number of features (variables) in a dataset while preserving important information.

#### Unsupervised Learning algorithms
##### K-means clustering
K-Means is a partitioning clustering algorithm that separates a dataset into K distinct, non-overlapping subsets (clusters).

**Working Principle (steps)** 
- *Initialization*: Randomly select K data points as initial cluster centers. (centroids)
- *Assignment*: Assign each data point to the cluster whose center is nearest.
- *Update Centers*: Recalculate the cluster centers as the mean, variance, Euclidian distance of the data points in each cluster.
- *Repeat*: Iterate steps 2 and 3 until convergence (when cluster assignments stabilize).

```
from sklearn.cluster import KMeans
from sklearn import datasets
from sklearn.utils import shuffle

# import some data to play with
iris = datasets.load_iris()
X = iris.data 
y = iris.target
names = iris.feature_names
X, y = shuffle(X, y, random_state=42)
model = KMeans(n_clusters=3, random_state=42) 
iris_kmeans = model.fit(X)
```

### Introduction to Deep Learning
Deep learning is a subset of machine learning, which itself is a subset of artificial intelligence (AI).
Deep learning models are inspired by the structure and function of the human brain, specifically neural networks, and they are designed to automatically learn features and patterns from large amounts of data. 
The output from each preceding layer is taken as input by each one of the successive layers.
- Deep learning models are capable enough to focus on the accurate features themselves by requiring a little guidance from the programmer and are very helpful in solving out the problem of dimensionality.
- Deep learning algorithms are used, especially when we have a huge no of inputs and outputs. 
- Deep learning is a collection of statistical techniques of machine learning for learning feature hierarchies that are actually based on artificial neural networks.

**Deep Learning Implementation** 
Deep learning is implemented by the help of deep networks, which are nothing but neural networks with multiple hidden layer.

***Artificial Neural Network*** 
Neural Networks processes information in a similar way the human brain does, and these networks actually learn from examples, you cannot program them to perform a specific task.
They will learn only from past experiences as well as examples.

Input Layer -> Hidden Layers -> Output layer

**Input Layer** 
This layer consists of neurons that directly accept the input features of the data. 
It acts as a channel to pass the raw data into the network. It does no computations.
For example, if the input is an image of 28x28 pixels, the input layer will have 784 neurons (one for each pixel).

**Hidden Layer** 
Where the actual computation and learning takes place.
Consists of neurons that apply weights and biases to the input, followed by an activation function to introduce non-linearity.
There can be one or multiple hidden layers, and each layer transforms the input data into a more abstract and useful representation.

**Output Layer** 
Produces the output prediction.
The number of neurons here corresponds to the number of output classes or the number of values to predict in the case of regression tasks.
In a classification task, it typically uses a `softmax` activation function to provide class probabilities. 
In regression tasks, it may use a linear activation function.

##### Perceptron
The Neural Network's basic unit is called a Perceptron. So, a perceptron can be defined as a neural network with a single layer that classifies the linear data.
- Networks without hidden layer.
- Also known as single-Layered Feed-Forward Networks.

Has four major components:-|
1. **Input Features (x)**: the inputs to the perceptron.
	- each input is associated with the feature of the data
	- e.g. for an image recognition task each pixel can be an input feature
2. **Weight (w)**: Each input feature is multiplied by a corresponding weight. 
	- Weights are parameters that the perceptron learns during training. 
3. **Bias (b)**: The bias term is added to the weighted sum of inputs. It allows the activation function to be shifted left or right, enabling the perceptron to make more flexible decisions.
	-  Bias helps in the adjustment of the curve of activation function so as to accomplish a precise output.
4. **Activation Function**: The weighted sum of the inputs plus the bias is passed through an activation function. The activation function determines the output of the perceptron based on this sum

**Perceptron's parts** 
For a basic perceptron, the activation function is usually a step function (Heaviside step function), which outputs 1 if the weighted sum is greater than a certain threshold and 0 otherwise.
Introducing non-linearity, allowing them to learn complex patterns and relationships in data.
$$z=\sum w_ix_i+b$$ output: 
$$f(z) = \begin{cases}
    1 & \text{if } z \geq 0 \\
    0 & \text{if } z < 0
\end{cases}$$

##### Types of Activation function 
[[#Activation Functions in Neural Networks]] ($\leftarrow$ link to detail explanation)

**When to use which Activation function** 
- *Sigmoid*: Use for binary classification tasks where the output needs to be interpreted as a probability between 0 and 1. 
- *Hyperbolic Tangent (Tanh)*:  Use in hidden layers of neural networks for zero-centered activations and when outputs need to be in the range (-1, 1). 
- *Rectified Linear Unit (ReLU)*: Use in hidden layers of deep neural networks for faster convergence and to overcome the vanishing gradient problem. 
- *Leaky ReLU*: Use to address the "dying ReLU" problem in deep neural networks where some neurons become inactive during training. 
- *Softmax*: Use in the output layer of neural networks for multi-class classification tasks where outputs need to be interpreted as probabilities and the sum of probabilities equals 1.

**Simple implementation** 
```python
# importing tensorflow library to create our ANN model. If your model has more than 2 layers it
# is called deep learning network.
import tensorflow.keras
from keras.models import Sequential
from keras.layers import Dense

model = Sequential()
# input dim is number of inputs. It is always of the same size as feature size. (X)
# 40 is number of neurons or units.
model.add(Dense(40, input_dim=5, activation='relu'))
model.add(Dense(40, activation='relu'))
model.add(Dense(1, input_dim=5, activation='linear'))

# Compile the model
model.compile(loss="binary_crossentropy", optimizer="adam", metrics=["accuracy"])

# Train the model
model.fit(X_train_scaled, y_train, epochs=10, batch_size=32)

# Evaluate the model on test data
loss, accuracy = model.evaluate(X_test_scaled, y_test)
print("Test Accuracy:", accuracy)
```


# CH - 5: PT 2 - Neural Networks
**History** 
- 1943: McCulloch & Pitts show that neurons can be combined to construct a Turing machine (using ANDs, Ors, & NOTs)
- 1958: Rosenblatt shows that perceptrons will converge if what they are trying to learn can be represented
- 1969: Minsky & Papert showed the limitations of perceptrons, killing research for a decade
- 1985: backpropagation algorithm revitalizes the field

**Definition** 
A Neural Network is a system composed of many simple processing elements operating in parallel which can acquire, store, and utilize experiential knowledge.

Each element of NN is a node called **unit**.
Units are connected by **links**.
Each link has a **numeric weight**.

A typical unit: input links -> (input function, activation function, output) -> output links

*Planning in building a Neural Network* 
Decisions must be taken on the following: 
- The number of units to use.
- Connection between the units.

*How NN learns a task.* 
- Initializing the weights.
- Use of a learning algorithm.
- Set of training examples.
- Encode the examples as inputs.
- Convert output into meaningful results.

There are 2 types of components: Linear and Non-linear.
- Linear: Input function
	- calculate weighted sum of all inputs.

- Non-linear: Activation function
	- transform sum into activation level.


**Standard Structure of an ANN** 
Input units
- represents the input as a fixed-length vector of numbers (user defined)

Hidden units
- calculate threshold weighted sums of the inputs
- represent intermediate calculations that the network learns

Output units
- represent the output as a fixed length vector of numbers

$z = W_{i,j} * \text{Input}_j + W_{i,k} * \text{Input}_k + W_{i,l} * \text{Input}_l + b$
- where $f(x)$ is a threshold (activation) function
- $f(z) = 1 / (1 + e^{-z})$  - “sigmoid”
- $\text{Output}_i = 1 / (1 + e^{-(W_{i,j} * \text{Input}_j + W_{i,k} * \text{Input}_k + W_{i,l} * \text{Input}_l + b)})$ 
- $f(x) = \text{step function}$ 

### Network Structures
**Feed-forward neural nets**:
- Links can only go in one direction.
- Arranged in layers.
- Each unit is linked only in the unit in next layer.
- No units are linked between the same layer, back to the previous layer or skipping a layer.

**Recurrent neural nets**: 
- Links can go anywhere and form arbitrary topologies.
- Allows activation to be fed back to the previous unit.
- Internal state is stored in its activation level.
- Can become unstable/ oscillate.

- May take long time to compute a stable output.
- Learning process is much more difficult.
- Can implement more complex designs.
- Can model certain systems with internal states.

### Perceptron
Also known as single Layered Feed-Forward Networks.

**Perceptron learning rule** 
- Teacher specifies the desired output for a given input
- Network calculates what it thinks the output should be
- Network changes its weights in proportion to the error between the desired & calculated results

$w_{i,j} = \eta * [teacher_i - output_i] * input_j$ (delta rule)
where: 
- $\eta$ is the learning rate;
 - $teacher_i - output_i$ is the error term; 
- and $input_j$ is the input activation

**Node biases** 
A node’s output is a weighted function of its inputs.
A bias is just another weight.

**Perceptron Convergence Theorem** 
If a set of `<input, output>` pairs are learnable (representable), the delta rule will find the necessary weights
- in a finite number of steps
- independent of initial weights

However, a single layer perceptron can only learn linearly separable concepts
- it works iff gradient descent works

**Linear separability** 
Consider a perceptron

Its output is
- 1, if $W_1X_1 + W_2X_2 > \eta$ 
- 0, otherwise

In terms of feature space
- hence, it can only classify examples if a line (hyperplane more generally) can separate the positive examples from the negative examples

**What can a Perceptron Represent?** 
- Some complex Boolean function can be represented.
- `Perceptrons` are limited in the Boolean functions they can represent.

**Learning Linearly Separable Functions** 
- There are not many linearly separable functions.
- BUT, There is a perceptron algorithm that will learn any linearly separable function, given enough training examples.

- Initial network has a randomly assigned weights.
- Learning is done by making small adjustments in the weights to reduce the difference between the observed and predicted values.
- Main difference from the logical algorithms is the need to repeat the update phase several times in order to achieve convergence.
- Updating process is divided into epochs.
- Each epoch updates all the weights of the process.

### Multi-Layer Neural Nets
**Need for Hidden Units** 
If there is one layer of enough hidden units, the input can be recoded.
This recoding allows any mapping to be represented.
- Layer 0 is input nodes
- Layers 1 to N-1 are hidden nodes
- Layer N is output nodes
- All nodes at any layer k are connected to all nodes at layer $k+1$ 
- There are no cycles

### Backpropagation Networks
A sensible approach for dividing the contribution of each weight.
- Works basically the same as a perceptron

*Principles* 
There are two differences for the updating rule:
1) The activation of the hidden unit is used instead of the input value.
2) The rule contains a term for the gradient of the activation function.

**Backpropagation Network training** 
1. Initialize network with random weights
2. For all training cases (called examples):
	- a. Present training inputs to network and calculate output
	- b. For all layers (starting with output layer, back to input layer):
			i. Compare network output with correct output (error function)
			ii. Adapt weights in current layer

Can’t use Perceptron Learning Rule - no teacher values are possible for hidden units.
Use gradient descent to minimize the error
- Propagate deltas to adjust for errors backward from outputs to hidden layers to inputs.

**Main Idea** 
The ideas of the algorithm can be summarized as follows:
1. Computes the error term for the output units using the observed error.
2. From output layer, repeat 
	- propagating the error term back to the previous layer and 
	- updating the weights between the two layers until the earliest hidden layer is reached.

**Algorithm** 
Initialize weights (typically random)
Keep doing epochs
- For each example e in training set do
	- forward pass to compute
		- O = neural-net-output(network)
		- miss = (T-O) at each output unit 
	- backward pass to calculate deltas to weights
	- update all weights
	- end
until tuning set error stops improving

*Backward Pass* 
- Compute deltas to weights from hidden layer to output layer.
- Without changing any weights (yet), compute the actual contributions within the hidden layer(s) and compute deltas

TOO MUCH COMPLEX MATH, I'M TIRED.

How do we pick $\eta$? - Small for slow, conservative learning
How Many Hidden Layers? - usually 1, (i.e. a 2-layer net)
- Too few ==> can’t learn
- Too many ==> poor generalization

How big a training set?
- Determine your target error rate, $e$ 
- Success rate is $1- e$ 
- Typical training set approx. $n/e$, where n is the number of weights in the net

##### Neural Network in Practice
NNs are used for classification and function approximation or mapping problems which are:
- Tolerant of some imprecision.
- Have lots of training data available.
- Hard and fast rules cannot easily be applied.

**Feed-forward vs. Interactive Nets** 
Feed-forward
- activation propagates in one direction
- We usually focus on this

Interactive
- activation propagates forward & backwards
- propagation continues until equilibrium is reached in the network
- We do not discuss these networks here, complex training. May be unstable.

**Ways of learning with an ANN** 
- Add nodes & connections
- Subtract nodes & connections
- Modify connection weights
	- current focus
	- can simulate first two
- I/O pairs: 
	- given the inputs, what should the output be? [“typical” learning problem]

**More Neural Network Applications** 
- May provide a model for massive parallel computation.
- More successful approach of “parallelizing” traditional  serial algorithms.
- Can compute any computable function.
- Can do everything a normal digital computer can do.
- Can do even more under some impractical assumptions.

**Summary** 
- Given enough units, any function can be represented by Multi-layer feed-forward networks.
- Backpropagation learning works on multi-layer feed-forward networks.
- Neural Networks are widely used in developing artificial learning systems.











