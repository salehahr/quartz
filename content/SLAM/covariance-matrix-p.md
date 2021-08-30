---
title: Covariance matrix P
date: "2020-07-29"
tags:
  - filters/EKF
  - -sa/processed
  - -published
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

s. also [EKF matrices](studienarbeit/ekf-matrices-vectors.md)

Covariance matrix P

*   Covariance: measure of correlation of two variables
*   Correlation: measure of degree of linear dependence

![unknown_filename.png](studienarbeit/_resources/Covariance_matrix_P.resources/unknown_filename.png)

|     |     |     |
| --- | --- | --- |
| A   | covariance of the robote POSE<br>updated in [Step 1: Odometry update](SLAM/step-1-odometry-update-prediction-step.md)| 3x3 |
| B .. C | covariance on the first .. nth landmark<br>[Step 3: New landmarks](studienarbeit/step-3-new-landmarks.md) | 2x2 |
| D   | covariance between POSE and first LM<br>updated in [Step 1: Odometry update](SLAM/step-1-odometry-update-prediction-step.md) | 2x3 |
| E, etc | E = D^T, etc<br>updated in [Step 1: Odometry update](SLAM/step-1-odometry-update-prediction-step.md) | 3x2 |
| F=G^T | [Step 3: New landmarks](studienarbeit/step-3-new-landmarks.md) |     |

Initially $P = A$ (robot has not seen any LMs)

Include initial uncertainty

*   There will often be a singular error if the initial uncertainty is not included
*   good idea to include some initial error even though there is reason to believe that the initial robot position is exact
*   initialise default values for the diagonal

Top three rows: cross correlation between POSE and landmarks
updated in [step 1 (odometry update)](SLAM/step-1-odometry-update-prediction-step.md)
