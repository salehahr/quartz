---
title: Qin 2019 General Optimization-based Framework (Multisensor)
date: "2020-08-07"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-read
  - discussion/2020/2020-08
  - -sa/to-be-processed
---

Authors: Qin et al
Code: <http://github.com/HKUST-Aerial-Robotics/VINS-Fusion> (uses ROS)

![unknown_filename.3.png](./_resources/[Qin_2019]_General_Optimization-based_Framework_(Multisensor).resources/unknown_filename.3.png)

Abstract:

*   odometry estimation with multiple sensors, general framework which is optimisation-based
*   demonstrated combinations:
    *   stereo cameras
    *   monocular cam + IMU
    *   stereo cams + IMU
*   sensor = factor in the framework
*   comparison with other state-of-the-art algos

Aim:

*   to create a general algo which supports different multisensor suites
*   also for redundancy: in case of sensor failure, it can be switched out easily

Related work:

*   multiple sensors to increase robustness of state estimation
*   two trends for multisensor fusion
    *   filter-based
    *   optimisation-based/bundle adjustment — graph-based
        *   outperform the filter-based algorithms in term of accuracy at the cost of computational complexity.

Framework
![unknown_filename.1.png](./_resources/[Qin_2019]_General_Optimization-based_Framework_(Multisensor).resources/unknown_filename.1.png)
Factors (sensors) constrain a state or several states

Optimisation problem

*   Solve the graph: find states which satisfy the constraints (edges)
*   MLE (Maximum Likelihood Estimation) problem: joint probability distribution of robot poses over a period of time
    ![unknown_filename.png](./_resources/[Qin_2019]_General_Optimization-based_Framework_(Multisensor).resources/unknown_filename.png)
    
*   Marginalization procedure summarises past measurements into one prior term (to reduce complexity due to huge number of states)

Results
![unknown_filename.2.png](./_resources/[Qin_2019]_General_Optimization-based_Framework_(Multisensor).resources/unknown_filename.2.png)

*   IMU integration works successfully in all sequences; improves motion tracking by bridging the gap when visuals are not so good
    *   stereo-only method performed worst in most sequences
*   stereo + IMU didn’t always perform best, because it requires a more accurate calibration compared to mono + IMU
*   results outperform [OKVIS](http://www.evernote.com/shard/s484/nl/217355218/ec22bc95-10ac-46e4-ae59-60c67cd8501f)

