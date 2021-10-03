---
title: SLAM hardware
date: "2020-07-27"
tags:
  - sensors
  - -sa/processed
  - -published
---

**Parent**: [SLAM index](SLAM/slam_index.md)  
**See also**: [Position acquisition (relative vs. absolute)](sensors/position-acquisition.md)

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

1.  Robot parameters to consider
    *   Ease of use
    *   [Odometry](definitions/odometry.md) performance:  how well the robot can estimate its own position, just from the rotation of the wheels
        *   Max errors: 2cm per meter moved, 2deg per 45deg turned
        *   Bad odometry --> bad estimation of current position --> hard to implement SLAM
2.  [Range measurement device options](sensors/sensors-absolute.md)
