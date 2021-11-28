---
title: SoftMax
date: 2021-11-28
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# SoftMax
* A more general version of [logistic regression](ma/logistic-regression.md)
* For [multi-class classification](ma/multi-class-classification.md) with unique labels
* Additionally constraints all output nodes to sum up to 1.0
	* Helps convergence
	* Probabilistic interpretation of outputs  	
	![](/_img/softmax.png)
	
	
## Options
* Full SoftMax (brute force): a probability is calculated for every single class
	* Cheap for small number of classes
* Candidate sampling: calculates probability for all positive labels but only for a random sample of negative labels
	* e.g. calculating a probability for `terrier`, `german_shepherd` but not for all of non-dog classes: `cat`, `coat`, `tree`, etc.
	* Possibly more efficient for greater number of classes