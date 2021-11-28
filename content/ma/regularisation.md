---
title: regularisation
date: 2021-11-27
tags:
  - machine-learning
---

**Parent**: [Generalisation](ma/generalisation.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Regularisation

* So far: penalisation of wrong predictions [empirical risk minimisation]  
	$$ \min L(x, y, \text{model})$$
* Now: penalise model complexity [structural risk minimisation] to prevent [overfitting](ma/overfitting.md)
	$$ \min L(x, y, \text{model}) + \text{complexity}(\text{model})$$
* Some metrics for model complexity
	* Function of the weights
	* Function of the total number of features with nonzero weights
* Types
	* Early stopping: stop the training before convergence (while using the training data)
	* [L$_0$ regularisation](ma/l0-regularisation.md)
	* [L$_1$ regularisation](ma/l1-regularisation.md)
	* [L$_2$ regularisation](ma/l2-regularisation.md)
	* [Dropout](ma/dropout.md)

## L$_1$ vs. L$_2$ regularisation
| Type  | Penalises              | Derivative                  |
| ----- | ---------------------- | --------------------------- |
| L$_2$ | weight$^2$             | $2*$ weight                 |
| L$_1$ | $\vert$ weight $\vert$ | const. $k$ indep. of weight |

