---
title: Camera calibration
date: "2020-11-20"
tags:
  - sensors/cameras
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)
Source: <http://de.mathworks.com/help/vision/ug/camera-calibration.html>

*   estimates lens/sensor parameters
*   e.g. to correct lens distortion, determine position, measurement etc
*   there are several camera models, e.g. fisheye, [pinhole](pinhole.md)

Camera parameters

*   [intrinsic](intrinsic.md)
*   [extrinsic](extrinsic.md)
*   distortion coefficients

How to solve for camera parameters?

1.  Need to have 3D world points and the corresponding 2D image points
2.  Take multiple images of a calibration pattern to obtain these correspondences
3.  With the mapping 3Dp -> 2Dp, solve for camera parameters

Evaluate accuracy of estimated camera parameters:

*   plot relative locations of the camera and the calibration pattern
*   calculate reprojection error
*   calculate parameter estimation error

