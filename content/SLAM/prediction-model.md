---
title: Prediction model
date: "2020-07-29"
tags:
  - filters/EKF
  - -sa/processed
  - -published
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)  

Used in the [prediction step](SLAM/step-1-odometry-update-prediction-step.md).

How to compute an expected position of the robot given the old position and the control input (so basically based on [odometry](definitions/odometry.md).

Control terms are $\Delta x, \Delta y, \Delta \theta$)

$$
f = \left[ 
\begin{array}{c}
x + \Delta t \cos \theta + q \Delta t \cos \theta \\
y + \Delta t \sin \theta + q \Delta t \sin \theta \\
\theta + \Delta \theta + q \Delta\theta
\end{array}
\right]
$$

[unknown_filename.1.png](studienarbeit/_resources/Prediction_model.resources/unknown_filename.1.png)  

$\Delta t$: change in thrust  
$q$: error term

Jacobian (assuming linearised version)

$$
\left[ 
\begin{array}{ccc}
1 & 0 & -\Delta t \sin\theta\\
0 & 1 & \Delta\cos\theta\\
0 & 0 & 1
\end{array}
\right]
$$

Not extended for landmarks because only used for robot position prediction

