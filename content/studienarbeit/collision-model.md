---
title: Collision model
date: "2020-07-15"
tags:
  - software/SOFA/models
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Models in SOFA](models-in-sofa.md)

Primitives coming into contact — we need

*   collision detection
*   collision response

Collision detection approaches:

*   Distances between pairs of geometric primitives
*   Points in distance fields
*   Distances between colliding meshes using ray-tracing
*   Intersection volume using images

Collision model

*   Similar to internal model
*   Topology/geometry is different (geometry specially for contact model), can be stored in a data structure dedicated to collision detection
    e.g. TriangleModel: computes collision detection on triangular mesh surfaces
    
*   Has best trade-off between precision and speed in collision detection, compared to the [internal model](internal-model.md)
*   When the contact models collide, pairs of contact points are created, each point a slave of a contact model.

Time take for collision detection depends on collision mesh

*   If too long, set collision mesh to be coarser
*   If precision required, detailed collision mesh

