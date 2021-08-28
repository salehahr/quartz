---
title: Sparse/Feature-based VSLAM
date: "2020-07-30"
tags:
  - SLAM/sparse-vs-dense/feature-based
  - -sa/processed
---

Parent: [Visual SLAM Implementation Framework](visual-slam-implementation-framework.md), [slam-index](slam-index.md)
See also: [Feature-based vs direct SLAM workflow](feature-based-vs-direct-slam-workflow.md)

Source: [Cometlabs What You Need to Know About SLAM](cometlabs what you-need-to-know-about-slam.md)

*   Front-end part of the [Visual SLAM Implementation Framework](visual-slam-implementation-framework.md)
*   Use only a small selected subset of the pixels in an image frame
*   [Feature maps](feature-maps.md) generated are point clouds --> used to track the camera pose
*   Requires feature extraction and [matching](matching.md)
*   To minimise: reprojection error (difference between a point's tracked location and where it is expected to be given camera pose estimate)
*   Pose estimation based on [RANSAC](http://www.evernote.com/shard/s484/nl/217355218/78822a3d-a9b1-40e3-b580-e0af94697de9?title=RANSAC)
*   A frame with most of its features concentrated in a small area: bad as the features are more likely to overlap

![unknown_filename.png](./_resources/Sparse_Feature-based_VSLAM.resources/unknown_filename.png)
Sparse

![unknown_filename.1.png](./_resources/Sparse_Feature-based_VSLAM.resources/unknown_filename.1.png)
Semi-dense

