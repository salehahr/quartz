---
title: Variance, standard deviation, covariances
date: "2020-08-31"
external_url: "http://nbviewer.jupyter.org/github/rlabbe/Kalman-and-Bayesian-Filters-in-Python/blob/master/03-Gaussians.ipynb"
tags:
  - -definitions
  - -sa/processed
  - math/statistics
---

Backlinks: [Multivariate Gaussian distributions](multivariate-gaussian-distributions.md)

Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)
See also: [Empirical rule 68/95/99.7](empirical-rule-68_95_99.7.md)

![unknown_filename.1.png](./_resources/Variance,_standard_deviation,_covariances.resources/unknown_filename.1.png)
![unknown_filename.png](./_resources/Variance,_standard_deviation,_covariances.resources/unknown_filename.png)

How much do the values vary from the mean?

![unknown_filename.2.png](./_resources/Variance,_standard_deviation,_covariances.resources/unknown_filename.2.png)

*   There are other ways of calculating variance (e.g. by using absolute values of error instead of error squared).
*   The other methods may be better w.r.t. outliers (outliers get magnified in the square term)

Process variance: error in the process model
Sensor variance: error in each sensor measurement

In multivariate Gaussian distributions, we also calculate covariances:
![unknown_filename.3.png](./_resources/Variance,_standard_deviation,_covariances.resources/unknown_filename.3.png)

and represent them in a covariance matrix (symmetric)
![unknown_filename.4.png](./_resources/Variance,_standard_deviation,_covariances.resources/unknown_filename.4.png)

Covariance calculation in numpy: uses biased estimator by default for small sample sizes (division by (N-1) instead of by N)

