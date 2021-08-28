---
title: Position acquisition (relative vs. absolute)
date: "2020-07-30"
tags:
  - sensors
  - -sa/processed
---

Parent: [SLAM Index](slam-index.md)
See also: [SLAM hardware](slam-hardware.md)

Source: [Cometlabs What You Need to Know About SLAM](cometlabs what you-need-to-know-about-slam.md)
![unknown_filename.png](./_resources/Position_acquisition_(relative_vs._absolute).resources/unknown_filename.png)

*   relative (interoceptive sensors)
    *   [odometry](http://www.evernote.com/shard/s484/nl/217355218/d6e4227d-18b0-4633-9967-b72012e0cd6b)
*   absolute (exteroceptive sensors)
    *   can be used alongside relative measurement sensors in order to correct odometry drift
    *   s. [major sensor types in SLAM (absolute measurements)](major sensor types in-slam-(absolute-measurements).md) incl. [visual-sensors](visual-sensors.md)
    *   Beacons
        *   direct measurement instead of integrating, therefore error in position does not grow unbounded
        *   e.g. laser ranger finders, wifi (collect signal strength across field), GPS (bad for indoors)
            *   Lidar, Ultra Wide Band (UWB), Wireless Fidelity, etc \[[Wu](wu.md)\]
            *   Compared to these, cameras are flexible and low-cost \[[Wu](wu.md)\] (are also passive sensors) \[[comet](http://blog.cometlabs.io/teaching-robots-presence-what-you-need-to-know-about-slam-9bf0ca037553)\]

