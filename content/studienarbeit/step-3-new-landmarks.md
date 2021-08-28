---
title: Step 3 New landmarks
date: "2020-07-29"
tags: 
- filters/EKF 
- localisation/landmarks 
- -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks: [Basic EKF for SLAM](basic-ekf-for-slam.md)

Overview

*   Landmarks that are new are not dealt with until step 3.
    *   Delaying the incorporation of new landmarks until the will decrease the computation cost needed for this step
    *   the covariance matrix, P, and the system state, X, are smaller by then.
*   Update state vector x and covariance matrix P with new landmarks

1.  Add new landmark to state vector X
2.  Add new row and column to [covariance matrix](http://www.evernote.com/shard/s484/nl/217355218/7bd4a70a-7c4d-4fa7-91ce-7de461360bc2)
    1.  Covariance for new landmark
    2.  Robot-landmark covariance

