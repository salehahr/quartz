---
title: Pinhole camera projection function
date: "2020-11-20"
tags:
  - sensors/cameras
  - -sa/processed
---

Backlinks: [Pinhole camera model](pinhole-camera-model.md)
See also: [World to camera trafo](world-to-camera-trafo.md)

Source: [Mur-Artal 2017 VI-ORB](bibliography/mur-artal-2017-vi-orb.md)
3D points
![unknown_filename.2.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.2.png)

Projection function ![unknown_filename.3.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.3.png)

*   Transforms 3D points into 2D points on image plane
    ![unknown_filename.4.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.4.png)
    
*   Focal length: ![unknown_filename.1.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.1.png)
*   Principal point: ![unknown_filename.6.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.6.png)
*   The projection does not consider the distortion due to the lens
    *   therefore when extracting image features, first undistort their coordinates
    *   only then match to projected points (existing features which have undergone projection from 3D to 2D)

Source: [Lamarca 2019 DefSLAM](lamarca-2019-defslam.md)
3D point:
![unknown_filename.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.png)

Projection function maps

*   [extrinsic camera parameters](extrinsic-camera-parameters.md) SE(3)
*   world map point

to a 2D image point (becomes a projected map point)

![unknown_filename.9.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.9.png)
![unknown_filename.7.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.7.png)
![unknown_filename.8.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.8.png) from camera transformation

Image

*   Set of observations in image: set of keypoints which are matched to map points
*   Normalised keypoint coordinates
    ![unknown_filename.5.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.5.png)
    

Source: <http://www.cse.psu.edu/~rtc12/CSE486/lecture12.pdf>
![unknown_filename.10.png](./_resources/Pinhole_camera_projection_function.resources/unknown_filename.10.png)
Derivation of the perspective projection

