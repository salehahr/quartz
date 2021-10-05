---
title: Template substitution in DefSLAM
date: "2020-11-25"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

**Parent**: [Mapping step-by-step in DefSLAM](mapping-step-by-step-in-defslam.md)  
**Source**: [lamarca-2020](studienarbeit/lamarca-2020.md)

![Image.png](./_resources/Template_substitution_in_DefSLAM.resources/Image.png)

*   Tracking runs at frame-rate, and mapping at keyframe-rate
*   Tracking processes Nm frames during a whole mapping run

## Process

1.  New keyframe $k$ is made. Now at time $t=k$
    *   At this point, the template in the tracking is still based on the old shape-at-rest, S\_(k-1)
    *   Mapping thread starts
        *   creates surface S\_k which is aligned to prev. template T\_(k-1)
        *   k is set as the reference keyframe
        *   from S\_k, create template T\_k and from now on use this template instead of the old one T\_(k-1)
2.  At time t=k+Nm, use data from the tracking thread
    *   image points at t=k+Nm
    *   deform the recently computed template T\_k based on these images
        *   use [SfT but neglecting the temporal term](sft-but-neglecting-the-temporal-term.md) (to allow large deformation, "as a lot might have happened in the time span of Nm")
        *   so now we get a T\_k that is deformed (updated) to the most recent image points
    *   we do this extra step instead of passing T\_k (from step 1) to the tracker immediately because, due to the new points occurring at t=k+Nm, using the original T\_k might lead to data association errors
    *   mapper passes the new template T\_k (t=k+Nm) to the tracker

