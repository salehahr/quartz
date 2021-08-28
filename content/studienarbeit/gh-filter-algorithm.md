---
title: GH filter algorithm
date: "2020-08-27"
tags:
  - -sa/processed
  - filters/gh-filter
---

Parent: [g-h filter or α-β filter](g-h-filter-or-α-β-filter.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Initialisation

1.  Initialise the state of the filter
2.  Initialise our belief in the state

Prediction

1.  Use system model to propagate the state to the next time step
2.  Adjust our belief to account for uncertainty in the prediction

Update

1.  Get a measurement and an associated belief about its accuracy
2.  Calculate residual = measurement - estimated state
3.  Using [a certain gain](http://www.evernote.com/shard/s484/nl/217355218/a7509361-eda5-4c69-a509-eb5c9d213ab2), our updated state estimate is somewhere on the residual line

