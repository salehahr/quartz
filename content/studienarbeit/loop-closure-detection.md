---
title: Loop closure detection
date: "2020-08-03"
tags:
  - -sa/processed
  - SLAM/loop-detection
---

Parent:  [VSLAM Framework](vslam-framework.md), [slam-index](slam-index.md)

Source: [cometlabs](http://www.evernote.com/shard/s484/nl/217355218/1a11af29-6862-53e6-3b33-4608a7c87c15?title=What%20You%20Need%20to%20Know%20About%20SLAM)
Backlinks:  [Step 2: Re-observation](step-2-re-observation.md)

*   Process of observing the same scene by non-adjacent frames and adding a constraint (relationship? association?) between them
*   A long-term data association in the [VSLAM Framework](vslam-framework.md) (part of front end)
*   Sort of incorporates [topological SLAM](topological-slam.md) into metric SLAM

![unknown_filename.png](./_resources/Loop_closure_detection.resources/unknown_filename.png)
Importance

*   Final refinement step (in data association)
*   Important for obtaining a globally consistent SLAM solution, especially when optimising over a long period of time

Basic loop closure detection
Match the current frame to all previous frames using feature matching

*   Computationally expensive, not always suitable for real-time applications
*   For RT—a possible solution: Define [key frames](key-frames.md) and perform the comparison with only the key frames

Problems with loop closure

*   False positive/perceptual aliasing: Places are different, but are perceived as the same
*   False negative: Places are the same, but perceived as being different
*   Abhilfe: [precision recall curve](precision-recall-curve.md)

