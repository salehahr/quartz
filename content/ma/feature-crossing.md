---
title: feature-crossing
date: 2021-11-28
tags:
  - machine-learning
---

**Parent**: [data-representation](ma/data-representation.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Synthetic features (feature crossing)
* e.g. generate feature $x_3$ by combining $x_1$ and $x_2$  
	$$x_3 = x_1 x_2$$
* crossing boolean features can result in a very sparse feature set
* a more sophisticated version of feature crossing is a [neural network](ma/neural-networks.md)


## Advantage
Enables learning with nonlinear features while making use of a linear model  
	--> nonlinear features scale well with large scale data sets

## Disadvantage
Crossing sparse features may significantly increase the size of the feature space.

May lead to
* Increased model size (more RAM usage)
* Noise coefficients (of 'redundant' feature subsets created by the cross), [overfitting](ma/overfitting.md)

### Solution
* try to 'zero' out some of those noise coefficients/weights
* must not lose useful features, only the 'noise' ones
* --> [L$_1$ regularisation](ma/l1-regularisation.md)