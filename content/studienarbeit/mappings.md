---
title: Mappings
date: "2020-07-15"
tags:
  - software/SOFA/mappings
  - -sa/processed
---

Source: [SOFA extended documentation](SOFA extended documentation.md)
Backlinks: [Models in SOFA](models-in-sofa.md), [Visual model](visual-model.md)

Enforces consistency between the many model representations of an object, by propagating information (such as positions, velocities, forces) in a top-down and bottom-up approach. 

![unknown_filename.png](./_resources/Mappings.resources/unknown_filename.png)
**Figure**: Mappings between liver and grasper models

*   Master model imposes its displacements to the slave models ([top-down mapping](top-down mapping.md))
*   Slaves, depending on model type, can also pass information (e.g. forces) back to the master (bottom-up)
*   A mapped model can be master of another model
*   Also used to connect generalised coordinates (e.g. joint angles) to world-space geometry

