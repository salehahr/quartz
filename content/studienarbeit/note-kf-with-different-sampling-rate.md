---
title: note KF with different sampling rate
date: "2021-03-24"
external_url: "http://stackoverflow.com/questions/59566384/kalman-filter-with-different-sampling-rate"
tags: 
- to-do/orphan 
- filters/kalman-filter 
- -sa/to-be-processed
---

Source: <http://stackoverflow.com/questions/59566384/kalman-filter-with-different-sampling-rate>

Approach 1: KF with variable dt
Approach 2: KF with static dt

'Sub' updates? e.g.

1.  predict()
2.  update() with sensor A
3.  skip update() for sensor B since no measurement arrived
4.  update() with sensor c
5.  repeat

Generally discouraged:

1.  If not predicting before each update, there is the risk of the filter lagging behind real world dynamics. The update step at t=k compares a measurement zk to the projected (predicted) state xk.
    This would however be ok if the real world dynamics are slower than the filter
    
2.  Separate updates --> redundant matrix operations. Split into different KFs if states are independent (purely diagonal matrices).

* * *

Source: <http://math.stackexchange.com/questions/694504/kalman-filter-with-sensors-having-different-sampling-rate>
Normally, what you should do when the rate of sensors do not match, is that

*   you should propagate states at a base sample rate (say 10Hz)
*   depending on your implementation you may propagate covariance only between measurements or all the time.
*   Once a measurement arrives, you perform the Kalman correction, updating your covariance and your state.

* * *

Source: \[Mirzaei 2008\] A Kalman Filter-Based Algorithm for IMU-Camera Calibration: Observability Analysis and Performance Evaluation -- 462
IMU sampling 100 Hz, i.e. T = 0.01s
When new IMU measurement received

*   state estimate propagated using 4th order RK integration of system dynamics
*   covariance propagation
    ![unknown_filename.png](./_resources/note__KF_with_different_sampling_rate.resources/unknown_filename.png)
    

Further reading
<http://www.ncbi.nlm.nih.gov/pmc/articles/PMC6339169/>
Fusion of High-Dynamic and Low-Drift Sensors Using Kalman Filters

* * *

Source: <http://www.visiondummy.com/2014/04/geometric-interpretation-covariance-matrix/>
Intuition covariance matrix
![unknown_filename.1.png](./_resources/note__KF_with_different_sampling_rate.resources/unknown_filename.1.png)

* * *

**Source:** Onur Sari 2020, Sensor Fusion for Localization of Automated Guided Vehicles

**Handling asynchronous measurements**

*   predict and update steps of the Kalman Filter are performed whenever a measurement is available
*   varying time interval between timesteps k and k + 1 in each KF cycle
*   F and Q are interval dependent matrices (recalculate in each prediction step)

![unknown_filename.2.png](./_resources/note__KF_with_different_sampling_rate.resources/unknown_filename.2.png)

