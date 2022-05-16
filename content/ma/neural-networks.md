---
title: neural-networks
date: 2021-11-28
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Neural networks
* Goal: we want the model to learn the nonlinear features itself without us having to manually define the nonlinear features
* More sophisticated version of [feature crosses](ma/feature-crossing.md)
* Automatic learning of the feature crosses

## Linear model
Each input (feature) is assigned a weight and the weight combination of all these features result in the output.  
![](/_img/linear-model.png)  


### Incorporate nonlinearity
Add another layer of features?  
![](/_img/linear-model-with-hidden-layer.png)  
* not linear yet
* linear combination of linear functions is still linear
* solution: do a nonlinear transform between layers (activation function)

## Activation function
### Sigmoid function
$$ F(x) = \dfrac{1}{1 + e^{-x}} $$

![](/_img/sigmoid.png)


### Rectified Linear Unit (ReLU)
Caps value (from the bottom) at 0.

$$ F(x) = \max (0, x)$$

![](/_img/relu.png)

* Often works better than the sigmoid function (from empirical findings)
* This is probably due to the responsiveness of the ReLU function compared to the sigmoid (flat gradient on extreme ends of the sigmoid)


### Notes
(taken from class notes)
* If no (nonlinear) activation functions are used:
    * in the case of a FCN, all hidden layers are parametrised by weights and biases (input to output is mapped by an affine function $y = Wx + b$)
    * if no nonlinearity is present between each mapping, the whole network then reduces to an affine mapping between the input and the output
    * so no nonlinear activations effectively render all hidden layers useless, reduces the neural newrok to a one layer perceptron
        $$ x_L = Wx_0 + b$$
* Alternatively, if activation function $\phi$ available but no hidden layers:
    $$x_L = x_1 = \phi( W_1x_0 + b_1 )$$
  * network is not able to approximate a general nonlinear I/O mapping
  * activation function $\phi$ is often monotone increasing, and this has no effect for maximising the network output in classification

## Training the neural network
* Due to the incorporated nonlinearities and layers: non-convex optimisation
* **Initialisation may be important**
* Perform [backpropagation](ma/backpropagation.md) (variant of [gradient descent](ma/gradient-descent.md) for non-convex optimisation) to train the weights 

## Notes
* The greater the number of neurons in a single hidden layer, the greater the redundancy
	* No redundancy: neuron is 'lost' during a run
	* With redundancy: increased likelihood of converging to a good model
* The more layers: the more complexity because of more 'crossings' between intermediate features --> result in the modeling of more complex topology
* It might make sense to have more nodes in the first layer to provide more base features for crossing in the next layer
* A first hidden layer with only one neuron can never be used to train a good model, no matter how deep the layers are.
	* The output of this first hidden layer will then only vary along one dimension
	* Later layers are not able to compensate for this
* Caution: [overfitting](ma/overfitting.md) with models which are too complex and too deep