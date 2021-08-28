---
title: Discussion 2021-05-10
date: "2021-05-10"
tags:
  - -resources
  - filters/EKF
  - -sa/processed
  - discussion/2021/2021-05
---

Agenda

*   Change/Reduction of scope of SA (from fusing IMU with camera) to using sensor fusion to determine transformation parameters between IMU and camera
*   Camera and IMU setup involves kinematic modelling (not fixed transformation as previously assumed!)
*   Offline implementation in Python/MATLAB (scripting language)
*   HiWi tasks can include
    *   DefSLAM bindings / interface
    *   C++ bindings of skrogh EKF implementation?
*   HiWi prioritises Versuchsstand for now

Tasks

1.  [x] Find an EKF implementation that works well and can be used with DefSLAM + IMU data
2.  [x] implement kinematic model equations in the prediction-step, s.  [discussion-2021-05-25](discussion-2021-05-25.md)

![unknown_filename.jpeg](./_resources/Discussion_2021-05-10.resources/unknown_filename.jpeg)

Links related to Task 1
[http://github.com/search?o=desc&q=ekf+slam&s=stars&type=Repositories](http://github.com/search?o=desc&q=ekf%2Bslam&s=stars&type=Repositories)

*   [http://github.com/ydsf16/aruco\_ekf\_slam](http://github.com/ydsf16/aruco_ekf_slam) : uses ROS? C++
*   <http://github.com/JzHuai0108/ekfmonoslam> : MATLAB
*   <http://github.com/AtsushiSakai/PythonRobotics> : doc <http://pythonrobotics.readthedocs.io/en/latest/modules/localization.html
- extended-kalman-filter-localization> — hard coded pred. eqns (vel model?) (can be overloaded?)
*   <http://filterpy.readthedocs.io/en/latest/kalman/ExtendedKalmanFilter.html> : nbviewer <http://nbviewer.jupyter.org/github/rlabbe/Kalman-and-Bayesian-Filters-in-Python/blob/master/11-Extended-Kalman-Filters.ipynb>

<http://github.com/micropython-IMU/micropython-fusion>
<http://github.com/enginBozkurt/Error-State-Extended-Kalman-Filter>

