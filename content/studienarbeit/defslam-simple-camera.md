---
title: DefSLAM simple_camera
date: "2020-10-19"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Without ground truth

App run
// Create defSLAM::system, which initializes all threads (local mapping, ~~loop closing~~, viewer)
[defSLAM::System](http://www.evernote.com/shard/s484/nl/217355218/c460b4e1-e0ae-4d47-8423-6d840e453d24) SLAM(orbVocab, calibFile, bUseViewer);

// Timestamp
uint timestamp := 0;

// Process frames from video capture
while (capture.isOpened())
{
 // Get the capture as a matrix;
 // SLAM
 SLAM.[TrackMonocular](defslam-system-trackmonocular.md)(img\_matrix, timestamp);
 timestamp++;
}

