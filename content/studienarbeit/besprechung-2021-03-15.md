---
title: Besprechung 2021-03-15
date: "2021-03-15"
tags:
  - -sa/processed
  - discussion/2021/2021-03
  - discussion/2021/2021-04
---

Status

*   Last week: generated noisy IMU data (pose) from stereo trajectory, 'offline' Kalman
*   This week: Kalman + 'live' DefSLAM
*   Still to do: design KF (EKF, or other methods...)

* * *

'Offline' Kalman

*   To learn how to use openCV's Kalman filter without having to rebuild DefSLAM every time
    Aim was to figure out the update/correction workflow and implement it in live DefSLAM run
    
*   Uses pre-extracted trajectories (mono and stereo)
*   Only testing update/correction of xyz coordinates, not the orientation
*   Update procedure ...

~~KF + 'live' DefSLAM~~

*   ~~Still have got to try out updating the pose while no images are received~~
    *   ~~- [ ] set state to LOST, or do System::Reset, or completely not carry out SLAM.TrackMonocular depending current timestamp~~
*   ~~at present, Kalman update from Frame 220 to Frame 260,, crash around frame 272~~
*   ~~angles look weird~~

* * *

After meeting notes

*   Continue working on offline Kalman until it works properly, then only implement it live
*   Make Kalman filter use raw IMU measurements
*   Incorporate DefSLAM pose (from optimisation) as an extra measurement to the KF
    *   Method I: freeze covariance matrix for the DefSLAM measurements
        maybe P -> infinity for DS measurements between frames
        or: use old DS measurements to fill in the gaps (between frames)
        
    *   ~~Method II: use MHE~~, scrapped because solver needed -- makes it harder to achieve real-time capability
*   Get pie at 12 pm

