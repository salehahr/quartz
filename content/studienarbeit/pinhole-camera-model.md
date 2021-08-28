---
title: Pinhole camera model
date: "2020-10-20"
tags:
  - sensors/cameras
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)
Backlinks: [Camera calibration](camera calibration.md), [pinhole camera projection function](pinhole camera projection function.md), [weiss thesis vision based navigation for micro helicopters](weiss thesis vision-based-navigation-for-micro-helicopters.md)
See also: [World to camera trafo](world-to-camera-trafo.md)

Source: <http://de.mathworks.com/help/vision/ug/camera-calibration.html>
Does not account for lens distortion (ideal pinhole camera doesn't have a lens)
To represent a real camera, the full camera model to be used should include (radial and tangential) lens distortion, (such as the one used in the MATLAB computer vision toolbox)

![unknown_filename.png](./_resources/Pinhole_camera_model.resources/unknown_filename.png)

Camera matrix P

*   Parameters are represented by a 4x3 camera matrix
*   Maps 3Dp -> 2Dp (image plane)
*   Extrinsic parameters
    *   location of the camera in the 3D world
    *   maps 3Dp (world) -> camera coordinates
*   Intrinsic parameters
    *   non-positional parameters
    *   maps camera coords -> 2Dp (image)
    *   optical centre (principal point), focal length, skew coefficient

![unknown_filename.1.png](./_resources/Pinhole_camera_model.resources/unknown_filename.1.png)
![unknown_filename.2.png](./_resources/Pinhole_camera_model.resources/unknown_filename.2.png)  ![unknown_filename.3.png](./_resources/Pinhole_camera_model.resources/unknown_filename.3.png)

Intrinsic parameters
K = ![unknown_filename.4.png](./_resources/Pinhole_camera_model.resources/unknown_filename.4.png)   ![unknown_filename.5.png](./_resources/Pinhole_camera_model.resources/unknown_filename.5.png)
![unknown_filename.6.png](./_resources/Pinhole_camera_model.resources/unknown_filename.6.png)

