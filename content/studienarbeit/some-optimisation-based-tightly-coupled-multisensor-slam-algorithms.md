---
title: Some optimisation-based tightly-coupled multisensor SLAM algorithms
date: "2020-07-30"
tags:
  - SLAM/filter-vs-optim/opt-based
  - -sa/processed
  - SLAM/algos
---

Parent: [SLAM Index](slam-index.md)

Source: [Wu 2018 Image-based camera localization: an overview](wu 2018-image-based-camera-localization_-an-overview.md)

Uses nonlinear optimization
may potentially achieve higher accuracy due to the capability to limit linearization errors through repeated linearization of the inherently nonlinear problem

*   \[117\] Forster: preintegration theory
*   \[118\] OKVIS: a novel approach
    *   to tightly integrate visual measurements with IMU
    *   optimise a joint nonlinear cost function that integrates an IMU error term with the landmark reprojection error in a fully probabilistic manner
    *   real-time operation: old states are marginalized to maintain a bounded-sized optimization window
*   Li et al. \[119\] proposed tightly coupled, optimization based, monocular visual-inertial state estimation for camera localization in complex environments. This method can run on mobile devices with a lightweight [loop closure](http://www.evernote.com/shard/s484/nl/217355218/75ada851-3e4e-88e0-9788-ee8cc5e2f104?title=Loop%20closure%20detection).
*   [VIORB](http://www.evernote.com/shard/s484/nl/217355218/014a8f28-8f7b-4178-aea8-c65f9ae1dd73) a tightly coupled visual-inertial slam system was proposed, following ORBSLAM monocular SLAM
