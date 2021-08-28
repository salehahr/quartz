---
title: Hidden variables in a multivariate Kalman filter
date: "2020-09-01"
tags:
  - filters/kalman-filter
  - -sa/to-be-processed
---

Parent: [Multivariate Kalman filters](multivariate-kalman-filters.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Example:
![unknown_filename.1.png](./_resources/Hidden_variables_in_a_multivariate_Kalman_filter.resources/unknown_filename.1.png)
Blue error ellipse:

*   Certainty in position x=0
*   No idea about the velocity (long in y-axis)

We know that position and velocity are correlated,
i.e. the next position depends on the current velocity value
(red error ellipse — likelihood/prediction for the next step)
e.g. if v=5m/s, the next position is 5m +- position uncertainties

We get a position update (new blue error ellipse)
![unknown_filename.png](./_resources/Hidden_variables_in_a_multivariate_Kalman_filter.resources/unknown_filename.png)

*   The new covariance (posterior) is obtained by multiplying the previous two covariances —> intersection
*   The posterior's tilt implies that there is some correlation between position and velocity
*   Not only are we now more certain about the velocity, but our position certainty also increases (compared to not considering the velocity at all)!

Observed variable: can be obtained from sensor
Hidden variable: inferrable from observedvariables
Unobserved variables: not sensable and also not inferrable from sensor measurements

**Takeaway**: Hidden variables can significantly increase the accuracy of the filter (due to their correlation with the observed variables)

**Caveat**: When inferring a state from an observed variable, do not always assume that the derived state is accurate. Possible error sources here:

*   We assume a correlation between the hidden variable and the observed variable, but in fact there is none
*   The hidden variable might be oscillating at a certain frequency F, but we sample the observed variable at a frequency less than 2F (s. Nyquist-Shannon theory) and get a bad representation of the velocity signal
*   Bad initialisation. An observed state may recover from bad IC, but a hidden state may not.

Validation necessary!

