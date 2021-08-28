---
title: Localisation
date: "2020-07-30"
external_url: https://de.wikipedia.org/wiki/Lokalisierung_(Robotik)
tags:
  - localisation
  - -sa/processed
---

Parent: [SLAM Index](SLAM Index.md)

Source: [Wikipedia Lokalisierung](Wikipedia Lokalisierung.md)
The positioning of an autonomous mobile robot relative to its environment

*   The position of a mobile robot is seldom known exactly
*   An unknown initial position / measurement uncertainties while moving
*   Becomes a SLAM problem when neither the position nor the map is known

Goal/Output: POSE

*   Due to uncertainties etc, it's good to have a POSE representation that also shows these uncertainties
*   e.g. probability densities, particle clouds

Approaches mostly fusion-based (odometry/sensors + landmarks)

*   Cross-bearing known landmarks
*   Template-matching current sensor measurements (auch Scan-Matching)
*   Probabilistic methods

Local and global localisation

*   Local
    *   current POSE in the environment is known
    *   correct the incremental odometry error that occurs every step
*   Global
    *   current POSE in the environment is unknown
    *   position errors aren't negligible
    *   error of the initial estimated position can be arbitrarily huge
    *   the robot has to determine its position first through finding significant landmarks, only then can a local localisation be carried out
*   [Kidnapped robot problem](https://www.evernote.com/shard/s484/nl/217355218/0bf37f21-1c54-6e11-7680-fefa5f5044df?title=Kidnapped%20robot%20problem) (check robustness)

