---
title: Discussion 2021-05-21
date: "2021-05-21"
tags:
  - -sa/processed
  - discussion/2021/2021-05
---

Notes — Before

*   Got the ESKF implementation (Solà) to work with my fake IMU data
    *   \[non-noisy IMU\] results look ok for low process noise (trust the prediction more) with relatively high measurement noise
    *   \[noisy IMU\] ok?
    *   current assumptions/simplifications:
        *   fake data assumes IMU is sitting right on top of camera
        *   fake data, as of yet, does not take into account: biases, gravity
        *   simplified state vector (no scale estimate, no gravity estimate, no bias estimate etc)
        *   TBD: [x] modify equations/states to fit the problem, i.e. to obtain the imu-camera trafo as an estimate instead of the imu/cam-position, s. [discussion-2021-05-25](discussion-2021-05-25.md)
    *   changes to code
        *   propagation function explicitly partitioned into: \_predict\_nominal, \_predict\_error, \_predict\_cov
        *   used the update equations/Jacobians given in the tutorial (Solà)
*   Had a look at FilterPy

Notes — After
[Endoscope/cystoscopy pics/videos](endoscope_cystoscopy-pics_videos.md)
[IMU on cystoscope](imu-on-cystoscope.md)

Next step
- [x] come up with equations for this, where the transformation for l1 is initially fixed (to be estimated later using ekf). l2 is assumed to be a rigid transformation. (s. [probe-forward-kinematics](probe-forward-kinematics.md))
![unknown_filename.png](./_resources/Discussion_2021-05-21.resources/unknown_filename.png)

![unknown_filename.1.jpeg](./_resources/Discussion_2021-05-21.resources/unknown_filename.1.jpeg)

Stuff I need

*   equations for calibration parameters (for predict\_nominal), maybe random walk?
*   Jacobians for predict\_error
*   corresponding process noise ... from actors?
*   noise values

