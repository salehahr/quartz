---
title: Thesis restructure
date: "2021-06-21"
tags:
  - -sounding-board
  - -master
  - -sa/processed
  - -master/thesis
  - discussion/2021/2021-07
  - discussion/2021/2021-08
---

Parent: [Thesis](thesis.md)
Backlinks: [Next update 2021-06](next-update-2021-06.md)

Introduction

*   General
    *   Bladder cancer surgery — cryosection
    *   The navigation/localisation problem
    *   GRK
*   Problem statement
    *   Questions arising from the localisation task:
        1.  Which localisation algorithm do we use?
        2.  We have settled on the camera-IMU combination.
            How do we take into account the non-constant calibration parameters between the camera and IMU (due to the surgeon's manipulation of the cystoscope)?
            
    *   Also, modularity of setup: the calibration estimation allows the IMU-camera combination to be applied to different devices 
*   Corresponding contributions

1.  Literature research deformable VI localisation
2.  Modelling the kinematic relations between the IMU and camera on the cystoscope
    Estimation of IMU calibration parameters for VI localisation on cystoscope
    

Literature review (I)

*   Use SLAM (unknown environment)
    *   KF vs optimisation-based SLAM
    *   sparse vs. dense approach
    *   front end
    *   back end
        *   filtering
        *   optim
*   Sensors for VI-SLAM
*   DefSLAM (deformable environment)

Background

*   Endoscopes
    *   Components and specifications
    *   Effect of the angled tip -- direction of view
    *   Coupling mechanism
*   Camera model
*   IMU model
*   General rotation + Quaternion stuff? or move to appendix. or skip entirely.
*   ESKF

**Implementation**

*   In this preliminary work, use KF & sparse approach
    *   Future work may make use of optimisation-based approaches and dense maps -- more for the localisation side though

*   Model of probe, kinematics
    *   forward kinematics using rtb
*   Generation of synthetic IMU data from camera data and probe kinematics, s. [Obtaining IMU measurements from camera by forward kinematics](obtaining imu measurements-from-camera-by-forward-kinematics.md)
*   EKF (tight/loose coupled approach) --> [ ] move to lit review
*   ESKF
    *   Our assumptions, simplified states

Validation/Results (II)

*   Validating the generation of synthetic IMU data
*   Results from the calib. param. estimation
    

?maybe: Compare DefSLAM stereo to mono+IMU

Conclusion and future work
This (estimation of the IMU-camera calibration parameters) provides the groundwork for implementing actual SLAM (VI fusion)
[Ausblick](ausblick.md)

Bilder Versuchsstandaufbau

