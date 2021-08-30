---
title: SLAM Index
date: "2020-08-06"
tags:
  - SLAM
  - -master
  - -sa/processed
  - -published
aliases:
  - /slam/_index/
  - /slam/index/
has_content: True
---

## Definition
- [Localisation](studienarbeit/localisation.md)
- [What is SLAM?](SLAM/what-is-slam.md)

## Sensors for SLAM
- [Position acquisition (relative vs. absolute)](sensors/position-acquisition.md)
- [SLAM hardware](sensors/slam-hardware.md)

### Relative
- [Odometry](definitions/odometry.md)
- [IMU](sensors/imu.md)

### Absolute
- [Sensors (absolute measurements) for measuring distance to landmarks](sensors/sensors-absolute.md)


- [Visual sensors for localisation](sensors/visual-sensors-for-localisation.md)
  - [Monocular depth perception](permanent/10-monocular-depth-perception.md)
  - [Pinhole camera model](studienarbeit/pinhole-camera-model.md)
  - [Camera calibration](studienarbeit/camera-calibration.md)
  - [World to camera trafo](studienarbeit/world-to-camera-trafo.md)

### Fusion
- [Multisensor fusion](studienarbeit/multisensor-fusion.md)
- [Loose vs Tight coupling](studienarbeit/loose-vs-tight-coupling.md)
- [Why use the visual-inertial sensor combination?](SLAM/why-use-the-visual-inertial-sensor-combination.md)

## Visual SLAM
- [Classification of image-based camera localization approaches](classification-of-image-based-camera-localization-approaches.md)
- [Visual SLAM Implementation Framework](SLAM/vslam-framework.md)
- [Feature-based vs direct SLAM workflow](feature-based-vs-direct-slam-workflow.md)

### Sparse vs dense
- [Sparse/Feature-based VSLAM](studienarbeit/sparse-feature-based-vslam.md)
- [Dense/direct VSLAM](studienarbeit/dense-direct-vslam.md)

### Landmarks/Feature extraction
- [landmarks](SLAM/landmarks.md)
- [Bag of words](studienarbeit/bag-of-words.md)

[Data association](SLAM/data-association.md)

### Loop closure
- [Loop closing in VIORB](SLAM/loop-closing-in-viorb.md)
- [Loop closure detection](SLAM/loop-closure-detection.md)

### Filtering vs optimisation
[Filter-based vs optimisation-based SLAM](studienarbeit/filter-based-vs-optimisation-based-slam.md)

#### Filter-based
- [Filter localisation methods](SLAM/filter-localisation-methods.md)
- [Extended Kalman Filter](SLAM/extended-kalman-filter.md) - [basic ekf-for-slam](SLAM/basic-ekf-for-slam.md)
- [rlabbe Kalman/Bayesian filters in Python](studienarbeit/rlabbe-kalman-bayesian-filters-in-python.md)

#### Keyframe-based
- [Some optimisation-based tightly-coupled multisensor SLAM algorithms](SLAM/algos-optimisation-based.md)
- [Handling the computational complexity of optimisation-based SLAM](studienarbeit/handling-the-computational-complexity-of-optimisation-based-slam.md)

### Established SLAM algorithms
- [Some optimisation-based tightly-coupled multisensor SLAM algorithms](SLAM/algos-optimisation-based.md)
- [State-of-the-art SLAM](studienarbeit/state-of-the-art-slam.md)
- [Mur-Artal 2017 VI-ORB](bibliography/mur-artal-2017-vi-orb.md)
- [Lamarca 2020 DefSLAM](studienarbeit/lamarca-2020.md)

### Resources
[SLAM resources](slam-resources.md)

