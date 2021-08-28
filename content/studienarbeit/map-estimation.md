---
title: MAP estimation
date: "2020-11-27"
tags:
  - sensors/IMU/preintegration
  - -sa/to-be-processed
---

Source: [Forster 2017 IMU Preintegration](forster-2017-imu-preintegration.md)

Factor graph: way of representing the posterior probability of the states ![unknown_filename.2.png](./_resources/MAP_estimation.resources/unknown_filename.2.png) given the available measurements ![unknown_filename.png](./_resources/MAP_estimation.resources/unknown_filename.png) and priors ![unknown_filename.1.png](./_resources/MAP_estimation.resources/unknown_filename.1.png)
![Image.png](./_resources/MAP_estimation.resources/Image.png)

![unknown_filename.3.png](./_resources/MAP_estimation.resources/unknown_filename.3.png)

The terms in the equation above are called 'factors'

*   MAP: maximum a posteriori
*   We want to maximise the probability derived above --> MAP estimate
*   (aka minimum of negative log posterior)
*   The negative log posterior can be written as a sum of squared residuals, **assuming** zero-mean Gaussian noise

![unknown_filename.4.png](./_resources/MAP_estimation.resources/unknown_filename.4.png)

|     |     |
| --- | --- |
| ![unknown_filename.5.png](./_resources/MAP_estimation.resources/unknown_filename.5.png) | residual errors (prior, IMU, camera) |
| ![unknown_filename.6.png](./_resources/MAP_estimation.resources/unknown_filename.6.png) | covariance matrices |

How do we define these residuals?

