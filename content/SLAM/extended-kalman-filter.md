---
title: Extended Kalman Filter
date: "2020-07-27"
tags:
  - filters/EKF
  - -sa/processed
---

Parent: [SLAM Index](SLAM/slam_index.md)
Backlinks: [RANSAC](SLAM/ransac.md),  [nearest neighbour](SLAM/nearest-neighbour.md), [Filtering in localisation](SLAM/filter-localisation-methods.md)

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

*   keeps track of an estimate of the position uncertainty
*   keeps track of the uncertainty in the features/landmarks seen

[General EKF implementation (non-SLAM)](studienarbeit/general-ekf-implementation-non-slam.md)  
[Basic EKF for SLAM](SLAM/basic-ekf-for-slam.md)

Diagram:
![unknown_filename.png](studienarbeit/_resources/Extended_Kalman_Filter.resources/unknown_filename.png)

| Triangle | Robot |
| --- | --- |
| Stars | Landmarks |
| Dashed triangle | Robot's position based on odometry alone (where it thinks it is) |
| Dotted triangle | Robot's position estimate based on EKF |
| Solid line triangle | Robot's actual position in real life! |

[EKF matrices](studienarbeit/ekf-matrices-vectors.md)

