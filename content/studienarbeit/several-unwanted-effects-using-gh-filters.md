---
title: Several unwanted effects using gh filters
date: "2020-08-27"
tags:
  - -sa/processed
  - filters/gh-filter
---

Parent: [g-h filter or α-β filter](g-h-filter-or-α-β-filter.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Effect of bad initial conditions: ringing (sinusoidal over- and undershooting before finally settling onto a trajectory)
![unknown_filename.png](./_resources/Several_unwanted_effects_using_gh_filters.resources/unknown_filename.png)

Effect of very noisy data
![unknown_filename.1.png](./_resources/Several_unwanted_effects_using_gh_filters.resources/unknown_filename.1.png)

Effect of acceleration (in data)
![unknown_filename.2.png](./_resources/Several_unwanted_effects_using_gh_filters.resources/unknown_filename.2.png)
Filter lags behind because it uses a model that assumes constant velocity in each propagation step.
Hence, a filter is only as good as the mathematical model used to describe the phenomenon.

