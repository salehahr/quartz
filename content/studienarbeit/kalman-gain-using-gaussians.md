---
title: Kalman gain using Gaussians
date: "2020-08-31"
tags:
  - filters/kalman-filter
  - -sa/to-be-processed
---

Parent: [1D Kalman filters](1d-kalman-filters.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Kalman gain in the [update step](http://www.evernote.com/shard/s484/nl/217355218/830f0fa2-05fa-4c1a-a183-a6cbf0bdff4e)
![unknown_filename.1.png](./_resources/Kalman_gain_using_Gaussians.resources/unknown_filename.1.png)

*   Basically a scaling term that chooses a value between the sensor distr. mean and the posterior distr. mean
*   Gives greater weight to the term with lower variance (we trust this data more!)

Mean and variance in terms of the Kalman gain
![unknown_filename.png](./_resources/Kalman_gain_using_Gaussians.resources/unknown_filename.png)

Variance of the filter (i.e., what variance is show by the estimated output/posterior?)

*   Always converges to a fixed value if the sensor and process variances are constant
*   We can run simulations to determine the value to which the filter variance converges
*   Then hard code this value into the filter (+ with first sensor measurement as initial value, the filter should have good performance)
*   Alternative: instead of using the variance value, use the calculated Kalman gain

Example implementation using the Kalman gain
However, using the Kalman gain obscures the Bayesian approach
![unknown_filename.2.png](./_resources/Kalman_gain_using_Gaussians.resources/unknown_filename.2.png)

