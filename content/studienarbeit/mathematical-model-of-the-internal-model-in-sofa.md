---
title: Mathematical model of the internal model in SOFA
date: "2020-08-09"
tags:
  - software/SOFA/models
  - -sa/processed
---

Source:  [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Internal model](internal-model.md)
Backlinks: [ODE solvers](ode-solvers.md), [constraint-solvers](constraint-solvers.md)

Dynamic/quasi-static system of particles (nodes)
Independent DOFs: node coordinates, governed by 
![unknown_filename.png](./_resources/Mathematical_model_of_the_internal_model_in_SOFA.resources/unknown_filename.png)

*   f: different force functions, e.g. volume, surface and external forces)
*   M: mass matrix
*   P: constraints (projection matrix)
*   each operator corresponds to a simulation component

