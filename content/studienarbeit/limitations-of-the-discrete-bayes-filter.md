---
title: Limitations of the discrete Bayes filter
date: "2020-08-31"
tags:
  - -sa/processed
  - filters/bayesian-filter
---

Parent: [Discrete Bayesian filter](discrete-bayesian-filter.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Limitations of the discrete Bayes filter

*   Scaling
    *   Dog tracking example is one-dimensional, but in real life we often want to track more things (e.g. 2D coordinates, velocities)
    *   Multidimensional case: store probabilities in a grid
    *   4 tracked variables: O(n^4) per time step
    *   High computational cost with high dimensionality
*   Filter is discrete and therefore gives discrete output
    *   But a lot of applications require continuous output
    *   Discretising a solution space can lead to lots of data (depending on accuracy required) --> calculations for lots of different probabilities!
*   Filter is multimodal
    *   Not always a problem, e.g. particle filters are multimodal
    *   But not always a good things either, sometimes not a realistic representation of the reality (e.g. 40% in this location, 30% in the other location)
*   Requires measurement of the change in state (dog tracking example assumes movement by 1 unit)

We want a unimodal, continuous filter --> achieve this by using [Gaussian distributions](http://www.evernote.com/shard/s484/nl/217355218/12fcf819-bea6-4160-9bf0-fd22e8f59cb1).

