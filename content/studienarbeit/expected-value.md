---
title: Expected value
date: "2020-08-27"
tags:
  - to-do/to-clarify
  - -sa/processed
  - math/statistics
---

Source: [rlabbe Kalman/Bayesian filters in Python](rlabbe-kalman_bayesian-filters-in-python.md)

Example: if we take a thousand sensor readings, the readings won't always be the same (due to the inherent noise).

*   The expected value 'averages' all of the readings into a single value.
*   This can be a mean (probabilities of all values assumed equal)
*   Or if incorporating individual and different probabilities, the expectation isn't the mean of the range of values

![unknown_filename.png](./_resources/Expected_value.resources/unknown_filename.png)
![unknown_filename.1.png](./_resources/Expected_value.resources/unknown_filename.1.png)

Proven: the average of a large number of measurements will be very close to the actual weight
- [ ] What is the name for this theorem?

Caveat:

*   Using a normal mean calculation assumes that all measurements are equally likely.
*   However, real sensors tend to return readings close to the actual value (barring any offset disturbances).
*   They can still return readings further away from the actual value, just with a reduced probability compared to values nearer the actual value
*   The probability \[distribution\] must be factored in somehow

