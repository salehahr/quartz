---
title: Step 1 Odometry update (Prediction step)
date: "2020-07-29"
tags: 
- filters/EKF 
- -sa/processed
- -published
---

**Parent**: [Basic EKF for SLAM](SLAM/basic-ekf-for-slam.md)

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

First step in the three-step [EKF](SLAM/basic-ekf-for-slam.md)

*   Update current state using odometry data
*   Based on the controls given to the robot
*   Calculate estimate of new POSE

Update equation:  [prediction model](SLAM/prediction-model.md) ($x = x + \Delta x \cdot q$)  
Or in a simple model, neglect the error term $q$

1.  State vector gets updated via the prediction model
2.  Jacobian of the prediction model also needs to be updated every iteration (with the controls deltax, ...)
3.  [Process noise Q](SLAM/50.2.1-process-noise-q-and-w-odometry.md) updated to reflect control terms
    ![unknown_filename.png](studienarbeit/_resources/Step_1__Odometry_update_(Prediction_step).resources/unknown_filename.png)
    
4.  Calculate new covariance for robot POSE (onlt the top left of the [P matrix](SLAM/covariance-matrix-p.md) using the Jacobian of pred. model A and process noise Q
    ![unknown_filename.1.png](studienarbeit/_resources/Step_1__Odometry_update_(Prediction_step).resources/unknown_filename.1.png)
    
5.  New cross correlations in [P matrix](SLAM/covariance-matrix-p.md) (top three rows)
    ![unknown_filename.2.png](studienarbeit/_resources/Step_1__Odometry_update_(Prediction_step).resources/unknown_filename.2.png)
    
6.  Transpose the cross correlations to the leftmost three columns

Due to odometry errors, this estimate is not exact.

