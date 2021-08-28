---
title: Smug filter
date: "2020-08-31"
tags:
  - -definitions
  - -sa/processed
  - filters
---

Parent: [1D Kalman filter algorithm](1d-kalman-filter-algorithm.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

A filter that, once enough measurements are made, becomes very confident in its prediction (P gets smaller with time while the filter becomes more inaccurate!).
From then on it will ignore measurements

To avoid this: add a bit of error to the prediction step, e.g. using the [process variance](http://www.evernote.com/shard/s484/nl/217355218/dd75d924-7153-4b9f-81a1-ec6237d4ec25)

