---
title: ODE solvers
date: "2020-08-22"
tags:
  - -sa/processed
  - software/SOFA/simulation-algos
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Simulation algorithms in SOFA](simulation-algorithms-in-sofa.md)
Backlinks: [Linear solvers](linear-solvers.md), [constraint-solvers](constraint-solvers.md)

*   implement animation algorithms at each time step
*   integrate and compute positions and velocities one time step ahead
*   uses state vectors (e.g. for position or force), denoted by symbolic identificators called [VecId](vecid.md)s
*   this allows the solver to be implemented completely independently of the physical model

![unknown_filename.png](./_resources/ODE_solvers.resources/unknown_filename.png)
Each statement in the example above is implemented using a visitor

*   Explicit solvers: variants of the above
*   Implicit solvers (consider the derivative somewhere)
    *   Solution of the equation system
        ![unknown_filename.1.png](./_resources/ODE_solvers.resources/unknown_filename.1.png)
        (also solvable using [direct solvers](direct-solvers.md))
        *   M - mass matrix
        *   K = ![unknown_filename.2.png](./_resources/ODE_solvers.resources/unknown_filename.2.png) stiffness matrix
        *   B = damping matrix
        *   if beta and gamma = 0 --> explicit
    *   Use a [projection matrix](projection-matrix.md) to apply simple displacement constraints
        ![unknown_filename.3.png](./_resources/ODE_solvers.resources/unknown_filename.3.png)
        
    *   [Lagrange multipliers](http://www.evernote.com/shard/s484/nl/217355218/d3ac75ba-fe8e-4ef2-bc5f-2fe53d54d4c0) are used for more complex constraints
        ![unknown_filename.4.png](./_resources/ODE_solvers.resources/unknown_filename.4.png)
        
    *   More stable than explicit schemes for stiff forces or large time steps

