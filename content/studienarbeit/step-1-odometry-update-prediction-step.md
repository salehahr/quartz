---
title: Step 1 Odometry update (Prediction step)
date: "2020-07-29"
tags: 
- filters/EKF 
- -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks: [Basic EKF for SLAM](basic-ekf-for-slam.md)

First step in the three-step EKF

*   Update current state using odometry data
*   Based on the controls given to the robot
*   Calculate estimate of new POSE

Update equation: [prediction model](http://www.evernote.com/shard/s484/nl/217355218/b3a77631-29df-4c28-97f3-a7ac49e87e90) (x = x + deltax)
Or in a simple model, neglect the error term q

1.  State vector gets updated via the prediction model
2.  Jacobian of the prediction model also needs to be updated every iteration (with the controls deltax, ...)
3.  [Process noise Q](http://www.evernote.com/shard/s484/nl/217355218/dd75d924-7153-4b9f-81a1-ec6237d4ec25) updated to reflect control terms
    ![unknown_filename.png](./_resources/Step_1__Odometry_update_(Prediction_step).resources/unknown_filename.png)
    
4.  Calculate new covariance for robot POSE (onlt the top left of the [P matrix](http://www.evernote.com/shard/s484/nl/217355218/7bd4a70a-7c4d-4fa7-91ce-7de461360bc2)) using the Jacobian of pred. model A and process noise Q
    ![unknown_filename.1.png](./_resources/Step_1__Odometry_update_(Prediction_step).resources/unknown_filename.1.png)
    
5.  New cross correlations in [P matrix](p-matrix.md) (top three rows)
    ![unknown_filename.2.png](./_resources/Step_1__Odometry_update_(Prediction_step).resources/unknown_filename.2.png)
    
6.  Transpose the cross correlations to the leftmost three columns

Due to odometry errors, this estimate is not exact.

