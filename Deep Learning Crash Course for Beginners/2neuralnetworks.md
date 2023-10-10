# Neural Networks

deep learning models refer to the training of things called neural networks

neural networks form the basis of deep learning a sub-field of machine learning where algorithms are "inspired by the structure of the human brain"

just like neurons make up the brain the fundamental building blocks of a neural network is also a neuron

neural networks take in data, they train themselves to recognize patterns in this data and predict outputs for a new set of similar data

1. Take in data as input
2. Train themselves to understand patterns in the data
3. Output useful predictions

in a neural network, information propagates through three central components that form the basis of every neural network architecture 
1. the input layer 
2. the output layer and 
3. several hidden layers between the two


### the learning process of a neural network

the learning process of a neural network can be broken into two main processes 
1. forward propagation and 
2. back propagation

# forward propagation

forward propagation is the propagation of information from the input layer to the output layer 

* we can define our input layer as several neurons x1 through xn 
* these neurons connect to the neurons of the next layer through channels and they are assigned numerical values called weights 
* the inputs are multiplied to the weights and their sum is sent as input to the neurons in the hidden layer where each neuron in turn is associated to a numerical value called the bias which is then added to the input sum
* this weighted sum is then passed through a non-linear function called the activation function(σ-Sigma) which essentially
decides if that particular neuron can contribute to the next layer 
* in the output layer it's basically a form of probability(ˆy) the neuron with the highest value determines what the output finally is

## terms
so let's go over a few terms
Weight - how important is that neuron

Bias - allows for the shifting of σ(sigma) to the right or left

* Weight - the weight of a neuron tells us how important the neuron is. The higher the value the more important it is in the relationship.

* Bias - the bias is like the new on having an opinion to the relationship. It serves to shift the activation function to the right or to the left.  

if you have had some experience with high school math you should know that adding a scalar value to a function shifts a graph either to the left or to the right and this is exactly what the bias does it shifts the activation function to the
right or to the left

#### [In mathematics, adding a scalar value to a function indeed results in a horizontal shift of the graph either to the left or right. This concept is particularly relevant when discussing neural networks and activation functions in deep learning. In the context of deep learning, the term "bias" refers to a learnable parameter within a neuron or node of a neural network. The bias serves a similar purpose as adding a scalar value to a function in mathematics. It allows the activation function of the neuron to be shifted horizontally, affecting when and how the neuron activates in response to input data.
#### For example, in a sigmoid activation function used in neural networks, adjusting the bias value shifts the sigmoid curve left or right along the x-axis. This shift can influence the neuron's responsiveness to certain inputs. Positive bias values shift the curve to the left, making the neuron more likely to activate for smaller inputs, while negative bias values shift the curve to the right, making the neuron more likely to activate for larger inputs. So, just as adding a scalar value shifts a function's graph in mathematics, adjusting the bias in a neural network shifts the activation function, allowing for fine-tuning of the model's behavior in response to different input data.] 


# back propagation

* back propagation is almost like forward propagation except in the reverse direction 
* information here is passed from the output layer to the hidden layers not the input layer
* but what information gets passed on from the output layer?

isn't the output layer supposed to be the final layer where we get the final output
well yes but no!!!
back propagation is the reason why new networks is so powerful!
it is the reason why neural networks can learn by themselves!!!

in the last step before propagation, a neural network spits out a prediction

this prediction could have two possibilities------> `either right or wrong`

in back propagation, the new network evaluates its own performance and checks if it is right or wrong!!!

* if it is wrong, the network uses something called a loss function to quantify the deviation from
the expected output and it is this information that's sent back to the hidden layers for the weights and biases to be adjusted so that the network's accuracy level increases 

# example
let's visualize the training process with a real example

let's suppose we have a data set(car-truck dataset). this dataset gives us the weight of a vehicle and the number of goods carried by that vehicle and also tells us if those vehicles are cars or trucks.

we want to go through this data, train a new networks to predict cars or trucks based on their weights and goods 

to start off let's initialize the neural network by giving it random weights and biases these can be anything we really
don't care what these values are as long as they're there

1. in the first entry of a data set, we have vehicle weight equal to a value which in this case is 15 and good as two
according to this it's a car we now start moving these input dimensions through the newer network so
basically what we want to do is take both the inputs multiply them by their weight and add a bias
and this is where the magic happens we run this weighted sum through an activation function okay now let's say that the output of this activation function is 0.001.

2. this again is multiplied by the weight and added to the bias and finally in the output layer. 
we have a guess now according to this neural network the type of vehicle with weight 15 and goods 2 has a greater probability of being a truck of course this is not true and a neural network knows this 

so we use back propagation

we're going to quantify the `difference between the expected result and the predicted output` using a loss
function in back propagation we're going to go backwards and adjust our initial rates and biases remember that during
the initialization of the neural network we chose completely random weight and biases

well during back propagation these values will be adjusted to better fit the prediction model
okay so that was one iteration through the first piece of the data set 

3. in the second entry we have vehicle weight 34 and goods 67.

we're going to use the same process as before multiply the input with the weight and add a box pass this result
into an activation function and repeat till the output layer check the error difference and employ back propagation
to adjust the weights in the biases. your neural network will continue doing this repeated processor for propagation
calculating the error and then back propagation for as many entries there are in this data set

the more data you give the newer network the better it will be at predicting the right output but there's a tradeoff
because too much data and you'll end up with a problem like overfitting which i'll discuss later in this course but
that's essentially how a neural network works you feed input the network initializes with random weights and
biases that are adjusted each time during back propagation until the network's gone through all your data and is now able to make predictions

## Time for Back Propagation
1. Use a Loss Function
2. Go backwards & adjust initial weights and biases
3. Values adjusted to better fit prediction model

#### Learning Algorithm
1. Initialize parameters with random values
2. Feed input data to network
3. Compare predicted value with expected value & calculate loss
4. Perform Backpropagation to propagate this loss back through the network
5. Update Parameters based on the loss
6. Iterate previous steps till loss is minimized

### this learning algorithm can be summarized as follows 
* first we initialize the network with random values for the network's parameters or the weights in the biases 
* we take a set of input data and pass them through the network 
* we compare these predictions obtained with the values of the expected labels and calculate the loss using a loss function
* we perform back propagation in order to propagate this loss to each and every weight and bias
* we use this propagated information to update the weights and biases of neural network with the gradient descent
algorithm in such a way that the total loss is reduced and a better model is obtained
* the last step is continue iterating the previous steps until we consider that we have a good enough model


