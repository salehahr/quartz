---
title: bonn-3D-cs
date: 2022-05-14
tags:
  - -resources/bibliography
---

**Source**: https://www.youtube.com/playlist?list=PLyWhIjKEKFn9pb7tVFmZObpp2KhReb5wP

**Author**: Wolfgang Förstner

## Motivation
* Integrating measurements from different viewpoints
* Observation of moving objects

## Notation
| Notation                                                    | Description                                                                         |
| ----------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| $\mathcal{R}$                                               | rotation transformation                                                             |
| $\mathbf{R}$                                                | rotation matrix                                                                     |
| $\mathcal{X} = \mathcal{X}(x, y) = \mathcal{X}(\mathbf{x})$ | 2D point given by the coordinates ($x, y$)                                          |
| $\mathbf{x}$                                                | coordinate vector                                                                   |
| $\mathbf{x}_2$                                              | coordinate vector with id 2                                                         |
| ${}^2 \mathbf{x}$                                           | coordinate vector in coordinate system 2                                            |
| ${}_2 \mathbf{T}^1$                                         | active transformation that transforms point 1 to point 2                            |
| ${}^w \mathbf{T}_b$                                         | passive transformation that transforms the point representation in CS $b$ to CS $w$ |

## Selected Contents
1. [Motions in the plane](math/motions-in-plane.md)
2. [Active vs. passive transformations](math/rotations/active-passive-or-alibi-alias-transformations.md)
3. [Global vs. local transformations](math/rotations/intrinsic-vs-extrinsic-rotations.md)