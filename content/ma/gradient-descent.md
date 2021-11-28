---
title: gradient-descent
date: 2021-11-27
tags:
  - math
  - machine-learning
---

**Parent**: [Variations of gradient descent](ma/variations-gradient-descent.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)


# Gradient descent
![](/_img/ml-iteration.png)

An iterated approach
1. Labeled data arrives
3. Gradient of the loss function is computed
4. Now the direction for updating the model parameters $\mathbf{w}$ is known (negative gradient).
5. A step is taken in this direction, in the parameter space. The step size is equivalent to the [learning rate](ma/learning-rate.md).
6. Repeat

![](/_img/gradient-descent.png)

This process tunes all model parameters **simultaneously**.


#### Notes
* Works well for [convex problems](ma/convex-problems.md) (loss function w.r.t. parameters is convex);
	the convex loss function converges at the minimum
* But many ML problems are not convex, e.g. neural networks
* [Variations of gradient descent](ma/variations-gradient-descent.md)