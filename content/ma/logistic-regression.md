---
title: logistic-regression
date: 2021-11-28
tags:
  - math
  - machine-learning
---

**See also**: [Linear regression](ma/simple-regression.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Linear logistic regression

* For predicting probabilities (value between 0 and 1)
* As an alternative, it could be possible to [cap the predicted data](ma/scaling-features.md) at 1, but this would be introducing [bias](ma/bias.md) to the model
* Therefore the necessity for a different loss function and data prediction model, which outputs the predicted probabilities


## Sigmoid function
Gives a bounded value between zero and one.
$$
y = \dfrac{1}{1 + e^{-z}}
$$

| Variable | Description                       |
| -------- | --------------------------------- |
| $y$      | Logistic regression output        |
| $z$      | Original model output, 'log-odds' |

$$
z = \log \left( \dfrac{y}{1 - y} \right)
$$

![](/_img/sigmoid.png)

## Log loss
$$
L = \sum_{(x,\,y) \, \in \, D}
	-y \log (y') - (1 - y) \log (1 - y')
$$
![](/_img/log-loss.png)

## Regularisation for logistic regression
* [Regularisation](ma/regularisation.md) is very important!
* Due to the asymptotes in the log loss function, the model will try to drive the losses to zero but will never reach this, so the model weights will approach infinity
* --> use [L$_2$ regularisation](ma/l2-regularisation.md) or [early stopping](ma/regularisation.md)