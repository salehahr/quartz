---
title: RANSAC
date: "2020-07-27"
tags:
  - localisation/landmarks
  - -sa/processed
---

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)

# Random Sampling Consensus

*   to extract lines from a laser scan
*   lines then used as landmarks
*   indoors: straight lines from walls
*   line landmarks are found by
    *   randomly taking a sample of laser readings (e.g. sample readings from 12deg to 22deg from within a range of 0 to 180deg)
    *   least squares approximation for line of best fit
    *   RANSAC then checks how many laser readings lie close to the best fit line
        *   initially, all readings are assumed to be unassociated to any lines
        *   if the num. of readings > threshold, then a line has been seen
        *   this threshold is the consensus

The [EKF](SLAM/extended-kalman-filter.md) implementation assumes that landmarks come in as single points with range and bearing \[r, b\] from the robots position

Translate a line to a fixed point:

*   Take a fixed point in the world coordinates
*   Calculate point on the line closest to the fixed point
*   Using the robot's position and the position of the FP on the line, a range and bearing can be calculated

Another possibility: EKF handles lines instead of just points

