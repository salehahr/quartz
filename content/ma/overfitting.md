---
title: overfitting
date: 2021-11-28
tags:
  - machine-learning
---

**Parent**: [generalisation](ma/generalisation.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Overfitting
Model is overly specific
* is only usable to predict a subset of input data (the training data that was used to train the model)
* model would have been fitted to the specific properties of the dataset used, e.g. if the dataset was noisy, and overfitted model takes into account the noise of this particular dataset
* not usable on new data --> not generalisable

![](/_img/overfitting.png)

![](/_img/overfitting-loss.png)