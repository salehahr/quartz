---
title: Odometry
date: "2020-08-22"
tags:
  - sensors
  - -definitions
  - -sa/processed
  - localisation/odometry
---

Parent: [SLAM Index](SLAM Index.md), [IMU index](IMU index.md)
Baclinks: [Position acquisition](Position acquisition.md), [SLAM hardware](SLAM hardware.md), [Prediction model](Prediction model.md)
See also: [Egomotion (vs odometry)](Egomotion (vs odometry).md)

Source: [Wikipedia Visual odometry](Wikipedia Visual odometry.md)

*   Data can be generated from actuator movements, e.g. rotary encoders that measure motor shaft rotations
*   This data can be used to estimate changes in position over time
*   Usually has precision problems, e.g. due to wheels slipping and sliding, bumpy surfaces
*   The errors are integrated over time and therefore get worse

Source: [cometlabs](cometlabs.md)

*   Acceleration is obtained: integrate to get velocity, displacement \[estimates\]
*   However, as the estimates drift over time and get integrated, this leads to increased errors
*   Subject to
    *   non-systematic errors e.g. human intervention
    *   systematic errors, e.g. due to imperfections in robots' structure
*   Examples:
    *   wheel odometry, via encoders -- error source: wheel slippage
    *   [IMU](IMU.md): measures lin and rotational acceleration, error sources: extensive drift, sensitive to bumpy terrain

Source: [SLAM for Dummies](SLAM for Dummies.md)

*   Provides approximate position of the robot as measured by its relative movement
*   Acts as an initial guess for the EKF

Problem: getting timing right between odometry data and laser data, so as not to compare outdated data to newer data
Solution: extrapolate the data, easiest to extrapolate odometry data (since the controls are known)
