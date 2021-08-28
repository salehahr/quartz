---
title: ORB descriptor
date: "2020-12-08"
tags:
  - -sa/processed
  - vision
  - discussion/2020/2020-12
---

Source: <http://medium.com/data-breach/introduction-to-orb-oriented-fast-and-rotated-brief-4220e8ec40cf>
**Backlinks**: [Descriptors in feature detection/extraction](descriptors-in-feature-detection_extraction.md)

*   Oriented FAST and Rotated BRIEF, developed 2011
*   Was developed as an alternative to SIFT and SURF, and ended up being better/faster than both
*   Build on
    *   [FAST keypoint detector](fast-keypoint-detector.md)
    *   BRIEF descriptor

ORB using FAST, but with (partial) scale invariance

*   Use a multiscale image pyramid
*   Each level of the pyramid is the same image, but scaled at different resolutions (reduced size as you go higher up)
    ![unknown_filename.png](./_resources/ORB_descriptor.resources/unknown_filename.png)
    
*   Once the pyramid is computed, FAST is used to detect keypoints 

ORB detection

*   Compute scale pyramid
*   Use FAST to detect keypoints using the scale pyramid
*   An orientation is assigned to each keypoint (left/right facing)
    *   orientation depends on how the intensity changes around the keypoint
    *   intensity detection: intensity centroid

Brief (binary robust independent elementary feature)

*   Converts all keypoints into a binary feature vector, in order to be able to represent an object with this vector
*   Binary feature vector = binary feature descriptor
*   Each keypoint is assigned a feature vector (128 to 512 bit-string)
    ![unknown_filename.1.png](./_resources/ORB_descriptor.resources/unknown_filename.1.png)
    

How it works

*   Image smoothing (Gaussian blur) to reduce descriptor's sensitivity to high-frequency noise
*   For one bit within the feature vector, perform a binary test:
    *   select a random pair of pixels in a neighbourhood (patch) around the keypoint
        *   p1 drawn from a Gaussian distribution centred around the KP, std = sigma
        *   p2 drawn from a Gaussian distribution centred around p1, std = 2sigma
    *   If p1 brighter than p2, bit is set to 1, else 0
*   If 128-bit vector, this process is repeated 128 times, with 128 random pairs

![unknown_filename.4.png](./_resources/ORB_descriptor.resources/unknown_filename.4.png)
tau: binary test
p: patch
p(x): intensity at x

Resulting binary vector of one feature (one keypoint) using n binary tests
![unknown_filename.5.png](./_resources/ORB_descriptor.resources/unknown_filename.5.png)

Drawbacks
BRIEF isn't invariant to rotation --> rBRIEF (rotation-aware BRIEF)

rBRIEF
For one feature with n binary tests we have the matrix S
![unknown_filename.2.png](./_resources/ORB_descriptor.resources/unknown_filename.2.png)

ORB steers BRIEF according to the keypoint orientation, via
![unknown_filename.3.png](./_resources/ORB_descriptor.resources/unknown_filename.3.png)
With theta = patch orientation, Rtheta = rotation matrix

Resulting rBRIEF feature vector
![unknown_filename.6.png](./_resources/ORB_descriptor.resources/unknown_filename.6.png)

