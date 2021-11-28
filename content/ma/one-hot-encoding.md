---
title: one-hot-encoding
date: 2021-11-27
tags:
  - machine-learning
---

**Parent**: [data-representation](ma/data-representation.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# One-hot encoding  
* We can assign each class to a unique coefficient, i.e. maps a category to a number.  
* The problem with this (using integer coefficients)
	* These coefficients get bundled in with the ML math and the weights learned are specific to the defined coefficient code.  
		$$ \text{model} = \sum \text{weight} * \text{feature}$$  
		The weight for the specified feature vector is multiplied with all values of the feature, in this case the coefficients... what happens if we add a new class and/or change the coefficient code?
	* No accounting for data which belong to multiple classes.
* Solution: transform to a binary vector notation
* Useful for sparse, categorical data.
* Multi-hot encoding when multiple values are allowed to be one.

![](/_img/one-hot-encoding.png)