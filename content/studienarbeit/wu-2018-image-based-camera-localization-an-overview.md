---
title: (Wu 2018) Image-based camera localization
date: "2020-07-30"
external_url: "http://link.springer.com/article/10.1186/s42492-018-0008-z"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-read
  - SLAM/VSLAM
  - -sa/processed
---

Authors: Wu, Tang, Li

Abstract/Contents

*   overview (classification) of image-based camera localization
*   classification of image-based camera localization approaches
*   techniques, trends
*   only considers 2D cameras
*   focuses on points as features in images (not lines etc)

Chapters
[Classification of image-based camera localization approaches](classification-of-image-based-camera-localization-approaches.md)
[Multisensor fusion](multisensor fusion.md) —  [why use the visual-inertial sensor combination?](why-use-the-visual-inertial-sensor-combination_.md)
[Loose vs Tight coupling](loose-vs-tight-coupling.md)
[Filter localisation methods](filter-localisation-methods.md)
[Some optimisation-based tightly-coupled multisensor SLAM algorithms](some-optimisation-based-tightly-coupled-multisensor-slam-algorithms.md)

Questions

*   [x] What's a metric map -- normal map (with landmarks, normal distances) as opposed to a topological one

![unknown_filename.png](./_resources/[Wu_2018]_Image-based_camera_localization__an_overview.resources/unknown_filename.png)

Takeaway

*   Learning SLAM is gaining in popularity, but geometric SLAM is often the chosen method for most applications, as it is more generalisable and at the same time reasonably accurate
*   For reliability and low cost practical applications, multisensor vision-centred fusion is an effective method.
*   Possibly interesting: embedded SLAM algorithms
*   Trend for a practical SLAM system: integrating all possible techniques
    *   e.g. geometric and learning fusion, multi-sensor fusion, multi-feature fusion, feature based and direct approaches fusion
    *   may solve the current challenges of poorly textured scenes, large illumination changes, repetitive textures, highly dynamic motions

