---
title: Effects of varying h
date: "2020-08-27"
tags:
  - -sa/processed
  - filters/gh-filter
---

Parent [Improving the gh-filter by using h](improving-the-gh-filter-by-using-h.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

![unknown_filename.png](./_resources/Effects_of_varying_h.resources/unknown_filename.png)

The greater the h value, the more we trust the rate of change that we can derive from the measurement data.

*   a larger h enables us to react to transient (initial condition dependent) changes more rapidly.
    Because if we have a large difference between our chosen IC and the measurement, this results in a huge residual velocity
    
*   the h term responds to changes in velocity that may not be present in the mathematical model we choose (change in velocity is then 'seen' in the sensor data)

