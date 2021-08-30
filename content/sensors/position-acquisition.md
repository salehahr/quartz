---
title: Position acquisition (relative vs. absolute)
date: "2020-07-30"
tags:
  - sensors
  - -sa/processed
  - -published
---

**See also**: [SLAM hardware](sensors/slam-hardware.md)

**Source**: [Cometlabs](cometlabs.md)

![unknown_filename.png](studienarbeit/_resources/Position_acquisition_(relative_vs._absolute).resources/unknown_filename.png)

*   relative (interoceptive sensors)
    *   [odometry](definitions/odometry.md)
*   absolute (exteroceptive sensors)
    *   can be used alongside relative measurement sensors in order to correct odometry drift
    *   s. [major sensor types in SLAM (absolute measurements)](sensors/sensors-absolute.md) incl. [visual sensors](sensors/visual-sensors-for-localisation.md)
    *   Beacons
        *   direct measurement instead of integrating, therefore error in position does not grow unbounded
        *   e.g. laser ranger finders, wifi (collect signal strength across field), GPS (bad for indoors)
            *   Lidar, Ultra Wide Band (UWB), Wireless Fidelity, etc \[[Wu](bibliography/wu-2018.md)\]
            *   Compared to these, cameras are flexible and low-cost \[[Wu](bibliography/wu-2018.md)\] (are also passive sensors) \[[Cometlabs](bibliography/cometlabs.md)\]

