---
title: DefTracking:TrackWithMotionModel()
date: "2020-10-21"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Parent: [DefTracking::Track](deftracking__track.md)

// Initial tracking to locate rigidly the camera and discard outliers.
bool DefTracking::TrackWithMotionModel()

// Update last frame relative pose according to its reference keyframe
UpdateLastFrame();

// Project points seen in prev frames
int th = 15;
int nmatches = Defmatcher.SearchByProjection(\*mCurrentFrame, mLastFrame, th,
 mSensor == System::MONOCULAR);

// Optimise frame pose with all matches to initialise camera pose
Optimizer::[poseOptimization](http://www.evernote.com/shard/s484/nl/217355218/c3625cbe-ddbe-4cbd-b447-00913cf6370d)(mCurrentFrame, myfile);

// Discard outliers

// return: sufficient number of matches?
return nmatchesMap >= 10;

