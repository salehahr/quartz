---
title: Improving the gh-filter by using h
date: "2020-08-27"
tags:
  - -sa/processed
  - filters/gh-filter
---

Parent: [g-h filter or α-β filter](g-h-filter-or-α-β-filter.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

[Implementing the g value without h](implementing-the-g-value-without-h.md)

We improve the estimation, previously by only predicting the state, by now predicting the rate of change of state.
i.e. Also predict the weight gain per day instead of setting it at a constant value.
We use the sensor information for this! Even if it's noisy, there's information in there somewhere, and data is always better than a guess.
e.g.![unknown_filename.png](./_resources/Improving_the_gh-filter_by_using_h.resources/unknown_filename.png) 
where 1/3 is an arbitrary, tunable value.

With this approach, not only do we predict a state, but we additionally predict its rate of change
 gain\_rate = gain\_rate + gain\_scale \* (residual/time\_step)

![unknown_filename.1.png](./_resources/Improving_the_gh-filter_by_using_h.resources/unknown_filename.1.png)
Due to bad prediction model (-1 lb/day), we have some bad early estimates and it takes the filter some time to achieve accuracy, but once it does, it remains accurate.

[Effects of varying h](effects-of-varying-h.md)

