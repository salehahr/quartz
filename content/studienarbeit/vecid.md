---
title: VecId
date: "2020-08-22"
tags:
  - software/SOFA
  - -sa/processed
---

Source: [SOFA extended documentation](SOFA extended documentation.md)
Parent: [ODE solvers](ODE solvers.md)

*   Uniquely identifies state vectors (which are scattered over all [MechanicalStates](MechanicalStates.md))
*   Mechanical operations (e.g. allocating a state vector, accumulating forces) are implemented using a specialised [visitor](visitor.md) parametrised on VecIds

