---
title: Feature-based vs direct SLAM workflow
date: "2020-08-03"
tags:
  - SLAM/sparse-vs-dense
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)

Source: [Cometlabs What You Need to Know About SLAM](cometlabs what you-need-to-know-about-slam.md)

|     |     |
| --- | --- |
| Feature-based (aka [sparse](sparse.md)) | direct (aka [dense](dense.md)) |
| Extraction of features required | No abstraction necessary |
| Aims to minimise error between point location estimate (from odometry) and location based on camera | Tracks objects by minimising photometric error (intensity differences) |

![unknown_filename.png](./_resources/Feature-based_vs_direct_SLAM_workflow.resources/unknown_filename.png)

