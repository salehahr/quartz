---
title: Modified Denavit-Hartenberg convention
date: "2021-05-24"
tags:
  - to-do/orphan
  - -sa/processed
  - math/kinematics
---

**Source**: Craig - Introduction to Robotics
**Backlinks**: [Kinematics primer](kinematics-primer.md)
Note: s. <http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.1083.6428&rep=rep1&type=pdf> for comparison (Lipkin)

**Link-frame attachment**

1.  Identify joint axes
2.  For joint axes i and i+1, identify the 
    *   common perpendicular + where it meets axis i, or
    *   point of intersection
        and let this be the link-frame origin
        
3.  Let Z\_i point along the i-th joint axis
4.  Let X\_i
    *   point along common perpendicular, or
    *   be normal to the plane containing the two axes
5.  Assign Y\_i (right hand coordinate system)
6.  Let CS0 match CS1 when the first joint variable is zero.
7.  Choose CS{N} (origin and direction of X\_N) such that as many parameters as possible become zero.

|     |     |
| --- | --- |
| **Link parameters**<br>![unknown_filename.png](./_resources/Modified_Denavit-Hartenberg_convention.resources/unknown_filename.png)<br><br>Note: does not result in a unique attachment of frames to links<br><br>![unknown_filename.2.png](./_resources/Modified_Denavit-Hartenberg_convention.resources/unknown_filename.2.png) | ![unknown_filename.1.png](./_resources/Modified_Denavit-Hartenberg_convention.resources/unknown_filename.1.png) |

**Examples**

|     |     |
| --- | --- |
| ![unknown_filename.4.png](./_resources/Modified_Denavit-Hartenberg_convention.resources/unknown_filename.4.png) | ![unknown_filename.3.png](./_resources/Modified_Denavit-Hartenberg_convention.resources/unknown_filename.3.png) |
| Spherical wrist (note: this doesn’t follow modified DH)<br>Source: [robotics.usc.edu/~aatrash/cs545/Lecture8.pdf](http://robotics.usc.edu/~aatrash/cs545/Lecture8.pdf)<br>![unknown_filename.6.png](./_resources/Modified_Denavit-Hartenberg_convention.resources/unknown_filename.6.png) | ![unknown_filename.5.png](./_resources/Modified_Denavit-Hartenberg_convention.resources/unknown_filename.5.png) |

