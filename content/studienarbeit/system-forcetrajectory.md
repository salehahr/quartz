---
title: System::forceTrajectory
date: "2021-03-04"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
  - discussion/2021/2021-03
---

Parent: [DefSLAM branch overview](defslam-branch-overview.md)

Reference: DefSLAMGT (stereo as ground truth)
For testing: DefSLAMVI

Description
Force update of DefSLAMVI's current frame pose to that of DefSLAMGT's for the frames 230 to 239

Without System::Reset
![unknown_filename.png](./_resources/System__forceTrajectory.resources/unknown_filename.png)
Frame pose is 'updated' during the interval, but after the interval, the optimisation (which uses frame pose as an estimate and also uses map node positions) makes the system resume it's trajectory before the update

(below: with pure monocular trajectory, without any forced updates)
![unknown_filename.2.png](./_resources/System__forceTrajectory.resources/unknown_filename.2.png)

With System::Reset
The system is reset after every forced pose update (i.e. every frame)
![unknown_filename.1.png](./_resources/System__forceTrajectory.resources/unknown_filename.1.png)
Immediately after the force update interval, everything goes to zero. Segfault at frame 252.

