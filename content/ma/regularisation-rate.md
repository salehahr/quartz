---
title: regularisation-rate
date: 2021-11-28
tags:
  - machine-learning
---

**Parent**: [Hyperparameters](ma/hyperparameters.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Regularisation rate $\lambda$
* If $\lambda$ too high: simpler model, risk of underfitting (not enough training being done)
* If $\lambda$ too low: model more complex, risk of [overfitting](ma/overfitting.md)
* Ideal $\lambda$ depends on data --> needs to be tuned
* Strong L$_2$ regularisation has similar effect to that of lower learning rate (smaller step size)
	* High regularisation drives weights towards zero
	* Lower [learning rates](ma/learning-rate.md) result in lower step sizes, and the steps towards zero (in parameter space) are smaller than steps away
	* Therefore tuning $\alpha$ and $\lambda$ simultaneously could be a bit confusing
	* Ensure that there are a high enough number of iterations (so that effect of [early stopping](ma/regularisation.md) doesn't affect the tuning of $\lambda$)