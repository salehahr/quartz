---
title: DefTracking::MonocularInitialization
date: "2020-10-28"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Parent: [DefTracking::Track](deftracking__track.md)

Initialises

*   surface
*   points in the surface

If num. features in current frame > 100

*   set frame pose to origin
*   make new KF (GroundTruthKeyFrame) pKFini
*   add the KF to the map mpMap
*   iterate over the N features
    *   get feature kp
    *   convert kp to 3d point
    *   make new DefMapPoint(3dp, pKFini, mpMap)
    *   set pointers between DefMapPoint, GroundTruthKeyFrame, DefMap
*   Save surface using bbs
*   Set mLastFrame := mCurrentFrame
*   **Local window**: Add KF to local KFs vector, add MapPoints to local MP vector, mpLocalMapper
*   Calculate Tcr from Tcw
*   **Initialise SLAM**: Set reference KF, reference MapPoints
*   set mState to OK

