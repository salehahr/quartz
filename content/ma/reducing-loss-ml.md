---
title: reducing-loss-ml
date: 2021-11-27
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)  

# Reducing loss in ML
Aim: compute model parameters (weights) such that [loss](ma/losses.md) is minimal
-   For which parameters does the loss converge? (Reach a minimum)
-   How to get these optimal model parameters? --> which direction do we go in the parameter space?
-   One possibility: compute the gradient and steer the model parameters based on the gradient --> [gradient descent](ma/gradient-descent.md), [variations of gradient descent](ma/variations-gradient-descent.md)
-   In [neural networks](ma/neural-networks.md): [backpropagation](ma/backpropagation.md)

**Gradient**: derivative of the loss function with respect to the model parameters
$$
\begin{align}
\dfrac{\partial L}{\partial \mathbf{w}}
\end{align}
$$