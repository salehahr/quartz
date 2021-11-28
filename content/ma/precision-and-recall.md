---
title: precision-and-recall
date: 2021-11-28
tags:
  - machine-learning
---

**Parent**: [classification](ma/classification.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Precision and Recall

## Precision
true positives / all positive predictions 

$$\dfrac{\text{TP}}{\text{TP} + \text{FP}}$$

* "What fraction of positive predictions were actually correct?" — focus on the correctness of the positive *predictions*
* or: "Did the model predict positive too often?"
* e.g. precision = 0.5, model is correct 50% of the time


## Recall / True Positive Rate (TPR)
true positives / all actual positives

$$\dfrac{\text{TP}}{\text{TP} + \text{FN}}$$

* "What fraction of actual positives were identified correctly?" — focus on the identification of the *actual* positives
* or: "How many misses?"
* e.g. recall = 0.11, model correctly identifies 11% of the actual positive cases


# Trade-off between precision and recall
* Increased precision: predict positive only when we are confident in the positive prediction
	* --> increasing the classification threshold / casting a smaller net
	* reduces false positives
* Increased recall: predict more positive so as to prevent the number of misses
	* --> lowering the classification threshold / casting a wider net to catch all actual positive cases
	* reduces false negatives
	* increases false positives
* Always look at both precision and recall!