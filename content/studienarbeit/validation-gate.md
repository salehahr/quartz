---
title: Validation gate
date: "2020-08-06"
tags:
  - localisation/data-association
  - -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks:  [Nearest Neighbour](nearest-neighbour.md)

An observed landmark is associated to a landmark if the following holds
![unknown_filename.png](./_resources/Validation_gate.resources/unknown_filename.png)

|     |     |
| --- | --- |
| v   | innovation |
| S   | innovation covariance |

The Validation gate makes use of the fact that the [EKF](ekf.md) implementation gives a bound on the uncertainty of an observation of a LM

*   Is an observed LM a LM in the database?
*   Check if the observed LM lies within the area of uncertainty
*   Can usually be shown in a graphic (error ellipse)

