###### ECE472 (Deep Learning) Final Project
# Quadratic Neurons as Activation Functions in Deep Neural Networks
### By Andrew Lorber & Mark Koszykowski
----
_Abstract_: Our final project for Deep Learning built upon the work of Yaparla Ganesh and Rhishi Pratap Singh in _Pattern Classification using Quadratic Neuron: An Experimental Study_. Their paper discusses the use of quadratic (QUAD) neurons to build quadratic neural networks, as opposed to the familiar linear neurons in multilayer perceptron (MLP) models. This paper displays the use of their quadratic neuron as a Quadratic Activation Function. Comparisons are made between the Sigmoid activation, ReLu activation, and two new types of quadratic activations. Extensive experimentation was conducted on toy datasets, such as MNIST, CIFAR10, Spirals, Circles, and more. Empirical results display the use of these Quadratic Activation Functions and motivate further study on the topic.

----
#### This repository contains our research paper on this topic and the source code for our Quadratic Activation Functions.

The Quadratic Activation Function is an extension of Ganesh and Singh’s Quadratic Neuron Model. Similar to their model, the output of this activation function is calculated using the non-linear equation Ax<sup>2</sup>+By<sup>2</sup>+Cxy+Dx+Ey+F = 0. Since the activation function requires two input values, the width of each layer passing through this activation will be halved.

In Ganesh and Singh’s model, each neuron had its own learned parameters A, B, C, D, E, and F. For the purpose of this study, two versions of the activation function were built: _The Quadratic Activation Function with Layer-Wide Coefficients_ and _The Quadratic Activation Function with Per-Neuron Coefficients_. In these two versions of the activation, two neurons from the previous layer are chosen, used to calculate the rest of the input parameters, and used in the above equation with the learned parameters. The activations described were implemented as custom Tensorflow Layers.

  - _Layer-Wide Coefficients_: This version of the Quadratic Activation Function uses a single set of coefficients (A, B, C, D, E, F) for each activation function within a given layer. For example, if this version of the Quadratic Activation Function were to be used following a 64 neuron dense layer, then this activation layer would learn only 6 coefficients.

  - _Per-Neuron Coefficients_: This version of the Quadatic Activation Function uses a different learned set of coefficients (A, B, C, D, E, F) for each activation function within a given layer. For example, if this version of the Quadratic Activation Function were to be used following a 64 neuron
dense layer, then this activation layer would learn 192 (64 / 2 × 6) different coefficients, 6 per activation function.

In addition to the two activation functions described, a variation of each was built in order to work with convolutional layers. Unlike the Quadratic activation layer following a dense layer, in which the selection of neurons for x and y could be done randomly, the Quadratic activation layer following a convolution layer needs to use neighboring neurons, as to maintain the original image. Two versions of The Quadratic Activation Function for Convolutional Layers were made as well: _Layer-Wide Coefficients_ and _Per-Neuron Coefficients_. 
