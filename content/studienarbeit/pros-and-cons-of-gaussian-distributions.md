---
title: Pros and cons of Gaussian distributions
date: "2020-08-31"
tags:
  - -sa/processed
  - math/statistics
---

Parent: [Gaussian distribution](gaussian-distribution.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Big advantage of using Gaussian distributions (as opposed to discrete ones w/ histogram bins): less data, b/c a Gaussian distribution is represented fully using only two values: the mean and the variance
![unknown_filename.png](./_resources/Pros_and_cons_of_Gaussian_distributions.resources/unknown_filename.png)

Limitations of using Gaussian distributions to model the world
i.e. deviations from the central limit theorem

*   Not all situations are describable by Gaussian distributions
    *   e.g. sensors in the real world have fat tails (kurtosis) — don't extend to infinity and skew
*   Can't depict any arbitrary probability distributions like in e.g. discrete probability distributions (used by particle filters)

![unknown_filename.1.png](./_resources/Pros_and_cons_of_Gaussian_distributions.resources/unknown_filename.1.png)
With enough bins, an arbitrary error characteristic \[of a sensor\] can be modelled.

