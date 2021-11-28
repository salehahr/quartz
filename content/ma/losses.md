---
title: losses
date: 2021-11-27
tags:
  - machine-learning
---

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Losses

## Losses according to dataset
* Training loss
* Validation loss — this is the one that matters, as this is the measure of the model's ability to predict on new and unseen data

## Losses according to definition
### Mean square error
* Average square loss of the whole dataset.
* The greater the prediction disparity, the higher the penalisation (squared amplification)  
	e.g. a disparity of 2 units results in a loss 4x bigger than a disparity of 1 unit

#### Single datapoint
L$_2$ loss, squared error
$$\left(\mathbf{y} - \mathbf{f}(\mathbf{x})\right)^\text{T}
\left(\mathbf{y} - \mathbf{f}(\mathbf{x})\right)$$

#### Whole dataset $D$
$$
\begin{align}
\text{MSE} &= \frac{1}{N}\sum_{(x,y) \in D}
	\left( y - f(x)
	\right)^2
\end{align}
$$
