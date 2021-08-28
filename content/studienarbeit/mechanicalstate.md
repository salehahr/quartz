---
title: MechanicalState
date: "2020-08-09"
tags:
  - software/SOFA/simulation-components
  - -sa/processed
  - to-do/missing-link
---

Source: [SOFA extended documentation](SOFA extended documentation.md)
Parents: [Components of the internal model](Components of the internal model.md), [Internal model as a scene graph in SOFA](Internal model as a scene graph in SOFA.md)
Backlinks: [VecId](VecId.md), [Scene graph in SOFA](Scene graph in SOFA.md), [Mesh topology](Mesh topology.md)

*   Contains state vectors of each mesh node
    *   Coordinates x
    *   Velocities v
    *   Net force f
*   n nodes: n entries of the state vector
*   Each entry has the same size of the node type (3 for 3D particles)
*   Nodes of different types belong to different MechanicalStates
    *   the other MechanicalStates are attached to other scene graph nodes
    *   they might be connected with one another using interaction forces

