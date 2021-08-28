---
title: ORBSLAM::Frame constructor (monocular)
date: "2020-10-28"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Source: [Tracking::GrabImageMonocular](tracking__grabimagemonocular.md)

*   Set scale level info from ORB extractor
*   Extract ORB features
    *   mvKeys (vector of keypoints/features)
*   Set N number of features
*   Make mvpMapPoints (null, but with size N), mvbOutlier (all entries false, size N)
*   If first frame or calibration change:
    *   ComputeImageBounds
*   AssignFeaturesToGrid()

