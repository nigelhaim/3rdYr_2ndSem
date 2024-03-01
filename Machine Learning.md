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


>[!Note]- Confusion Matrix
>![[Pasted image 20240223203438.png]]

# Formulas

$$Precision  = \frac{\text{True Positives}}{\text{True Positives + False Positive}}$$

$$Accuracy = \frac{\text{True positives + True Negatives}}{\text{True positives + True negatives + False positives + False negatives}}$$
$$Recall = \frac{\text{True positive}}{\text{True positives + False negatives}}$$
$$F1 = \frac{2*\text{Precision}*\text{Recall}}{\text{Precision + Recall}}$$