---
title: l2-regularisation
date: 2021-11-28
tags:
  - machine-learning
---

**Parent**: [regularisation](ma/regularisation.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# L$_2$ regularisation / Ridge regularisation
Model complexity is given by the sum of the squares of the weights[^1]

[^1]: Just one metric out of several possible ways of measuring model complexity.

$$
\begin{align}
&\min L(x, y, \text{model}) + \lambda
\left\lVert \mathbf{w} \right\rVert_2^2
\end{align}
$$

with the L$_2$ regularisation term
$$
\left\lVert \mathbf{w} \right\rVert_2^2
= \left( w_1^2 + \dots + w_n^2 \right)
$$

and the [regularisation rate $\lambda$](ma/regularisation-rate.md) determines whether the total loss is more dependent on the training loss or on the model complexity.


**Note**:
* If training data is abundant and looks similar to the test data (i.i.d.), then regularisation is potentially unnecessary.


## Effect
* Weight values tend toward zero
* Distribution of weights tends toward a normal distribution with zero mean

