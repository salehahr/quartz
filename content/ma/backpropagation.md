---
title: Backpropagation
date: 2021-11-28
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Backpropagation
[Gradient descent](ma/gradient-descent.md) for [neural networks](ma/neural-networks.md)

## Idea
Gradience/the need for differentiable functions: things need to be differentiable in order for learning to occur

## Problems
* Vanishing gradients
	* In too deep networks, the signal to noise ratio gets worse further in the model
	* Thus the gradients for the initial layers can approach zero
	* Learning becomes slow
	* Strategies:
		* Limit model depth
		* Use ReLUs
* Exploding gradients
	* Especially if learning rates are too high, weights too large --> NaNs in model
	* Gradients in initial layers explode, become too large to converge
	* Strategies:
		* Lower learning rate
		* Batch normalisation
* ReLU layers can 'die'
	* Due to the cap at zero
	* If values end up being below zero then the gradients can't get backpropagated
	* Strategies:
		* Different initialisation
		* Lower learning rate

## Tricks
* [Scaling/normalising features](ma/scaling-features.md)   
	If features are roughly on the same scale, this can make convergence faster
* [Dropout](ma/dropout.md)