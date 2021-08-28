---
title: Extended Kalman Filter
date: "2020-07-27"
tags:
  - filters/EKF
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)
Backlinks: [RANSAC](ransac.md),  [nearest neighbour](nearest neighbour.md), [filter-localisation-methods](filter-localisation-methods.md)

Source: [SLAM for Dummies](slam-for-dummies.md)

*   keeps track of an estimate of the position uncertainty
*   keeps track of the uncertainty in the features/landmarks seen

[General EKF implementation (non-SLAM)](general-ekf-implementation-(non-slam).md)
[Basic EKF for SLAM](basic-ekf-for-slam.md)

Diagram:
![unknown_filename.png](./_resources/Extended_Kalman_Filter.resources/unknown_filename.png)

|     |     |
| --- | --- |
| Triangle | Robot |
| Stars | Landmarks |
| Dashed triangle | Robot's position based on odometry alone (where it thinks it is) |
| Dotted triangle | Robot's position estimate based on EKF |
| Solid line triangle | Robot's actual position in real life! |

[EKF matrices](http://www.evernote.com/shard/s484/nl/217355218/c605b3ca-b822-40c9-9549-fc89088f96a7)

