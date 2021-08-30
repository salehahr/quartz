---
title: Classification of image-based camera localization approaches
date: "2020-07-30"
tags:
  - SLAM/VSLAM
  - -sa/processed
---

Parent: [SLAM Index](SLAM/slam_index.md)
Source: [Wu 2018 Image-based camera localization: an overview](wu 2018-image-based-camera-localization_-an-overview.md)

![unknown_filename.png](./_resources/Classification_of_image-based_camera_localization_approaches.resources/unknown_filename.png)

Unknown environment (must be reconstructed from image data)
Online/real-time mapping (SLAM)

*   [geometric metric SLAM](http://www.evernote.com/shard/s484/nl/217355218/41c3a019-d86e-7e60-40a5-d4680f7d668b?title=Geometric%20metric%20SLAM) (accurate computations, therefore still widely used in practice)
    *   monocular
    *   multiocular
    *   [multi-kind sensor](http://www.evernote.com/shard/s484/nl/217355218/0df3e4ab-19f4-4b5f-bd9f-eb689af9d991?title=Multi-kind%20sensors%20SLAM) (active)
        *   loosely-coupled
        *   closely-coupled
*   learning SLAM (active)
    *   needs a prior dataset to train NN -- dataset determines performanace of the SLAM
    *   low generalisation capability, therefore not as flexible as geom. SLAM
    *   Has a 3D map
*   [topological SLAM](http://www.evernote.com/shard/s484/nl/217355218/fe42bb48-04ca-333c-346e-c694bd94e354?title=Topological%20SLAM) (getting more unpopular)
*   marker SLAM (semi-known environment)

\[GEOM\] Filter-based SLAM
\[GEOM\] Keyframe-based SLAM(active)

*   Feature-based
*   Direct

