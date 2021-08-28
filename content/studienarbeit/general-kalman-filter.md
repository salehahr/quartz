---
title: General Kalman Filter
date: "2020-08-23"
tags:
  - -sa/processed
  - filters/kalman-filter
---

Backlinks: [Main paradigms of SLAM](main-paradigms-of-slam.md)
Source: [Scaradozzi 2018 SLAM application in surgery](scaradozzi-2018-slam-application-in-surgery.md)

KF original algorithm assumes linearity (rarely ever the case)

*   Variations of the Kalman filter:
    *   [Extended Kalman Filter](http://www.evernote.com/shard/s484/nl/217355218/a3417515-123a-4310-ac2f-937cd4878942) (EKF)
    *   [Unscented Kalman Filter](http://www.evernote.com/shard/s484/nl/217355218/b19e0595-dbcb-4e34-8ea9-78069a850ca3) (UKF)
*   [Information filtering](http://www.evernote.com/shard/s484/nl/217355218/bf412e27-aa5a-41b0-986e-1ba17317747a) (IF) — dual to KF
*   Combination of EKF and IF: CF-SLAM, with the goal to be more efficient w.r.t. computational complexity

