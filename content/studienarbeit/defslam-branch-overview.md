---
title: DefSLAM branch overview
date: "2021-02-19"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
  - discussion/2021/2021-03
---

Parent: [SA TODO](sa-todo.md)

Repo
<http://github.com/feudalism/DefSLAM>

Dormant

*   master
*   sa

Deprecated

*   windows - deprecated, changes made for building on Windows
*   imu - deprecated, has Imu tracking functions but dependencies not resolved
*   obs\_tuple - initial attempt to incorporate Atlas, attempt to use OS3's structure for MapPoint observations : <KeyFrame, tuple<int, int>> as opposed to <Keyframe, int> in DefSLAM+OS2

Temporary/Experimental

*   s. to do list
*   [debugging the segfault](http://github.com/feudalism/DefSLAM/tree/db_segf_nsp) that seemingly appears in Surface::getNormalSurfacePoint
    seems to happen after System reset
    
*   [sockets](http://github.com/feudalism/DefSLAM/commits/sockets)

To-do

*   [x] code to [read out DefSLAM pose](http://github.com/feudalism/DefSLAM/tree/extractpose) and write
    *   [x] visualisation
        *   [x] post process using trajectory.txt
        *   [ ] [live vis. of trajectory using sockets](http://github.com/feudalism/DefSLAM/commits/sockets) — for later!
    *   [x] [write access to camera-pose](write-access-to-camera-pose.md)
        done, but map points in optimisation step push Tcw back to its original trajectory before the update
        
*   [ ] [DefSLAM + Kalman](http://github.com/feudalism/DefSLAM/commits/kalman)
    *   [x] load DefSLAMGT poses to be used as measurements
    *   [ ] implement filter (prereq: make sure write function works)
*   [ ] DefSLAM + ORBSLAM3
    *   [x] System ctor for IMU\_MONOCULAR case
        *   [x] Map::SetInertialSensor()
        *   [x] DefTracking::ctor
        *   [x] DefLocalMapping::ctor
        *   [x] ? LoopCloser?
    *   [ ] System::TrackMonocularIMU
        *   - [x] Tracker::ResetActiveMap
        *   [x] Tracker::GrabImuData
        *   [ ] DefTracker::DefGrabImageMonocular
            *   [x] ImuFrame ctor
                *   [x] ImuFrame::ExtractORB (vLapping for stereo)
            *   [ ] [DefTracker::TrackWithImu](http://github.com/feudalism/DefSLAM/commits/dt_trackwimu)
                *   [x] Map::IsImuInitialised
                *   [x] System::Reset
                    might need to change some stuff here to prevent a segfault occurring
                    *   [x] Tracker::Reset
                        *   [x] localMapper.requestReset
                        *   [x] Atlas::ClearAtlas
                        *   [x] Atlas::CreateNewMap (new map ptr in OS3, defSLAM reuses old ptr)
                *   [x] System::ResetActiveMap
                    *   [x] Tracker::ResetActiveMap
                        *   [x] localMapper::RequestResetAM
                        *   [x] Atlas::ClearMap
                            *   [x] Map::Clear
                *   [x] PreintegrateImu
                *   [x] Tracker::MonocularInitialization
                *   [x] change mCurrentFrame in Tracking from pointer to object
                *   [ ] TrackWithMotionModel
                *   [ ] ...
                *   [ ] TrackLocalMap (main tracking function?)
                *   [ ] ...

Notes
Mandala dataset: 30 fps (from DefSLAM paper), 640x480 px
1560936003.993-1560936003.113 (first 30 frames à 1s), i.e. \*1e-3 to get real timestamp

