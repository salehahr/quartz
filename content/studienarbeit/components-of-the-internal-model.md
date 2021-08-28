---
title: Components of the internal model
date: "2020-08-09"
tags:
  - software/SOFA/simulation-components
  - -sa/processed
---

Source:  [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Internal model as a scene graph in SOFA](internal model as-a-scene-graph-in-sofa.md)

![Image.png](./_resources/Components_of_the_internal_model.resources/Image.png)

*   MeshLoader: topology, geometry
*   [MechanicalState](mechanicalstate.md)
*   TetrahedronSetTopologyContainer
    *   tetrahedral connectivity
    *   passed on to other components
*   [Forces](forces.md)
    
*   Mass
    *   DiagonalMass
    *   UniformMass: less accurate, but allows faster computation
*   FixedConstraint: P (cancels displacements)
*   EulerSolver: integration scheme

