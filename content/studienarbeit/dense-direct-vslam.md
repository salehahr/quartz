---
title: Dense/direct VSLAM
date: "2020-07-30"
tags:
  - SLAM/sparse-vs-dense/direct-SLAM
  - -sa/processed
---

Parent: [Visual SLAM Implementation Framework](SLAM/vslam-framework.md), [slam_index](SLAM/slam_index.md)
See also: [Feature-based vs direct SLAM workflow](feature-based-vs-direct-slam-workflow.md)

Source: [Cometlabs What You Need to Know About SLAM](cometlabs what you-need-to-know-about-slam.md)

*   Front-end part of the [Visual SLAM Implementation Framework](SLAM/vslam-framework.md)
*   Use most or all of the pixels in each received frame
    *   Provide more information about the environment
*   Many more pixels, require GPUs
*   [Feature-based vs direct SLAM workflow](feature-based-vs-direct-slam-workflow.md)
*   Disadvantages:
    *   Don't handle outliers very well (outliers will be processed and implemented into the final map)
    *   Slower than [feature-based](feature-based.md) variants
*   Aims to minimise photometric error (intensity differences)

![unknown_filename.1.png](./_resources/Dense_direct_VSLAM.resources/unknown_filename.1.png)
Semi-dense

![unknown_filename.png](./_resources/Dense_direct_VSLAM.resources/unknown_filename.png)
Dense map

