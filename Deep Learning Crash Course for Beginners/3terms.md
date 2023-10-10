# Terms Used in Neural Networks

### Overview
# 1. Activation Functions
* Introduce Non-Linearity in the Network
* Decide whether a neuron can contribute to the next layer

#### Activation functions introduce non-linearity in neural networks, enabling them to model complex relationships in data. Unlike linear functions, which produce a linear output based on input, activation functions apply a mathematical operation to the input and produce non-linear outputs. This non-linearity allows neural networks to approximate and learn complex patterns, making them suitable for various tasks like image recognition and natural language processing.

#### Common activation functions include ReLU (Rectified Linear Unit), sigmoid, and tanh. ReLU, for instance, outputs the input if it's positive and zero if negative, introducing non-linearity by breaking the linearity at zero.

#### The introduction of non-linearity is crucial because real-world data is rarely linear. Activation functions enable neural networks to capture intricate features and make accurate predictions. Different activation functions may be more suitable for specific tasks, and choosing the right one is an important aspect of designing effective neural networks.

But, how do we decide if a neuron can fire/activate or not?
## a. Step Function 
If value > 0 ---> Activate
else ----> Don't activate
0 is the "threshold"
Drawback: Doesn't model every situation

## b. Linear Function
Derivate is constant
y = mx + b
Derivate, y' = m
Output y E (-infinity, infinity)

## c. Sigmoid Function
Non-Linear
Analog Outputs
sig(t) E (0,1)
Vanishing Gradient Problem

## d. Tanh Function
Non-linear
Vanishing Gradient Problem

## e. ReLU Function(Rectified Linear Unit)
R(z) = max(0,z)
R(z) E [0, infinity)
Non-Linear
Sparse Activations
Gradient = 0
Dying ReLU Problem

f. Leaky ReLU Function

## Which Activation Function to Use?

Binary Classification Problems: Sigmoid
If you're unsure: ReLU(or modified ReLU)

## Why Non-Linear Activation Functions?

# 2. Loss Function
Quantify the deviation of the `predicted` output by the neural network to the `expected` output

Different types of Loss functions depending on the project you're working on

Regression: Squared Error, Huber Loss

Binary Classification: Binary Cross-Entropy, Hinge Loss

Multi-Class Classification: Multi-Class Cross-Entropy, Kullback Divergence

# 3. Optimizers
During trainig, we adjust the parameters to minimize the loss function and make our model as optimized as possible.

But, HOW do we do that?

1. Tie together the loss function and model parameters by updating the network based on the output of the loss function.
2. Loss Functions guide optimizers

You = Neural Network
Descending = Minimizing the Error
Feet = Loss Functions

# Gradient Descent - The Granddaddy of Optimizers

Iterative Algorithm that starts off at a random point on the loss function and travels down its slope in steps until it reaches the lowest point(minimum) of the function.
Most Popular Optimizer
Fast, Robust, Flexible

## Algorithm
1. Calculate what a small change in each individual weight would do to the loss function
2. Adjust each paramter based on its gradient(i.e. take a small step in the determined direction)
3. Repeat steps 1 and 2 until the loss function is as low as possible

# Gradient
The Gradient of a Function is the vector of partial derivatives with respect to all independent variables
f(x,y) = ((∂ f/ ∂ x(x,y) ,  ∂f/ ∂ y(x,y))

In Gradient Descent, we ideally want to find the `global minimum` of the loss function

To avoid getting stuck in a local minima, we use the proper `Learning Rate`

# Learning Rate
Usually a small number, like .001, that are multiplied to scale the gradients
Ensures that any changes made to the weights are quite small
We dont want a large learning rate, where the algorithm will `overshoot` the global minimum.
Similarly, we dont want one too small, where the algorithm will take `forever ` to converge to the global minimum

# Stochastic Gradient Descent
Like Gradient Descent, except uses a subset of training examples rather than the entire lot.

SGD is an implementation of Gradient Descent that uses batcges on each pass

Uses momentum to accumulate gradients

Less intensive computationally

Backpropagation --> Gradient Descent implemented on a network

# Adagrad

Adapts Learning Rate to individual features

Some weights will have different learning rates

Ideal for sparse datasets with many input examples missing

Learning rate tends to get small with time

# RMSprop
Specialized version of Adagrad

Accumulates Gradients in a fixed window

Similar to Adaprop

# Adam
Stands for Adaptive Moment Estimation

Uses the concept of momentum

Pretty widespread today

## Closing Thoughts
1. It's easy to get lost with so many optimizers
2. All have the same goal: Minimizing that loss function
3. Trial & Error will get you there!

--------------------------------------------------------------------------------------------------------------------------
### Explaination in Brief
the most common terminologies used in deep learning today

!. let's start off with the activation function
the activation function serves to introduce something called non-linearity into the network and also decides whether a particular neuron can contribute to the next layer but how do you decide if the neuron can fire or activate

well we had a couple of ideas which led to the creation of different activation functions

* the first idea we had is how about we activate the neuron if it is above a certain value or threshold 
* if it is less than the threshold don't activate it
* activation function a is equal to activated if y is greater than some threshold else it's not
* this is essentially a step function its output is 1 or activated when value is greater than 0. 

# drawbacks

think about a case where you want to classify multiple such neurons into classes say 
class 1 class 2 class 3 etc

what will happen if more than one neuron is activated?

All these neurons will output a one. How do you decide now how do you decide which class it belongs to?
it's complicated!!!

you would want the network to activate only one neuron and the other should be zero. only then you would be able to say it was classified properly.

in real practice however it is harder to train and converge it this way. it would be better if the activation was not
binary and instead some probable value like 75 activated or 16 activated there's a 75 chance that it belongs to class 2 etc.

then if more than one neuron activates you could find which neuron fires based on which has the highest probability
okay maybe you'll ask yourself i want something to give me a more analog value rather than just saying activated or not
activated something other than in binary and maybe you would have thought about a `linear function` a straight line function where `the activation is proportional to the input by a value called the slope of the line`





