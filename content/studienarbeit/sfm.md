---
title: Structure from Motion
date: "2020-10-05"
tags:
  - -sa/to-be-processed
  - to-do/missing-tag
  - -published
---

**Source**: https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Schonberger_Structure-From-Motion_Revisited_CVPR_2016_paper.pdf

**Note**:
* This paper uses incremental SfM
* Corresponding paper for COLMAP

# Structure from motion
Reconstruction of 3D structure from a sequence of 2D images of that structure, taken from different viewpoints.

![](_img/sfm-pipeline.png)
1. Search for correspondence between images --> output: scene graph (nodes: images, edges: verified pairs)
	1. Feature extraction
	2. [Feature matching](studienarbeit/feature-matching.md)  
		Output: set of image pairs and their associated feature correspondences
	3. Verification: do features map to the same scene point?  
		Also: filter outliers e.g. using [RANSAC](SLAM/ransac.md)
2. Scene graph initialises the reconstruction stage --> output: {camera pose estimates, set of scene points}


---

**Source**: https://en.wikipedia.org/wiki/Structure_from_motion

# Structure from motion

Uses [motion-parallax](definitions/motion-parallax.md).

Geometric information to be estimated:
* 3D structure
* Camera motion

## Tasks
* find [correspondence between images](studienarbeit/feature-matching.md)
	* use feature detectors to detect features
	* feature matching to track the features across images  
		e.g. Lucas-Kanade tracker, [RANSAC](SLAM/ransac.md) to filter outliers
* reconstruct the 3D object
* reconstruct the camera motion

Feature trajectories over time are used to reconstruct their 3D positions as well as the camera motion [Dellaert, Thrun 2000].

Alternatively: feature-free methods / direct methods, where geometric information is directly estimated from the images without abstracting to features [LSD-SLAM]


## Approaches to SfM
* Incremental SfM: solve for camera poses one by one [Schönberger, Frahm 2016]
* Global SfM: solve for all camera poses at once [Tomasi, Kanade 1992]
* [NRSfM](studienarbeit/nrsfm.md)