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


