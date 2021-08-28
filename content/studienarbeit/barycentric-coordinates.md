---
title: Barycentric coordinates
date: "2020-08-09"
tags:
  - software/SOFA/data-types
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Baclinks:  [Top-down mapping (master to slave)](top-down mapping (master to slave).md), [lamarca-2019-defslam](lamarca-2019-defslam.md)

*   Barycentre: centre of mass
*   A coordinate system, in which the location of point of a [simplex](simplex.md) (line, triangle, tetrahedron, etc) is specified as the centre of mass of the masses placed at its vertices

![unknown_filename.png](./_resources/Barycentric_coordinates.resources/unknown_filename.png)

|     |     |
| --- | --- |
| x\_i | vertices of a simplex |
| p   | a point in space |

*   The a\_i coefficients are the barycentric coordinates of p w.r.t. x\_1 ... x\_n
*   Non-unique, e.g. (ba1 ... ban) are also the barycentric coordinates of p, unless the coordinate values are restricted with a relation like ![unknown_filename.2.png](./_resources/Barycentric_coordinates.resources/unknown_filename.2.png) (absolute barycentric coordinates)
*   Negative coordinates lie outside of the simplex

Barycentric coordinates of the vertices: ![unknown_filename.1.png](./_resources/Barycentric_coordinates.resources/unknown_filename.1.png)

