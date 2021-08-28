---
title: Monocular cameras
date: "2020-07-30"
tags:
  - sensors/cameras
  - -sa/processed
---

Source: [Cometlabs What You Need to Know About SLAM](cometlabs what you-need-to-know-about-slam.md)
Backlinks: [Visual sensors for localisation](visual-sensors-for-localisation.md)

*   \+ Simpler hardware implementation
*   \+ Smaller and cheapter systems
*   \- need complexer algos and software because of lack of direct depth information from a 2D image

How is the shape of the map generated?

*   Integrating measurements in the chain of frames over time
    *   Use triangulation method
    *   As well as camera motion, if camera isn't stationary
*   Depths of points are not observed directly (s. [monocular depth perception](monocular-depth-perception.md))
    *   est point and camera positions are related to the real positions by a common unknown scale factor (scale availability issue)
    *   requires camera movement when depth is to be calculated

Adressing the scale availability issue

*   Stereo cameras
*   Introduce a real metric scale (via external scale reference: pre-specified object or sth w/ known size that can be recognised during mapping)

