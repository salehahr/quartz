---
title: Gain g of the gh-filter
date: "2020-08-27"
tags:
  - -sa/processed
  - filters/gh-filter
---

Parent: [Calculating the estimated state based on measurements and predictions](calculating the estimated state-based-on-measurements-and-predictions.md)
Backlinks: [GH filter algorithm](gh-filter-algorithm.md)

Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Which one do we trust more, the meaasurement z or the prediction x?
Applying corresponding weights to both, we obtain the estimate x\_est

![unknown_filename.png](./_resources/Gain_g_of_the_gh-filter.resources/unknown_filename.png)

The prediction is nothing other than a propagated state estimate.

\[Me\] The prediction is basesd on the model (a priori knowledge)
If the model also depends on previous states (which are themselves an output of the filter, i.e. the state estimates), then the prediction is dependent on filter output too (up till the last time step).

\# Prediction step
prediction = system\_model(previous\_state\_estiamte)

\# Update step
residual = measurement z - prediction x
estimate = prediction + g \* residual

Here we have applied a scale to the measurement, but we can also do this to the rate of change of measurement.
gain\_rate = gain\_rate + h \* (residual/time\_step)

