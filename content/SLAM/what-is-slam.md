---
title: What is SLAM?
date: "2020-07-30"
tags:
  - SLAM
  - -sa/processed
  - -published
---

**Source**: [Scaradozzi 2018](studienarbeit/scaradozzi-2018.md)

Process which allows a mobile robot to

*   construct a map of its environment (assumed to be unknown)
*   compute its location using the map simultaneously

* * * 

**Source**: [Lamarca 2020](studienarbeit/lamarca-2020.md)

*   Goal is to locate a sensor in an unknown map/environment, which is simultaneously being reconstructed.
*   Typically used in exploratory trajectories (new or changing environments)

* * *

**Source**: [Wikipedia SLAM](wikipedia-slam.md)

Simultaneous localization and mapping (SLAM)

*   computational problem
*   construct/update a map of an unknown environment
*   simultaneously keep track of an agent's location within it

* * *

**Source**: [SLAM for Dummies](bibliography/riisgaard-slam-for-dummies.md)  

**Goal**: to use the environment to update robot position

*   robot odometry is often erroneous, therefore we cannot rely directly on odometry
*   in this specific example, laser scans are used to correct the position of the robot in an EKF implementation
    *   extract features from environment
    *   update position estimate based on the features
    *   re-observe when the robot moves around

* * *

**Source**: [Cometlabs](cometlabs.md)

*   Getting precise measurements based on known maps --> ok
*   Building a map of the environment --> ok

But solving both simultaneously is harder!

With a map (i.e. prior knowledge of environment, e.g. via storage of known landmarks in a database)

*   mobile robot can perform a set of tasks like path planning
*   error in estimating the state is limited
*   robot can 'reset' localisation error by revisiting known areas

Without a map

*   [Dead-reckoning](definitions/dead-reckoning.md) (odometry) would quickly drift over time
*   [Data association](SLAM/data-association.md) becomes much more difficult
    *   Unknown mapping b/w existing landmarks and observations

* * *

**Source**: [Grisetti 2011 - Tutorial graph-based SLAM](studienarbeit/grisetti-2011.md)

Another way of defining SLAM: "learning maps under pose uncertainty"

