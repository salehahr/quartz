---
title: Scene graph in SOFA
date: "2020-07-15"
tags:
  - software/SOFA/data-types
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Data structure in SOFA](data-structure-in-sofa.md)
Backlinks: [SOFA Introduction](sofa-introduction.md)
See also: [Scene graph (general)](scene-graph-(general).md)

*   Pool of simulated objects and algorithms in a hierarchical data structure
*   Scenes can be built procedurally or read from XML files
*   Root node represents whole simulation
*   Graph is processed by using [visitors](visitors.md)

A scene graph node

*   Gathers components associated with the same DOFs/topology
*   Connections between non-sibling components require explicit references

Example:
![unknown_filename.png](./_resources/Scene_graph_in_SOFA.resources/unknown_filename.png)

*   The collision spheres of the rigid object are in a child contact node of their own, because
    *   they are not independent DOFs (separate from independent DOFs in [MechanicalState](http://www.evernote.com/shard/s484/nl/217355218/d4586073-9cf7-40f7-9750-a8736a94457f))
    *   they are of a different data type
*   Interactions between the rigid and deformable objects are handled by a shared component (ContactSpring) defined as a sibling node to both (coupling)
    *   Soft coupling using penalty forces
        *   Can be modelled by a constant interaction force (assumption) during each time step
        *   Compatible with all explicit time intergration schemes
    *   Hard coupling using penalty forces / constraint-based interaction via [Lagrange multipliers](http://www.evernote.com/shard/s484/nl/217355218/d3ac75ba-fe8e-4ef2-bc5f-2fe53d54d4c0)
        *   Stiff interaction forces
        *   Implicit integration necessary, for large time steps without any instabilities
*   Generally more efficient to process independent interaction groups using separate solvers

