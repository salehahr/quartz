---
title: Chen 2018 Review of VI SLAM
date: "2020-08-24"
external_url: "http://www.researchgate.net/publication/327064224_A_Review_of_Visual-Inertial_Simultaneous_Localization_and_Mapping_from_Filtering-Based_and_Optimization-Based_Perspectives"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-read
  - SLAM/multisensor
  - -sa/processed
  - -published
---

**Source**: <http://www.mdpi.com/2218-6581/7/3/45>  
**Authors**: Chen et. al

## Abstract

*   Survey on visual-inertial SLAM over the last 10 years
*   Aspects: filtering vs optimisation based, camera type, sensor fusion type
*   Explains core theory of SLAM, feature extraction, feature tracking, loop closure
*   Experimental comparison of filtering-based and optimisation-based methods
*   Research trends for VI-SLAM

## Recommended other works
s. [Works of possible interest](bibliography/works-of-interest.md)

## Contents/Chapters
### SLAM
SLAM: build a real-time map of the unknown environment based on sensor data, while the sensor (robot) itself is traversing the environment

Growing prevalence of visual SLAM: rich in information compared yet low-cost (camera vs other sensors)

### Filtering-based:

*   Loose vs tight coupling
*   Feature extraction, feature tracking
*   Basic method framework (three step): propagation, image registration, update
*   Algorithms: MSCKF, Maplab

*   Loosely-coupled: usually only fuses the IMU to estimate partial state, not full POSE
*   Tightly-coupled: camera and IMU states are fused together into a motion and observation equation --> more common

### Optimisation-based:

*   front- vs back-end division (map construction vs pose optimisation)
*   Loop closure (odometry-based or appearance-based), preintegration
*   Algorithms: OKVIS (stereo), [VIORB](bibliography/mur-artal-2017-vi-orb.md), VINS-mono

## Takeaway
| **Filtering-based** | **Optimisation-based** |
| --- | --- |
| More advantageous w.r.t. computing resources | Good localisation accuracy with lower memory utilisation |

