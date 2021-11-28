---
title: learning-rate
date: 2021-11-27
tags:
  - machine-learning
---

**Parent**: [Hyperparameters](ma/hyperparameters.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Hyperparameter 'learning rate' $\alpha$
-   Small learning rate: small steps, long time to reach the minimum
	![](/_img/small-learning-rate.png)
-   Big learning rate: big steps, shorter computation time but with potential to overshoot the minimum
	![](/_img/high-learning-rate.png)
	
## Ideal learning rate
In 1D: the inverse of the second derivative of the model
$$
\begin{align}
\alpha = \frac{1}{f(x)''}
\end{align}
$$

In $\geq$ 2D: inverse of the Hessian