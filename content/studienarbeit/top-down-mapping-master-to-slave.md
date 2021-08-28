---
title: Top-down mapping (master to slave)
date: "2020-08-09"
tags:
  - software/SOFA/mappings
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Mappings](mappings.md)

Mapping of a master states to the slave states
![unknown_filename.png](./_resources/Top-down_mapping_(master_to_slave).resources/unknown_filename.png)
![unknown_filename.1.png](./_resources/Top-down_mapping_(master_to_slave).resources/unknown_filename.1.png) with the Jacobian ![unknown_filename.2.png](./_resources/Top-down_mapping_(master_to_slave).resources/unknown_filename.2.png) (kinematic relation)
![unknown_filename.3.png](./_resources/Top-down_mapping_(master_to_slave).resources/unknown_filename.3.png)

Linear/nonlinear mappings

*   In linear mappings, J and J are the same
*   In nonlinear mappings, J is nonlinear w.r.t. x\_m, i.e. not a matrix

Surfaces

*   Surfaces embedded in deformable cells: J contains [barycentric coordinates](http://www.evernote.com/shard/s484/nl/217355218/047632d6-892f-4007-917a-b5d97be87350)
*   Surfaces attached to rigid bodies: each row of J encodes ![unknown_filename.4.png](./_resources/Top-down_mapping_(master_to_slave).resources/unknown_filename.4.png) for each vertex

