---
title: scaling-features
date: 2021-11-27
tags:
  - machine-learning
---

**Parent**: [data-representation](ma/data-representation.md)

**Source**: [google-ml-course](bibliography/google-ml-course.md)

# Scaling/normalising feature values
* No benefit if only one feature in the feature set
* Can be beneficial for multifeature set
	* Helps the gradient descent to converge more quickly
	* Helps avoid numbers becoming NaN
	* Makes the model spend the same time learning for each feature vector. If scaling is not done, more learning is done for features which have a bigger range of data.
* Scaling methods
	* Map [min, max] to [-1, +1]
	* Use Z scores  
		$$ Z = \frac{x - \mu}{\sigma} $$  
		which results in most values lying within [-3, +3]
	* Log scaling for data with very big difference between min and max value (might still not be very ideal)
* Clipping/capping at a max value (this doesn't mean all values exceeding the max are thrown out, instead the outlier values get mapped to the max value)


| Original                | Log                        | Clipped                     |
| ----------------------- | -------------------------- | --------------------------- |
| ![](/_img/unscaled.png) | ![](/_img/log-scaling.png) | ![](/_img/clip-scaling.png) |
