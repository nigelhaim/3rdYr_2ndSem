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

# Neural Networks 
- **Graphs has 2 things** 
	- Nodes
	- Edges 
- Neural Networks are inspired from the actual brain 

## Neural Networks
- Mathematical models 
- Based from Neuroscience 
	- Understanding how the brain works 
- To process information 
	- They are bioinspired computing 
		- Inspired from real world phenomenons
- Densely interconnected 
	- Di lang  basta basta nodes
	- After easter break 
- During the 1980s 
	- They try to just model the brain 
	- So simple 
	- They do not have the powerful computational capabilities 

**McCullough and Pitts (1944)**
- Arranged into weights but weren't arranged into laers 
- Focused on trying to understand the brain rather than thte computer science part

**Iphone (Siri)**
- Through neural networks siri understands us 
- NLP and speech recognition had a hardtime to understand human language without neural networks 

### Mathematical Model 
- Based from the human anatomy in highschool (Brain)
	- Axon - information from  a neuron (Differetn information)
	- dendrite - Transfers information to the cell body 
	- Cell body (Computation)
	- Activation - Output 
- **ReLU**
	- Electrified Unit
	- Anything negative is 0
	- Anything positive = Same value 
	- Introducing non-linearity 
	- Able to capture varied patterns 
- There are 50 activation functions 

### Neural Network Architecture 
- A neuron is basically a building block of a layer and layers can be arranged based on their function (Input, hidden, output)
- Information is divided from the input then all enters in each node of the hidden layer to produce an output 

#### Naming conventions
**2 Layer network**
- Input + Hidden + Output 
- Multi output

Number of layer network = Total number of layers - 1 


**Representational power**
- The higher the hidden neurons the more complicated
- At least one hidden layer is a universal appropriator 
	- **Universal approximation** - Can represent any function
- The more hidden neurons it is better but too much hidden neurons can overfit

#### What do you need to learn? 
- Forward pass : Inference 
	- Basically prediction 
- Backward pass: Inference 
	- Error checking and optimization 

#### To find the weights 
- MInimize the loss 
- Optimize using gradient descent 


#### Backpropogation
- Gradient-based optiimization 
- Propagate errors backward
- Backpropogation is a bit complicated to derive 


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

Classification - arranging things into kinds of things / groups of classes 

Regression - continous variables 
Classification - categorical outputs

Classification as a regression problem? Yes, ignore the output is categorical 

Linear classification - based on the value of a linear combination. To learn good decision boundaries 

Classes can be perfectly serparate classes = linearly serparable problem 

causes of non perfect serparation 
- Model too simple 
- Noise 
- Simple features does not account 
- Errors on target 

Recall - fraction of relevant instances that are retrived 

Precision - fraction of retrived instances taht are relevant 


Accuracy - fraction of correct instances 

F1 - Harmonic mean of precision and recall 

Regression - Statistical technique that relates a dependent variable to one or more independent variables 

Logistic regression - Models the probability of an event taking place 
Probability - numerical descriptions of how likely an event is to occur 

Frequentist probability - 1000 times = 500h and 500t
subjectivist probability - probability based on velief and gives constitutions for logically consistent beliefs 

Experiment - produces exactly one out of several outcomes 
sample space - set of possible outcomes 

event - subset of sample space 

Bayes formula - logically consistent way of reasoning about evidence and consequences of evidence 

probability model - assigns probabilities to events

Conditional probability - outcome based on the previous outcome 

Decision trees - Tree-like model of decisions and their possible consequences

High Entropy - Uniform distribution, less predictable 
Low entropy - peaks and valleys, more predictable 

Instance-based learning - comparison of new problem instances seen in training 

Sigmoid function - converts real-valued inputs to have values of 0 to 1


K-Nearest - Non parametic supervised learning classifier which uses proximity to make classifications or predictions 

Larger k may lead to better performance 

Unsupervised learning - work on their own to discover the inherent structure of data (dont need labels)

Clustering - Grouping of set of similar objects 

Euclidean distance - defines similarity 

K-means clustering - centroid-based clustering, calculates the distance between each data point and a centroid to assign to a cluster 

Hierarchical clustering - analysis that seeks to build a hierarchy of clusters. Does not require a pre-specified choice  of K 

Dimensionality Reduction - high to lower dimensions data set ensuring similar information 

Covariance - measure of the joint variability of two random variables 

vector space - set whose elements often called vectors, Generalize Euclidean vectors that has a magnitude and direction 

subspace - vector space that is a subset of some larger vector space 

Orthonormality - orthonormal vectors are both perpendicular to each other and have a length of 1

Principal component analysis - maps in a high dimension data to a low dimension space. Variance of the data in the lower dimension space should be maximum 

principal components - eigenvecors that are analogous to the principal axes of an ellipse

Neural Networks - mathematical models that use learning algorithms inspired by the brain 

McCullough and Pitts(1944) - arranged to weights but not layers. Results more neuroscience than computer science 

units - artificial neurons
Neural network with at least one hidden layer is a universal approximator (can represent any function).

Capacity of the network increases with more hidden units and more hidden layers

Backpropagation - efficient method for computing gradient-based optimization of the weights in a multi-layet network 

Error gradient is computable for any continuous activation function