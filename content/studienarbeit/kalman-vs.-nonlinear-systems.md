---
title: Kalman vs. nonlinear systems
date: "2020-08-31"
tags:
  - -sa/processed
  - filters/kalman-filter
---

Parent: [Factors affecting Kalman filter performance](factors-affecting-kalman-filter-performance.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Kalman filter equations are linear
![unknown_filename.png](./_resources/Kalman_vs._nonlinear_systems.resources/unknown_filename.png)

Example: approximating a sine-wave signal
![unknown_filename.1.png](./_resources/Kalman_vs._nonlinear_systems.resources/unknown_filename.1.png)

Explanation:

*   Back to the basic g-h filter structure: the filter output chooses a value on the residual line
*   The process model in the underlying filter assumes constant velocity (0 acceleration), whereas in the sine example above, the signal is always accelerating

