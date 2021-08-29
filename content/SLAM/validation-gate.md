---
title: Validation gate
date: "2020-08-06"
tags:
  - localisation/data-association
  - -sa/processed
  - -published
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

An observed landmark is associated to a landmark if the following holds

$$
\begin{aligned}
v_i^T S_i^{-1} v_i \leq \lambda
\end{aligned}
$$

|     |     |
| --- | --- |
| v   | innovation |
| S   | innovation covariance |

The validation gate makes use of the fact that the [EKF](SLAM/extended-kalman-filter.md) implementation gives a bound on the uncertainty of an observation of a [landmark](SLAM/landmarks.md).

*   Is an observed LM a LM in the database?
*   Check if the observed LM lies within the area of uncertainty
*   Can usually be shown in a graphic (error ellipse)

