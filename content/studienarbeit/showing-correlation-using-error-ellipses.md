---
title: Showing correlation using error ellipses
date: "2020-09-01"
tags:
  - to-do/to-clarify
  - -sa/processed
  - math/statistics
---

Parent: [Error ellipse/Confidence ellipse](error-ellipse_confidence-ellipse.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

A slanted ellipse implies correlation
- [ ] The 'thinner' side isn't necessarily more accurate, it just means that the spread of data is reduced along this dimension (when viewing sensor data, for example) 

Example
First epoch
![unknown_filename.1.png](./_resources/Showing_correlation_using_error_ellipses.resources/unknown_filename.1.png)
**Yellow**: prior (very uncertain about position)
**Green**: evidence (more accurate in one of the dimensions than the other; more certainty compared to prior)
**Blue**: posterior via [multiplication](multiplication.md)

Posterior retains the shape of the evidence (which has more certainty than the prior)

Second epoch
![unknown_filename.png](./_resources/Showing_correlation_using_error_ellipses.resources/unknown_filename.png)

*   Old posterior now becomes the next prior (in yellow)
*   A new measurement (in green) is made
*   The resulting covariance shape reflects the physical layout of the system (geometry of the problem)
*   Enables triangulation of the system (via use of two sensors at two different locations) -- optimal triangulation when sensors are orthogonal to each other, as in the example

