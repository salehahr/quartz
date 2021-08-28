---
title: Factors affecting Kalman filter performance
date: "2020-08-31"
tags:
  - -sa/processed
  - filters/kalman-filter
---

Parent: [1D Kalman filters](1d-kalman-filters.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Difficulties of creating a well-performing Kalman filter:
Includes modeling the sensor performance (what variance most accurately represents the reality? Which probability distribution?)

Factors affecting the performance of the Kalman filter

*   [On modelling the process noise/variance](on-modelling-the-process-noise_variance.md)
*   Bad initial estimate
    *   Filter can recover from this, because we have a certain belief in the sensor measurements
    *   Typically the initial value is set to the first sensor measurement
*   [Nonlinearity of the system](nonlinearity-of-the-system.md)

