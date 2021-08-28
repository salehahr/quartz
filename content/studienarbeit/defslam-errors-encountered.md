---
title: DefSLAM errors encountered
date: "2021-01-13"
external_url: "http://www.google.com/search?client=firefox-b-d&q=segmentation+fault"
tags:
  - -sa/processed
  - software/cpp
  - SLAM/algos/DefSLAM
---

Rebuilding DefSLAM in Debug mode
Error: "Virtual memory exhausted: Cannot allocate memory"
![unknown_filename.png](./_resources/DefSLAM_errors_encountered.resources/unknown_filename.png)
Solution: reduce degree of make -j

Segmentation fault in Defslam debug mode
![unknown_filename.1.png](./_resources/DefSLAM_errors_encountered.resources/unknown_filename.1.png)

Based on <http://stackoverflow.com/questions/19615371/segmentation-fault-due-to-vectors>
Changed: surfacePoints\_\[ind\] to surfacePoints\_.at(ind)

New error
![unknown_filename.2.png](./_resources/DefSLAM_errors_encountered.resources/unknown_filename.2.png)
surfacePoints\_ appears to be NULL? 
Was it instantiated in another thread?
<http://stackoverflow.com/questions/11645857/debugging-with-gdb-why-this-0x0>

Using core dumps with gdb
<http://jvns.ca/blog/2018/04/28/debugging-a-segfault-on-linux/>

