---
title: Precision recall curve
date: "2020-08-03"
tags:
  - -sa/processed
  - SLAM/loop-detection
---

Parent: [Loop closure detection](loop-closure-detection.md)
Source: [cometlabs](http://www.evernote.com/shard/s484/nl/217355218/1a11af29-6862-53e6-3b33-4608a7c87c15?title=What%20You%20Need%20to%20Know%20About%20SLAM)

*   used to better quantify the performance (balance between false positives and false negatives in [loop closure detection](loop-closure-detection.md))
*   highlights tradeoff between precision and recall
    *   precision (absence of false positives) [ ] but may lead to the appearance of false negatives
    *   recall (prediction power)
*   e.g. tweaking to improve recall
    *   increases sensitivity to similarities in the image
    *   thus increases possibility of false positives

![unknown_filename.png](./_resources/Precision_recall_curve.resources/unknown_filename.png)

