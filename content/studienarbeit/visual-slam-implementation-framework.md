---
title: Visual SLAM Implementation Framework
date: "2020-07-30"
tags:
  - SLAM/VSLAM
  - discussion/2020/2020-08
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)

Source: [Cometlabs What You Need to Know About SLAM](cometlabs what you-need-to-know-about-slam.md)

Basic principle:

*   tracking a set of points through successive frames
*   these tracks are used to triangulate the 3D positions of the points to create the map
*   at the same time, using the the est point locations to calculate the pose of the camera, which could have observed them (i.e. calculate real time 3D structure of a scene from the estimated motion of the camera)

![unknown_filename.png](./_resources/Visual_SLAM_Implementation_Framework.resources/unknown_filename.png)

Two main architecture components:

1.  Front-end
    *   Abstracts sensor data into models (which are good for estimation) / Processing
    *   [Data association](data-association.md)
        *   Short term (feature tracking); features in consecutive sensor measurements
            *   Either from [sparse maps](sparse-maps.md) or [dense-maps](dense-maps.md)
        *   Long term ([loop closure](http://www.evernote.com/shard/s484/nl/217355218/75ada851-3e4e-88e0-9788-ee8cc5e2f104?title=Loop%20closure%20detection)); associating new measurements to older landmarks
2.  [Back-end](back-end.md)
    *   Performs inference on the abstracted data produced by the front end

![unknown_filename.1.png](./_resources/Visual_SLAM_Implementation_Framework.resources/unknown_filename.1.png)

