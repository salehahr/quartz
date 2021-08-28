---
title: Linear solvers
date: "2020-08-22"
tags:
  - -sa/processed
  - software/SOFA/simulation-algos
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Simulation algorithms in SOFA](simulation-algorithms-in-sofa.md)

Conjugate gradient
![unknown_filename.png](./_resources/Linear_solvers.resources/unknown_filename.png)
J: first-order mapping of a node to its parent
path(i): list of mappings from the independent DOFs to the node the force applies to

Computation using a visitor:
![unknown_filename.1.png](./_resources/Linear_solvers.resources/unknown_filename.1.png)

*   Top down visitor: propagates the given displacement, clears force vector
*   Bottom up visitor: accumulates forces, maps them up to the independent DOFs

Direct solvers

*   can be used as preconditioners of the conjugate gradient algorithm
*   can be used to solve [the equation system A\*dv=b](http://www.evernote.com/shard/s484/nl/217355218/e3d45207-3f91-4941-8a1d-0573043b4546)
*   implementations are based external libraries

