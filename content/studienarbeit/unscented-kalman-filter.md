---
title: Unscented Kalman Filter
date: "2020-08-23"
tags:
  - -sa/processed
  - filters/kalman-filter
---

**Parent**: [General Kalman Filter](general-kalman-filter.md)

Source: [Scaradozzi 2018 SLAM application in surgery](studienarbeit/scaradozzi-2018.md)

*   developed to overcome main problems of the [EKF](http://www.evernote.com/shard/s484/nl/217355218/a3417515-123a-4310-ac2f-937cd4878942)
*   like EKF, approximates the state distribution with a Gaussian Random Variable
    *   only the representation is different—using alpha points (a minimal set of sample points)
    *   capture posterior mean and covariance accurately for any nonlinearity, up to3rd order Taylor

