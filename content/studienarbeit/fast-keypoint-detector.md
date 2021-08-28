---
title: FAST keypoint detector
date: "2020-12-08"
tags:
  - -sa/processed
  - vision
  - discussion/2020/2020-12
---

Source: <http://medium.com/data-breach/introduction-to-orb-oriented-fast-and-rotated-brief-4220e8ec40cf>
**Parent**: [ORB descriptor](orb-descriptor.md)

FAST (Features from Accelerated and Segments Test)

How it works

*   Given: pixel p, surrounded by other pixels in the image
*   Take the surrounding pixels that are in a small circle around p
    ![unknown_filename.jpeg](./_resources/FAST_keypoint_detector.resources/unknown_filename.jpeg)
    
*   If more than half of the surrounding pixels are darker/brighter than p, p is selected as a keypoint
*   Good for edge detection

**Drawbacks**

*   Noninvariant with respect to orientation and scaling

