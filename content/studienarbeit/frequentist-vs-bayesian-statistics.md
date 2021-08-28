---
title: Frequentist vs Bayesian statistics
date: "2020-08-31"
tags:
  - -definitions
  - -sa/processed
  - math/statistics
---

Parent: [Discrete Bayesian filter](discrete-bayesian-filter.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Frequentist vs Bayesian statistics

*   Probability of flipping a fair coin infinitely many times is 50% - frequentist
*   Probability of flipping a fair coin one more time (which way do I believe it landed?), single event - Bayesian
    *   Bayesian statistics takes past information (prior) into account
    *   If finding the prior is tricky, frequentist techniques are sometimes used

e.g. Weather

*   Frequentist: If it rains 4 out of 100 days, the chance of rain today is 25%
*   Bayesian: If we know that it's raining today and the storm front is stalled (prior information), it is likely to rain tomorrow

