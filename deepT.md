# Deep learning: the theoretical way
## Keywords
- layers
- weights
- activation functions
- neurons
- gradient
- backpropagation
- optimizer
- learning rate

## What is it
Deep learning involves learning through layers, in a hierarchical manner. E.g. first learn colours, then contours and finally shapes.

> Deep Learning really took off in the 2000, thanks to the evolution of GPUs.

## Neurons
To learn in this way deep learning tries to emulate the functioning of human neurons, through a mathematical representation.

The inputs are fixed and you want to play around with parameters (weights, bias, activation function) to reach the right output.
In practice often the activation function is fixed.

## Activation functions
- identity: useful for regression
- ReLu: often used in classification
- Tanh: good alternative after having tried ReLu

## Neural network
A layer is the group of all neurons at the same depth
An hidden layer is a layer which is not the first nor the last.

Multiple layers create a multilayer perceptron.

[tensorflow playground](http://playground.tensorflow.org)

At first the predictions will be copletely wrong. You need to have a loss function, which tells you how much off you are. The idea is to change the weights according to the current weights and loss.

A gradient is a function that tells you in which direction a function grows more.
We are going to use the inverse of the gradient to chose in which direction to move, so that we minimize the loss.

To update the weights we use backpropagation to find the gradient for each layer: going from the result to the input

You use an optimizer to adjust the weights in a way that minimizes the loss function.

You could find yourself stuck in a local minimum and which is not the best you, to cope with that you can play around wiht learning rates.

2 optimizers are stochastic gradient descent (SGD) and SGD with momentum

## Type of networks
**fully connected**
Every neuron of a layer is connected to every neuron of the following layer
- 1 for regression
- 2 for binary classification and pick the highest one
- n outputs interpreted with softmax to bring te sum of all the outputs to 1

**Convolutional neural network**
[explanation](http://cs231n.github.io/assets/conv-demo/index.html)
Input Layer -> Convolutional layer: each filter should pick a different feature up
Convolution layer -> Pooling layer: pick the highest

**Autoencoder**
It's composed by an encoder, which extracts the important information from the input, and a decoder, which converts it back to the original format.

**Recurrent neural network**
The output can be fed again as input for some neurons. Those are very useful in natural language processing

## Overfitting
To avoid overfitting at each epoch of learning some neurons are turned off at random, so that the network learns meaningful connection and not connections that are only in your data.

Another technique is stopping the learning before it overfits.

You can also do batch normalization to avoid noise being passed from a layer to the next
