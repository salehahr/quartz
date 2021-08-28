---
title: Collision detection and response
date: "2020-08-22"
tags:
  - -sa/processed
  - software/SOFA/simulation-algos
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Simulation algorithms in SOFA](simulation-algorithms-in-sofa.md)

*   split into several phases
*   each phase is scheduled by a CollisionPipeline component
*   an object which can potentially collide is associated with a collision geometry
    *   returns pairs of colliding bounding volumes (broad phase component)
    *   returns pairs of geometric primitives + contact points (narrow phase component)
*   the returned pairs are passed to the contact manager
*   the contact manager creates contact interactions

... (skimmed)

