---
title: Step 3 New landmarks
date: "2020-07-29"
tags: 
- filters/EKF 
- localisation/landmarks 
- -sa/processed
---

**Parent**: [Basic EKF for SLAM](SLAM/basic-ekf-for-slam.md)

**Source**: [SLAM for dummies](bibliography/riisgaard-slam-for-dummies.md)  

Overview

*   Landmarks that are new are not dealt with until step 3.
    *   Delaying the incorporation of new landmarks until the will decrease the computation cost needed for this step
    *   the covariance matrix, P, and the system state, X, are smaller by then.
*   Update state vector x and covariance matrix P with new landmarks

1.  Add new landmark to state vector X
2.  Add new row and column to [covariance matrix](SLAM/covariance-matrix-p.md)
    1.  Covariance for new landmark
    2.  Robot-landmark covariance

