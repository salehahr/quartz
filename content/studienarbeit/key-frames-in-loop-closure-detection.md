---
title: Key frames in loop closure detection
date: "2020-08-03"
tags:
  - localisation/keyframes
  - -sa/processed
---

Source: [cometlabs](http://www.evernote.com/shard/s484/nl/217355218/1a11af29-6862-53e6-3b33-4608a7c87c15?title=What%20You%20Need%20to%20Know%20About%20SLAM)
Backlinks: [Loop closure detection](loop-closure-detection.md)

Most common method to get candidate key frames: use a place recognition approach

*   approach based on vocab tree
*   feature descriptors of candidate key frames are quantised
    *   one colour in image below corresponds to one feature descriptor/'vocabulary'
    *   each point is a 'word' that belongs to a vocabulary
    *   the words can then be counted and put into a frequency histogram
    *   the histogram is used to compare similarity of images
    *   I think similar images then get filtered out, so we get key frames

![unknown_filename.png](./_resources/Key_frames_in_loop_closure_detection.resources/unknown_filename.png)

