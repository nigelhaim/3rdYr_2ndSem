
**Convolutional neural network** is a regularized type of feed-forward neural network that learns feature engineering by itself via filters optimization.


A digital image is a 2D grid of pixels 

A neural network expects a vector of numbers as input 

Locality: nearby pixels are more strongly correlated 
Translation invariance: meaningful patterns can occur anywhere in the image 
Weight sharing: use the same network parameters to detect local patterns as many locations in the image. 
Hierarchy: Local low-level features are composed into larger, more abstract features

![[Pasted image 20240524143657.png]]

Kernel slides across the image and produces an output value at each position

![[Pasted image 20240524143807.png]]

Aside: What are Filters? 

You apply the filter or kernel to the input to create a feature map 

But what is a filter or kernel anyway? 

Filtering is a technique for modifying or enhancing an image. For example, you can filter an image to emphasize certain features or remove other features. 

For traditional image processing and computer vision research, academics would often derive these filters and handcraft them 

Convolutional neural networks on the other hand, leverage on backpropagation to learn these filters

These learned filters will then generate good feature maps that can be fed to a classifier for prediction

Padding. It is the amount of pixels added to an image when it is being processed by the kernel of a CNN

Stride Convolution: kernel slides along the image with a step > 1

Dilated Convolution: kernel is spread out, step > 1 between kernel elements

Pooling: Compute mean or max over small window to reduce resolution

LeNet-5 a convent for handwritten digit recognition

Alexnet: 8 Layers, ReLU, dropout, weight decay 

BGGNet: Stack many convolutional layers before pooling use "Same" convolutions to avoid resolution reduction

Batch Normalization - Reduces Sensitivity to initialisation introdcues stochasticity and acts as a regulariser

Residual connections facilitate training deeper networks 

ResNet V2 (bottom) avoids all nonlinearities in the residual pathway 

Data augmentation makes them robust against other transformations

A recurrent neural network is a type of neural network made for sequential data. They take information from prior inputs to influence the current input and output.

sequence - collection of where elements can be repeated, order matters, and are of variable length

Loss: Cross Entropy - Next word prediction is essentially a classification task where the number of classes is the size of the vocabulary 

Long Short-Term Memory Networks is a special type of RNN which is capable of handling the vanishing gradient problem faced by RNN

A Seq2Seq model is a model that takes a sequence of items (words, letters, time series, etc) and outputs another sequence of items.

Attention mechanisms enhance deep learning models by selectively focusing on important input elements, improving prediction accuracy and efficiency


A transformer is a deep learning architecture, initially proposed in 2017, that relies on the parallel multi-head attention mechanism.

learn word associations from a large corpus of text.


Representation learning is a set of techniques that allows a system to automatically discover the representations needed for feature detection or classification from raw data.

Autoencoders - It learns how to efficiently and effectively encode data then learns how to reconstruct the data back from the encoded representation


Bottle necks = lower dimensional hidden layer where the encoding is produced

sparse autoencoder is selectively activate regions of the network depending on the input data.

A generative adversarial network (GAN) is a class of neural network architectures and a prominent framework for approaching generative AI.

Implicit generative models implicitly define a probability distribution

generator network tries to produce realistic-looking samples

e discriminator tries to figure out whether an image came from the training set or the generator network

Reinforcement learning is a machine learning training method based on rewarding desired behaviors and punishing undesired ones.

Interactions are often sequential, future actions can depend on previous ones

A Markov Chain is a stochastic model describing a sequence of possible events in which the probability of each event only depends on the state attained in the previous event

Marcov Decision process It provides a mathematical framework for modelling decision-making in situations where outcomes are partly random and partly under control of a decision-maker

![[Pasted image 20240524170220.png]]
A policy gives an action for each state

n optimal policy is one that maximizes expected utility if followed

Value Iteration dynamic-programming method for finding the optimal value function by solving the Bellman equations iteratively.

policy evaluation process calculates the expected cumulative reward for each state under a specific policy

Policy iteration is a dynamic programming technique for calculating a policy directly, rather than calculating an optimal and extracting a policy