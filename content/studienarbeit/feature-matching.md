---
title: Feature matching
date: "2020-12-08"
tags:
  - to-do/to-clarify
  - -sa/processed
  - vision
---

**Source**: <http://medium.com/data-breach/introduction-to-feature-detection-and-matching-65e27179885d>
**Backlinks**: [Bag of words](bag-of-words.md), [sparse/feature-based-vslam](sparse_feature-based-vslam.md)

For matching between images, i.e. to establish a relationship ('correspondence') between two images of the same scene or object.

**Basic algorithm**

*   Find/detect a set of identifying ('distinctive') keypoints from all images to be matched
*   Define a search region around each keypoint
*   Extract and normalise the region content
*   Compute a local descriptor from the normalised region
*   Match local descriptors between the images

Performance of matching methods depend on

*   characteristic of the interest points themselves
*   choice of the feature detectors / image descriptors
    *   e.g. corner detector for man-made surfaces, blob detector for more organic sturctures
    *   the detector/descriptor should be able to handle image degradation

**Some algorithms**

*   Brute-Force Matcher
*   FLANN (Fast Lirbary for Approximate Nearest Neighbours) Matcher

