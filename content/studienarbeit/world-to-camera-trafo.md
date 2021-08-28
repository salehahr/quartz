---
title: World to camera trafo
date: "2021-03-03"
tags:
  - sensors/cameras
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)
See also: [Pinhole camera model](pinhole camera model.md), [pinhole camera-projection-function](pinhole-camera-projection-function.md)
Source: <http://www.cse.psu.edu/~rtc12/CSE486/lecture12.pdf>

|     |     |     |
| --- | --- | --- |
| Camera coordinates (X, Y, Z) | World coordinates (U, V, W) | Image plane (x, y) / Pixel coordinates (u, v) |
| ![unknown_filename.1.png](./_resources/World_to_camera_trafo.resources/unknown_filename.1.png) | ![unknown_filename.png](./_resources/World_to_camera_trafo.resources/unknown_filename.png) | ![unknown_filename.2.png](./_resources/World_to_camera_trafo.resources/unknown_filename.2.png)<br>![unknown_filename.3.png](./_resources/World_to_camera_trafo.resources/unknown_filename.3.png) |

Forward projection

![unknown_filename.4.png](./_resources/World_to_camera_trafo.resources/unknown_filename.4.png)

Representing 2D point as a fictitious 3D point (x', y', z') \[for matrix calculations\]
Convention: Given (x', y', z'), we can recover the 2D point (x, y) as
![unknown_filename.5.png](./_resources/World_to_camera_trafo.resources/unknown_filename.5.png)

World to camera trafo

*   Translation of -C as seen in W-CS
*   Apply rotation Rcw to get P in camera coordinates
    pc = Rcw (pw - cw)
    

![unknown_filename.6.png](./_resources/World_to_camera_trafo.resources/unknown_filename.6.png)
![unknown_filename.7.png](./_resources/World_to_camera_trafo.resources/unknown_filename.7.png)

