# Machine Learning

# $Y = f(x)$
## Relevance of AI 

### What is AI 
- The study and creation of machines that perform tasks normally associated with intelligence

**Psychologsts/Cognitive Scientists**
- AI is being commercialized 
**Engineers**
- AI for corporations mainly used for automations
- Ex. 
	- Spam Filters
	- Analyze for data clustering 

### Why is it relevant
- **Traditionally human capabilities** - Human labor

### How did AI Start
- The Inception of Artificial Intelligence (1943-1956)
	- Just trying to model the human brain 
- Early Enthusiasm, great expectations (1952-1969)
	- They know the physical limitations but focused on the logical and analytical part
- Dose of reality (1966-1973)
	- Back in the days (Intelligent systems 1) those are the people that creates the algorithms 
- Expert Systems (1969-1986)
	- Less generality and focus on things they can solve 
	- Focused on the If-Else AI 
	- Deterministic
- Neural networks, Machine Learning, Probalistic Reasoning (1986-present)
	- Instead of logic, Hand coding, and philosophical claims it was implemented to be automated and focused on probability
- Big Data and Deep Learning (2001-present, 2011-present)
	- Dawn of the internet 


### The Usual Machine Learning Workflow

#### Preprocessing 
- Convert it into the language the machine can understand 
- You create your features through the raw data 
	- Feature Engineering 
		- How do you identify a person? 
		- Key for good outputs 
	- Splitting the Data 
		- There is no golden ratio between training and testing data 

#### Modelling 
- Model does not mean its only machine model.

#### Evaluation 
- The most important to learn in this class

### Linear Regression

#### Loss Functions
- Current output -> Expected output 
- Loss function is the relationship between the hypothesis and conclusion 


$t = \text{target or  predictions}$
$X = \text{input}$
$X^{(i)} \text{ for which } t^{(i)} = \text{Training samples}$
The relationship of $X \text{ and } t$ = Model 
Tells how the model approximates the target given the training = Loss
Finding the parameters of a model  = Optimization 

**We square values to make exponential adjustments based on the results**



**Stochastic **
- Tignan isa isa bago update kaagad
**Batch**
- Tignan lahat bago update 

$\lambda$ - learning rate 




![[Pasted image 20240205081759.png]]

Index card prelim exam 
------------------

AI - The study and creation of machines that perform tasks normally associated with intelligence 
Relevance - Can be applied to every sector new possibilities and efficiencies 

**Phsychologists** - how people work. Machine can help
**Engineers** - building machines can do useful tasks 

Inception (43-56)
- model of artificial neurons 
- any computable function could be computed by some network of connected neurons 

Enthusiasm, great expectations (52-69)
- researchers responded by demonstrating 
- taks considered indicative of intelligence in humans 

Reality(66-73)
- primarily based on "informed introspection"
- lack of appreciation of intractability 
Expert Systems (69-86)
- Alternative to weak methods - use more powerful domain-specific knowledge taht allows larger reasoning steps 
Neural Networks, ML, Prob reasoning(86-)
- Reinvented the back-propagation learning algorithm 
- more scientific approach incorporating probability
Big Data and Deep Leearning (2001-, 2011-)
- BigData - Large datasets 
- deep learning - ML using mutliple layers of simple, adjustable computing elements (CNN - 1970)

ML - takes examples and produces a program that does the job

Output space - Target variable that is desired to be estimated 
Hypothesis - speculative relationship between the input and output spaces
Input space - Variables/Features/Attributes

Types of learning 

Supervised - Maps inputs to outputs. Learning to predict an output given an input vector. Learning by examples.

Classification - Categoral outputs 
Regression - Real-valued outputs 

Unsupervised - Learn patterns in input data without feedback. Create an internal representation of the input, capturing regularities/structure in data. Learning by discovery. Output corresponding to input is not provided 

Reinforcement - Learn actions causing occasional rewards and punishments. Learn by experimentation 

Pre processing- includes anything that needs to be done on the data prior to feeding it to the model 

Feature engineering - Manipulation of the data set to improve machine learning model training. 

Data cleaning - proccess of fixing or removing, incorrect, corrupted, incorrectly formatted, duplicate, or incomplete data within a dataset

Scaling and Normalization - transform the range of features of data. 

Splitting the Data - model validation procedure that allows to simulate how a model would perform 

Modelling - description of a system using math concepts represents of objects and relationships and languages 

Evaluation - process of using different evaluation to understand a machine a ML model's performance, strengths and weaknesses


AI - Intelligent behavior - ML - learning from data to make predictions - DL - Learning using artificial neural networks 

Loss Functions - computes the distance between current output and the expected output. Maps an event or values of one or more variables onto a real number 

Optimization problem seeks to minimize a loss function 


Regression - statistical technique that relates a dependent variable to one/more independent variables
What to predict 
![[Pasted image 20240314182029.png]]


Batch updates - sum of average updates accross every example

Stochastic updates - update parameters for each training case in turn according to its won gradients
Gradient descent to solve for each coefficient, or compute analytically.

Generalization is the model’s ability to predict the held out data

ridge regression -penalty on the squared weights