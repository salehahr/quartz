---
title: defSLAM::System::TrackMonocular
date: "2020-10-21"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Parent: [DefSLAM simple\_camera](defslam-simple-camera.md)

cv::Mat defSLAM::System::TrackMonocular
cv::Mat Tcw = mpTracker->[GrabImageMonocular](tracking-grabimagemonocular)(im, timestamp);

// get information from mpTracker:
// get states mTrackingState
// get map points mTrackedMapPoints
// get key points mTrackedKeyPointsUn

// return camera pose
return Tcw;

