---
title: RGB-D cameras
date: "2020-07-30"
tags:
  - sensors/cameras
  - -sa/processed
---

Source: [Cometlabs What You Need to Know About SLAM](cometlabs what you-need-to-know-about-slam.md)
Backlinks: [Visual sensors for localisation](visual sensors-for-localisation.md), [stereo-cameras](stereo-cameras.md)

*   Provide depth information directly
*   Employed by most of the SLAM systems
*   Generate 3D images through structured light or time of flight technology
    *   Structured light
        *   camera projects a known pattern onto objects
        *   Perceives deformation of pattern by an infrared camera
        *   This lets depth and surface information of the objects be calculated
    *   Time of flight
        *   ToF of a light signal between camera and objects is measured --> from this, depth is obtained
*   Structured light sensors are sensitive to illumination -- not applicable in direct sunlight

Limitations of RGB-D cameras

*   Range data for semi-transparent or highly reflective surfaces are not reliable
*   Limited effective range
