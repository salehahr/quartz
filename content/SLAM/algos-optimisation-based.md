---
title: Some optimisation-based tightly-coupled multisensor SLAM algorithms
date: "2020-07-30"
tags:
  - SLAM/filter-vs-optim/opt-based
  - -sa/processed
  - SLAM/algos
  - -published
---

**Source**: [Wu 2018](bibliography/wu-2018.md)

* Uses nonlinear optimization
* may potentially achieve higher accuracy due to the capability to limit linearization errors through repeated linearization of the inherently nonlinear problem

<pre></pre>
*   \[117\] [Forster 2017](studienarbeit/forster-2017-imu-preintegration.md): preintegration theory
*   \[118\] OKVIS: a novel approach
    *   to tightly integrate visual measurements with IMU
    *   optimise a joint nonlinear cost function that integrates an IMU error term with the landmark reprojection error in a fully probabilistic manner
    *   real-time operation: old states are marginalized to maintain a bounded-sized optimization window
*   Li et al. \[119\] proposed tightly coupled, optimization based, monocular visual-inertial state estimation for camera localization in complex environments. This method can run on mobile devices with a lightweight [loop closure](SLAM/loop-closure-detection.md).
*   [VIORB](bibliography/mur-artal-2017-vi-orb.md) a tightly coupled visual-inertial slam system was proposed, following ORBSLAM monocular SLAM

