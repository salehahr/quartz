---
title: Viewer segfault
date: "2021-02-02"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

![unknown_filename.png](./_resources/Viewer_segfault.resources/unknown_filename.png)

**Error**
\[New Thread 0x7fff86ffd700 (LWP 1117)\]
NORMALS REESTIMATED : 277 - 277
\[Thread 0x7fff86ffd700 (LWP 1117) exited\]
NORMAL ESTIMATOR OUTPoints potential : 293  70
New template requested
Number Of normals 277 0x555566923da0
\-0.79956  0.655022 -0.594482POINTS matched:167
Points
Scale Error Keyframe : 1
stan dev 0.310974
chi 0.013115  0.01  201
SurfaceRegistration not sucessful (Not enough points to align or chi2 too big

Thread 6 "DefSLAM" received signal SIGSEGV, Segmentation fault.
\[Switching to Thread 0x7fffc1996700 (LWP 275)\]
\_\_memmove\_avx\_unaligned\_erms () at ../sysdeps/x86\_64/multiarch/memmove-vec-unaligned-erms.S:379
379     ../sysdeps/x86\_64/multiarch/memmove-vec-unaligned-erms.S: No such file or directory.

**Backtrace**
(gdb) bt
#0  0x00007ffff4f7eb80 in \_\_memmove\_avx\_unaligned\_erms ()
    at ../sysdeps/x86\_64/multiarch/memmove-vec-unaligned-erms.S:379
#1  0x00007fffa6e31853 in  () at /usr/lib/x86\_64-linux-gnu/dri/swrast\_dri.so
#2  0x00007fffa7267cc1 in  () at /usr/lib/x86\_64-linux-gnu/dri/swrast\_dri.so
#3  0x00007fffa68d1012 in  () at /usr/lib/x86\_64-linux-gnu/dri/swrast\_dri.so
#4  0x00007fffa68d2bfa in  () at /usr/lib/x86\_64-linux-gnu/dri/swrast\_dri.so
#5  0x00007fffa6a4dfc7 in  () at /usr/lib/x86\_64-linux-gnu/dri/swrast\_dri.so
#6  0x00007fffa6a4fc50 in  () at /usr/lib/x86\_64-linux-gnu/dri/swrast\_dri.so
#7  0x00007ffff78f6ca7 in defSLAM::MeshDrawer::drawMesh(double, bool) (this=0x5555661fb0f0, alpha=alpha@entry=1, drawedges=drawedges@entry=true) at /home/user3/slam/DefSLAM/Modules/Viewer/MeshDrawer.cc:112
#8  0x00007ffff78e6141 in defSLAM::DefMapDrawer::DrawTemplate() (this=0x5555557f8e40)
    at /home/user3/slam/DefSLAM/Modules/Viewer/DefMapDrawer.cc:250
#9  0x00007ffff78ee739 in defSLAM::DefViewer::Run() (this=0x5555557f70c0)
    at /home/user3/slam/DefSLAM/Modules/Viewer/DefViewer.cc:169

Possible solution
<http://stackoverflow.com/questions/43805701/can-someone-interpret-this-for-me>

