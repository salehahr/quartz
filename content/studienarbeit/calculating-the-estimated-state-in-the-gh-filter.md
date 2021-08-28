---
title: Calculating the estimated state in the GH-filter
date: "2020-08-27"
external_url: "http://nbviewer.jupyter.org/github/feudalism/Kalman-and-Bayesian-Filters-in-Python/blob/master/01-g-h-filter.ipynb"
tags:
  - -sa/processed
  - filters/gh-filter
---

Parent: [g-h filter or α-β filter](g-h-filter-or-α-β-filter.md)
Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

![unknown_filename.png](./_resources/Calculating_the_estimated_state_in_the_GH-filter.resources/unknown_filename.png)
Using [a gain](http://www.evernote.com/shard/s484/nl/217355218/a7509361-eda5-4c69-a509-eb5c9d213ab2), the estimate therefore always falls between the measurements (circles) and the predictions (in red).
The prediction is dependent on the previous filter output (i.e. last estimate). Here it is modelled to increase by 1 from the previous estimate.

The estimates are not a straight line, but definitely closer in shape to the ground truth than the measurements alone.
Moreover, they seem to improve with time.

[Effects of varying g](effects-of-varying-g.md)

Caveat: This worked well because we had a good prediction model (gain +1 lb/day), which is close to the ground truth behaviour (also +1 lb/day).
If we had derived the prediction model with a bad gain, e.g. -1 lb/day, the esimates won't be that good anymore (but nevertheless an improvement over the prediction alone).

![unknown_filename.1.png](./_resources/Calculating_the_estimated_state_in_the_GH-filter.resources/unknown_filename.1.png)

Improvement: [Improving the gh-filter by using h](improving-the-gh-filter-by-using-h.md)

