---
title: g-h filter or α-β filter
date: "2020-08-27"
tags:
  - -sa/processed
  - filters/gh-filter
---

Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

A filter that uses two scaling factors:

*   [g or \\alpha](http://www.evernote.com/shard/s484/nl/217355218/a7509361-eda5-4c69-a509-eb5c9d213ab2) for the measurement
*   h or \\beta for the rate of change of measurement

[GH filter algorithm](gh-filter-algorithm.md)

[Calculating the estimated state in the GH-filter](calculating the-estimated-state-in-the-gh-filter.md)
[Improving the gh-filter by using h](improving-the-gh-filter-by-using-h.md)

[Several unwanted effects using gh filters](several-unwanted-effects-using-gh-filters.md)

Basis for many other filters, e.g.

*   Kalman filter
*   Least squares filter
*   Benedict-Bordner filter
*   etc.

where each different filter has a different way of determining g and h (whether constant values or varying them dynamically with time)

Static choices for g and h do not perform very well — tied to only one particular dataset.

