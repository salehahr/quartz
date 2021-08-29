---
title: Thesis
date: "2021-06-21"
tags:
  - -sounding-board
  - -master/thesis
  - -sa/processed
  - -master/thesis
  - discussion/2020/2020-10
  - discussion/2021/2021-07
  - discussion/2021/2021-08
---

## Introduction

*   General
    *   Bladder cancer surgery — cryosection
    *   The navigation/localisation problem
    *   GRK
    *   [diagnosis-bladder-cancer](studienarbeit/diagnosis-bladder-cancer.md)
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
    

## Literature review (I)
*   Monocular visual SLAM: problem: depth info, s. [monocular depth perception](permanent/10-monocular-depth-perception.md)  
*   SLAM (general)
    *   Subsets of SLAM
    	*   [ ] feature-based vs direct SLAM
    *   SLAM rigidity assumption
    *   SLAM front end
        *   Begriffe data association, loop closure etc.
    *   SLAM back end (filtering/optim type)
        *   (adaptability/generalisability to other problems)
        *   MAP estimation stuff
    *   KF vs optimisation-based SLAM
    	*  [ ] the generalisability of optim.-based methods
    *   sparse vs. dense approach
    *   front end
    *   back end
        *   filtering
        *   optim
*   use of ORB features in def. envs
*   [ ] ORB-SLAM3 in lit review
*   Sensors for VI-SLAM
*   DefSLAM (deformable environment)
*   other papers on SLAM for deformable envs e.g. MIS-SLAM ([Chen](studienarbeit/chen-2018-mis-slam.md)), Song
*   [Works of possible interest](bibliography/works-of-interest.md)
*   Computer vision
    *   Descriptors: ORB, etc.
        *   Use of ORB for deformable envs.
    *   Bag of words
    *   Camera model (projection equation)

## Background

*   [Endoscopes](permanent/30-endoscopes.md)
    *   Components and specifications
    *   Effect of the angled tip -- direction of view
    *   Coupling mechanism, [modes of operation of the scope](studienarbeit/modes-of-operation-of-the-scope.md)
    *   [ ]  Relate endoscopy to bladder cancery surgery ...
*   Camera model
*   IMU model
*   General rotation + Quaternion stuff? or move to appendix. or skip entirely.
*   ESKF

## Implementation

*   In this preliminary work, use KF & sparse approach
    *   Future work may make use of optimisation-based approaches and dense maps -- more for the localisation side though

*   Model of probe, kinematics
    *   forward kinematics using rtb
*   Generation of synthetic IMU data from camera data and probe kinematics, s. [Obtaining IMU measurements from camera by forward kinematics](obtaining imu measurements-from-camera-by-forward-kinematics.md)
*   EKF (tight/loose coupled approach) --> [ ] move to lit review
*   ESKF
    *   Our assumptions, simplified states

## Validation/Results (II)

*   Validating the generation of synthetic IMU data
*   Results from the calib. param. estimation
    

?maybe: Compare DefSLAM stereo to mono+IMU

## Conclusion and future work
This (estimation of the IMU-camera calibration parameters) provides the groundwork for implementing actual SLAM (VI fusion)
[Ausblick](thesis/ausblick.md)

Bilder Versuchsstandaufbau


**To check before submitting**:
- [ ] [Fact checks](thesis/fact-checks.md)
- [ ] [Schönheitsfehler](thesis/schoenheitsfehler.md)
- [ ] [Tex stuff](thesis/tex-stuff.md)
- [ ] [Spelling](thesis/spelling.md)