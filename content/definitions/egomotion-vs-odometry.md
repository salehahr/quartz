---
title: Egomotion (vs odometry)
date: "2020-08-25"
external_url: "http://en.wiktionary.org/wiki/egomotion"
tags:
  - -definitions
  - -sa/processed
  - localisation/odometry
---

See also: [Odometry](definitions/odometry.md)

**Source**: <http://en.wiktionary.org/wiki/egomotion>  
The three-dimensional movement of a camera relative to its environment

***

**Source**: <http://answers.ros.org/question/296686/what-is-the-differences-between-ego-motion-and-odometry/>

*   Generally used interchangeably with odometry
*   Possible difference:
    *   Egomotion is more about the estimation of twist (lin, rotational velocities)
    *   Odometry is more about the estimation of path

## Examples

*   Wheel odometry: path estimation via time-integration of an estimated twist
*   Visual odometry/Scan matching: direct estimation of pose without time-integration

