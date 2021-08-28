---
title: Back-end optimisation
date: "2020-08-03"
tags:
  - to-do/to-clarify
  - SLAM/VSLAM
  - -sa/processed
---

Parent: [Visual SLAM Implementation Framework](visual-slam-implementation-framework.md)

Source: [cometlabs](cometlabs.md)

(Camera pose optimisation)

*   To compensate for drift of pose estimation
*   Traditionally using EKF ([filter-based](http://www.evernote.com/shard/s484/nl/217355218/48ab2536-eadf-4a7f-8dfa-f377bfbe3839))
    *   simple implementation
    *   therefore good for small scale estimations
*   Alternative: bundle adjustment (graph optimisation)
    *   joint optimisation of the camera pose and the 3D structure parameters
    *   combines numerical methods and graph theory
    *   increasingly favoured over filtering, due to the latter's inherent inconsistency
    *   more efficient when combined with sub-mapping

