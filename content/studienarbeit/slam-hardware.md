---
title: SLAM hardware
date: "2020-07-27"
tags:
  - sensors
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)
See also: [Position acquisition (relative vs. absolute)](position-acquisition-(relative-vs.-absolute).md)

Source: [SLAM for Dummies](slam-for-dummies.md)

1.  Robot parameters to consider
    *   Ease of use
    *   [Odometry](http://www.evernote.com/shard/s484/nl/217355218/d6e4227d-18b0-4633-9967-b72012e0cd6b) performance:  how well the robot can estimate its own position, just from the rotation of the wheels
        *   Max errors: 2cm per meter moved, 2deg per 45deg turned
        *   Bad odometry --> bad estimation of current position --> hard to implement SLAM
2.  [Range measurement device options](http://www.evernote.com/shard/s484/nl/217355218/8fa864a3-e043-d560-9722-9f1edeff4046)

Source: [Wikipedia Lokalisierung](wikipedia-lokalisierung.md)
Categories of sensors for localisation

*   Measuring own movement \[rel\]
    *   [Odometry](odometry.md) sensors
    *   Compass
*   [Measuring distance to landmarks](measuring-distance-to-landmarks.md) \[abs\]
*   [Measuring absolute POSE](http://www.evernote.com/shard/s484/nl/217355218/33574306-95c8-4e36-8a73-c12c8daab639) \[abs\]

