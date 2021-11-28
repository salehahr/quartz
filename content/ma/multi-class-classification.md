---
title: multi-class-classification
date: 2021-11-28
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Multi-class classification
* Building off on [binary classification](ma/classification.md) --> do one-vs-all classification, e.g. for the classes red-blue-yellow:
	* Red vs not red
	* Blue vs not blue
	* Yellow vs not yellow	 
	![](/_img/one-vs-all.png)
* For unique classes: [SoftMax](ma/softmax.md) can be used, where the sum of the outputs is one
* For non-unique classes: one-vs-all classification with multiple [logistic regressions](ma/logistic-regression.md), the sum of the outputs need not be one