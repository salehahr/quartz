---
title: note KF with missing measurements
date: "2021-03-26"
external_url: "http://math.stackexchange.com/questions/982982/kalman-filter-with-missing-measurement-inputs"
tags: 
- to-do/orphan 
- filters/kalman-filter 
- discussion/2021/2021-04 
- -sa/to-be-processed
---

**Sources**
<http://math.stackexchange.com/questions/982982/kalman-filter-with-missing-measurement-inputs>
<http://opencv-users.1802565.n2.nabble.com/Kalman-filters-and-missing-measurements-td2886593.html>

For a missing measurement:

*   use the last state estimate as a measurement
*   set the covariance matrix of the measurement to essentially infinity.

This would cause a Kalman filter to essentially ignore the new measurement since the ratio of the variance of the prediction to the measurement is zero.
The result will be a new prediction that maintains velocity/acceleration but whose variance will grow according to the process noise.

