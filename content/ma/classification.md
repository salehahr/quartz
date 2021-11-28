---
title: classification
date: 2021-11-28
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Classification
* [Logistic regression](ma/logistic-regression.md) returns a probability
* This probability can be converted to a binary value by making use of a classification threshold
* Classification/decision threshold: the value which splits between true and false  
	![](/_img/classification-threshold.png)
* s. [confusion matrix](ma/confusion-matrix.md), which contains information used for the performance metrics


## Evaluation metrics
* One possibility: accuracy (fraction of correct predictions over total predictions)  
	* $\dfrac{\text{TP} + \text{TN}}{\text{all predictions}}$
	* Poor metric, especially when working with datasets with class imbalance (significant difference between number of positive and negative labels) 
		e.g. when prediction would almost always return false -- accuracy would be close to 100% but this doesn't say anything about the model!
* [Precision and recall](ma/precision-and-recall.md)
* [Bias](ma/bias.md)


## Model performance for all possible classification thresholds
### Receiver Operating Characteristics (ROC) curve
* Each point on the curve is the TP rate ([recall](ma/precision-and-recall.md)) and FP rate at one decision threshold

$$
\begin{align}
\text{TPR} &= \dfrac{\text{TP}}{\text{TP} + \text{FN}}
	= \dfrac{\text{TP}}{\text{actual positives}}\\
\text{FPR} &= \dfrac{\text{FP}}{\text{FP} + \text{TN}}
	= \dfrac{\text{FP}}{\text{actual negatives}}
\end{align}
$$

![](/_img/roc-curve.png)

### Area under the ROC Curve (AUC)
* Probability of getting a pairwise (pick a random positive and a random negative) comparison correct, i.e. assigning a higher score to the positive — probability of the model ranking a random positive example higher than a random negative example
* Aggregate measure of performance across all possible decision thresholds (as opposed to calculating TPR and FPR for each threshold in the ROC)
* e.g. probability that a random green point (actual positive) is to the right of a random red point (actual negative)  	
	![](/_img/auc-example.png)
* perfect ROC with AUC = 1.0
	![](/_img/perfect-roc.png)

#### Advantages:
* AUC is scale-invariant, independent on absolute values of the predictions
* AUC is classification-threshold-invariant

#### Disadvantages:
* When scale invariance is not always desirable (when we need well calibrated probability outputs)
* When classification-threshold-invariance isn't desired, e.g. when there is a big cost difference between false negatives and false positives
	* e.g. in email spam detection, a false positive (legit email marked as spam) is much worse than a false negative (spam comes through)
	* we would therefore want to minimise false positives (lower the classification threshold)