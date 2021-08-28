---
title: Constraint solvers
date: "2020-08-22"
tags:
  - -sa/processed
  - software/SOFA/simulation-algos
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Simulation algorithms in SOFA](simulation-algorithms-in-sofa.md)
Backlinks: [Scene graph in SOFA](scene-graph-in-sofa.md)

*   Lagrange multipliers to handle complex constraints (which aren't handle-able using [projection matrices](projection-matrices.md))
*   May be combined with explicit or implicit integration

![unknown_filename.png](./_resources/Constraint_solvers.resources/unknown_filename.png)
phi: bilateral interaction laws (attachments, sliding joints, ...)
psi: unilateral interaction laws (contact, friction, ...)

The Lagrange multipliers add force terms to the equation [A\*dv = b](http://www.evernote.com/shard/s484/nl/217355218/e3d45207-3f91-4941-8a1d-0573043b4546)
![unknown_filename.1.png](./_resources/Constraint_solvers.resources/unknown_filename.1.png)
![unknown_filename.2.png](./_resources/Constraint_solvers.resources/unknown_filename.2.png)

The H matrices are stored in the MechanicalState of each node.

Solving the constraints

1.  Free motion (lam = 0; A\*dv = b)
    *   Solve interacting objects independently
    *   Obtained: free motion ![unknown_filename.3.png](./_resources/Constraint_solvers.resources/unknown_filename.3.png) for each object (here: 2 objects)
    *   Integrate to get: ![unknown_filename.4.png](./_resources/Constraint_solvers.resources/unknown_filename.4.png)
2.  Constraint solving
    ![unknown_filename.5.png](./_resources/Constraint_solvers.resources/unknown_filename.5.png)
    with ![unknown_filename.6.png](./_resources/Constraint_solvers.resources/unknown_filename.6.png)
    *   Together with the interaction laws above, this poses a mixed complementarity problem
    *   Compute the value of lambda
3.  Corrective motion
    ![unknown_filename.7.png](./_resources/Constraint_solvers.resources/unknown_filename.7.png)
    

Compliance computation

*   Compliance: inv(A), changes at every time step (in a nonlinear model)
*   Computation of the compliance is time-consuming for RT applications
*   There are strategies to improve the speed of the algorithm, implemented in ConstraintCorrections
*   ConstraintCorrections: computed ![unknown_filename.8.png](./_resources/Constraint_solvers.resources/unknown_filename.8.png)

