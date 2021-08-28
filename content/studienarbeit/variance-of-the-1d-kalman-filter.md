---
title: Variance of the 1D Kalman filter
date: "2020-08-31"
tags:
  - -sa/processed
  - filters/kalman-filter
---

Parent: [1D Kalman filters](1d-kalman-filters.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

i.e., what variance is show by the estimated output/posterior?)

*   Always converges to a fixed value if the sensor and process variances are constant
*   We can run simulations to determine the value to which the filter variance converges
*   Then hard code this value into the filter (+ with first sensor measurement as initial value, the filter should have good performance)
*   Alternative: instead of using the variance value, use the calculated Kalman gain

Example implementation using the Kalman gain
However, using the Kalman gain obscures the Bayesian approach
![unknown_filename.png](./_resources/Variance_of_the_1D_Kalman_filter.resources/unknown_filename.png)

