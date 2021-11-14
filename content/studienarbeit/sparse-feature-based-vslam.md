---
title: Sparse/Feature-based VSLAM
date: "2020-07-30"
tags:
  - SLAM/sparse-vs-dense/feature-based
  - -sa/processed
  - -published
---

Parent: [Visual SLAM Implementation Framework](SLAM/vslam-framework.md), [slam_index](SLAM/slam_index.md)
See also: [Feature-based vs direct SLAM workflow](feature-based-vs-direct-slam-workflow.md)

Source: [cometlabs](bibliography/cometlabs.md)

*   Front-end part of the [Visual SLAM Implementation Framework](SLAM/vslam-framework.md)
*   Use only a small selected subset of the pixels in an image frame
*   [Feature maps](feature-maps.md) generated are point clouds --> used to track the camera pose
*   Requires feature extraction and [matching](studienarbeit/feature-matching.md)
*   To minimise: reprojection error (difference between a point's tracked location and where it is expected to be given camera pose estimate)
*   Pose estimation based on [RANSAC](SLAM/ransac.md)
*   A frame with most of its features concentrated in a small area: bad as the features are more likely to overlap

![unknown_filename.png](./_resources/Sparse_Feature-based_VSLAM.resources/unknown_filename.png)
Sparse

![unknown_filename.1.png](./_resources/Sparse_Feature-based_VSLAM.resources/unknown_filename.1.png)
Semi-dense

