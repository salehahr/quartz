---
title: Step 2 Re-observation
date: "2020-07-29"
tags: 
- filters/EKF 
- -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks: [Basic EKF for SLAM](basic-ekf-for-slam.md)

Second step in the three-step EKF — overview

*   In this step we update the robot position that we got in [step 1](http://www.evernote.com/shard/s484/nl/217355218/fe366015-f610-46f9-a801-eb6deb8a839d)
    *   Compensate for errors due to odometry
        pos\_est (odometry-based) - pos\_actual (LM-based) = Innovation, (based on the LM that the robot can see)
        
    *   Use this to update robot position
*   Update the uncertainty of each observed LM to reflect recent changes e.g.
    *   very low uncertainty of a LM.
    *   Re-observing the LM from the same position with low uncertainty will increase the LM certainty (s. [loop closure](http://www.evernote.com/shard/s484/nl/217355218/75ada851-3e4e-88e0-9788-ee8cc5e2f104))
    *   (variance of LM w.r.t. current robot position)
*   This step is run for each re-observed landmark

1.  Calculate range and bearing to the landmark (range and bearing in current measurements) using the [measurement model](http://www.evernote.com/shard/s484/nl/217355218/54e21e37-2184-46fe-b494-01ef63b3b2eb).
    This can be compared to the range and bearing obtained from data association (denoted as z)
    
2.  Calculate the [Jacobian H](jacobian-h.md) of the measurement model
3.  Update the [error matrix R](http://www.evernote.com/shard/s484/nl/217355218/fc4f284b-8751-4c90-9253-94898f905f97) to reflect range and bearing in current measurements
4.  Compute Kalman gain
    1.  ![unknown_filename.png](./_resources/Step_2__Re-observation.resources/unknown_filename.png)
    2.  term in bracket is S (innovation covariance)
5.  Compute new [state vector](http://www.evernote.com/shard/s484/nl/217355218/9090a6f9-c3ba-4927-be3a-496e4aa93d4c) (range and bearing) using Kalman gain
    1.  ![unknown_filename.1.png](./_resources/Step_2__Re-observation.resources/unknown_filename.1.png)
    2.  this updates robot pose along with landmark positions
    3.  z - h = v (displacement in range and bearing)

