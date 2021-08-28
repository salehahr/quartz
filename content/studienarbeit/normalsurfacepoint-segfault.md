---
title: NormalSurfacePoint Segfault
date: "2021-02-09"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

![unknown_filename.png](./_resources/NormalSurfacePoint_Segfault.resources/unknown_filename.png)

Crash around frame 65
\[New Thread 0x7fff7ffff700 (LWP 3854)\]
\[Thread 0x7fff7ffff700 (LWP 3854) exited\]
\[New Thread 0x7fff7ffff700 (LWP 3855)\]
\[Thread 0x7fff7ffff700 (LWP 3855) exited\]
\[New Thread 0x7fff7ffff700 (LWP 3856)\]

Thread 5 "DefSLAM" received signal SIGSEGV, Segmentation fault.
\[Switching to Thread 0x7fffc215d700 (LWP 3571)\]
defSLAM::SurfacePoint::thereisNormal (this=0x6705) at /home/user3/slam/DefSLAM/Modules/Mapping/SurfacePoint.cc:54
54        bool SurfacePoint::thereisNormal() { return NormalOn; }
(gdb) bt
#0  0x00007ffff78798a0 in defSLAM::SurfacePoint::thereisNormal() (this=0x6705)
    at /home/user3/slam/DefSLAM/Modules/Mapping/SurfacePoint.cc:54
#1  0x00007ffff7878f95 in defSLAM::Surface::setNormalSurfacePoint(unsigned long, cv::Vec<float, 3>&) (this=0x555565b0e030, ind=ind@entry=939, N=...) at /home/user3/slam/DefSLAM/Modules/Mapping/Surface.cc:84
#2  0x00007ffff7834a6d in defSLAM::NormalEstimator::ObtainK1K2() (this=this@entry=0x7fffc2155530)
    at /home/user3/slam/DefSLAM/Modules/Mapping/NormalEstimator.cc:223
#3  0x00007ffff7832846 in defSLAM::DefLocalMapping::NRSfM() (this=this@entry=0x5555633b07e0)
    at /home/user3/slam/DefSLAM/Modules/Mapping/DefLocalMapping.cc:178
#4  0x00007ffff7832d30 in defSLAM::DefLocalMapping::insideTheLoop() (this=this@entry=0x5555633b07e0)
    at /home/user3/slam/DefSLAM/Modules/Mapping/DefLocalMapping.cc:125
#5  0x00007ffff7832d9e in defSLAM::DefLocalMapping::Run() (this=0x5555633b07e0)
    at /home/user3/slam/DefSLAM/Modules/Mapping/DefLocalMapping.cc:85
#6  0x00007ffff54926df in  () at /usr/lib/x86\_64-linux-gnu/libstdc++.so.6
#7  0x00007ffff44206db in start\_thread (arg=0x7fffc215d700) at pthread\_create.c:463
#8  0x00007ffff4eed71f in clone () at ../sysdeps/unix/sysv/linux/x86\_64/clone.S:95

