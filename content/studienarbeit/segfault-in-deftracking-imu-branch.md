---
title: Segfault in DefTracking (imu branch)
date: "2021-01-20"
tags:
  - -sa/processed
  - software/cpp
  - SLAM/algos/DefSLAM
---

![unknown_filename.png](./_resources/Segfault_in_DefTracking_(imu_branch).resources/unknown_filename.png)

/home/user3/slam/datasets/mandala0/images/stereo\_im\_l\_1560936003993.png i:  30
POINTS matched:10
Track lost soon after initialisation, reseting...
/home/user3/slam/datasets/mandala0/images/stereo\_im\_l\_1560936004022.png i:  31
System Reseting
NORMAL ESTIMATOR IN - NORMALS REESTIMATED : 0 - 0
NORMAL ESTIMATOR OUTPoints potential : 939  70
New template requested
Number Of normals 0 0x5555636b1fb0
Not enough normals
Reseting Local Mapper... done
Reseting Loop Closing... done
Reseting Database... done

Thread 1 "DefSLAM" received signal SIGSEGV, Segmentation fault.
0x00007ffff78d9fae in cv::Mat::Mat (m=..., this=0x7ffffffeaea0) at /usr/local/include/opencv4/opencv2/core/mat.inl.hpp:545
545             step\[0\] = m.step\[0\]; step\[1\] = m.step\[1\];
(gdb) bt
#0  0x00007ffff78d9fae in cv::Mat::Mat(cv::Mat const&) (m=..., this=0x7ffffffeaea0) at /usr/local/include/opencv4/opencv2/core/mat.inl.hpp:545
#1  0x00007ffff78d9fae in defSLAM::DefTracking::UpdateLastFrame() (this=0x7ffff7e50010)
    at /home/user3/slam/DefSLAM/Modules/Tracking/DefTracking.cc:424
#2  0x00007ffff78e00de in defSLAM::DefTracking::TrackWithMotionModel() (this=0x7ffff7e50010)
    at /home/user3/slam/DefSLAM/Modules/Tracking/DefTracking.cc:357
#3  0x00007ffff78db3fb in defSLAM::DefTracking::Track() (this=0x7ffff7e50010) at /home/user3/slam/DefSLAM/Modules/Tracking/DefTracking.cc:103
#4  0x00007ffff4555d49 in ORB\_SLAM2::Tracking::GrabImageMonocular(cv::Mat const&, double const&) (this=0x7ffff7e50010, im=..., timestamp=@0x7fffffffded8: 1560936004022) at /home/user3/slam/DefSLAM/Thirdparty/ORBSLAM\_2/src/Tracking.cc:278
#5  0x00007ffff781d25f in defSLAM::System::TrackMonocularIMU(cv::Mat const&, double const&, std::vector<ORB\_SLAM3::IMU::Point, std::allocator<ORB\_SLAM3::IMU::Point> > const&) (this=0x7fffffffe100, im=..., timestamp=@0x7fffffffded8: 1560936004022, vImuMeas=std::vector of length 5, capacity 8 = {...}) at /home/user3/slam/DefSLAM/Modules/Common/System.cc:313
#6  0x000055555555cd1b in main(int, char\*\*) (argc=<optimized out>, argv=<optimized out>) at /home/user3/slam/DefSLAM/Apps/vi.cc:91
(gdb)

