---
title: Visual SLAM Implementation Framework
date: "2020-07-30"
tags:
  - SLAM/VSLAM
  - discussion/2020/2020-08
  - -sa/processed
  - -published
---

**Source**: [Cometlabs](bibliography/cometlabs.md)

## Basic principle:

*   tracking a set of points through successive frames
*   these tracks are used to triangulate the 3D positions of the points to create the map
*   at the same time, using the the est point locations to calculate the pose of the camera, which could have observed them (i.e. calculate real time 3D structure of a scene from the estimated motion of the camera)

![vslam-triangulation](_img/vslam-triangulation.png)

## Architecture

1.  Front-end
    *   Abstracts sensor data into models (which are good for estimation) / Processing
    *   [Data association](SLAM/data-association.md)
        *   Short term (feature tracking); features in consecutive sensor measurements
            *   Either from [sparse maps](studienarbeit/sparse-feature-based-vslam.md) or [dense-maps](studienarbeit/dense-direct-vslam.md)
        *   Long term ([loop closure](SLAM/loop-closure-detection.md); associating new measurements to older landmarks
2.  [Back-end](studienarbeit/back-end-optimisation.md)
    *   Performs inference on the abstracted data produced by the front end

![vslam-architecture](_img/vslam-architecture.png)

