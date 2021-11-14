---
title: Key frames in loop closure detection
date: "2020-08-03"
tags:
  - localisation/keyframes
  - -sa/processed
---

**Source**: [cometlabs](bibliography/cometlabs.md)

Most common method to get candidate key frames: use a place recognition approach

*   approach based on vocab tree
*   feature descriptors of candidate key frames are quantised
    *   one colour in image below corresponds to one feature descriptor/'vocabulary'
    *   each point is a 'word' that belongs to a vocabulary
    *   the words can then be counted and put into a frequency histogram
    *   the histogram is used to compare similarity of images
    *   I think similar images then get filtered out, so we get key frames

![kf-loop-closure](/_img/kf-loop-closure.png)
