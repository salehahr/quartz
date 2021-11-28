---
title: splitting-dataset
date: 2021-11-27
tags:
  - machine-learning
---

**Parent**: [generalisation](ma/generalisation.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Splitting the dataset

## Strategy 1
* A good performance on the training set doesn't necessarily correspond to good performance on another test set
	* The training set must be large enough (to exclude possibility of underfitting)
	* The training set isn't reused for validation (to exclude possibility of [overfitting](ma/overfitting.md))
* Thus, the idea is, if we only have one large data set, to split it into subsets:
	* The **training set** is used to learn the model weights.
	* The trained model is applied onto the **validation set**
		* The model is generalised if the validation losses are the same as that of the training losses
* How to split?
	* The larger the training set, the better the learning potential
	* But the larger the validation set, the more confident we can be in the model evaluation metrics
	* If the original dataset is large, a 90% to 10% training:validation split can be sufficient
	* If the original dataset is small, cross-validation might be helpful

**Notes**:
* shuffle the data before splitting to prevent only certain clusters of data being used in the training/validation sets
* doing too many evaluations on the validation set (and then tuning the model hyperparameters) can increase the risk of overfitting to that validation set  
	![](/_img/train-validate-workflow.png)
	
## Strategy 2
![](/_img/dataset-split-three.png)  
![](/_img/train-validate-test-workflow.png)

* Training data: for learning model parameters
* Validation data: for evaluating model and tuning the hyperparameters
* Test data: for final testing

If the results on the independent test data are similar to the results on the validation data, this is good (over-fitting probably did not occur)

**Notes**
* Test and validation sets 'wear out' the more they are used.
* The more they are used for tuning, the higher the risk of overfitting.
* To avoid this, new data can be injected into each set.