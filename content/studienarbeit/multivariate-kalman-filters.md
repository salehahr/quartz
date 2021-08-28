---
title: Multivariate Kalman filters
date: "2020-09-01"
tags:
  - filters/kalman-filter
  - -sa/to-be-processed
---

Parent: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

[Hidden variables in a multivariate Kalman filter](hidden variables-in-a-multivariate-kalman-filter.md)

Here:

*   Focus is on a subset of problems describable using Newton's equations of motion
*   Discretised continuous-time kinematic filters

[Multivariate Kalman filter algorithm](multivariate-kalman-filter-algorithm.md)

Designing the filter

*   State (x, P)
*   Process (F, Q)
*   Measurement (z, R)
*   Measurement function H
*   Control inputs (B, u)

Assumptions of the Kalman filter

*   The sensors and motion model have Gaussian noise
*   Everything is linear

If the assumptions are true, then the Kalman filter is optimal in a least squares sense

