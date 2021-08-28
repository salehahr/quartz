---
title: Internal model as a scene graph in SOFA
date: "2020-08-09"
tags:
  - software/SOFA/models
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Internal model](internal-model.md)

Scene graph of the internal model

*   Consists of components which are connected to a common scenegraph node (root of the internal model)
*   Each component is responsible for a set of tasks
    Examples: solver, mass, constraints, ...
    
*   Each component can query its parent node to get access to the its sibling components such as [MechanicalState](http://www.evernote.com/shard/s484/nl/217355218/d4586073-9cf7-40f7-9750-a8736a94457f), topology
*   Components are independent of one another — modularity

[Components of the internal model](components-of-the-internal-model.md)
![unknown_filename.png](./_resources/Internal_model_as_a_scene_graph_in_SOFA.resources/unknown_filename.png)

