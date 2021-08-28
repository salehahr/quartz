---
title: Internal model
date: "2020-07-15"
tags:
  - software/SOFA/models
  - -sa/processed
---

Source:  [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Models in SOFA](models-in-sofa.md)

For the internal deformable mechanics

*   Contains the independent DOFs, mass and physical laws
*   Mechanical behaviour modelled e.g. by FEM
*   Geometry of this model is optimised for the computation of internal forces
    *   usually by using a reduced number of well-shaped tetrahedra
    *   this increases speed and stability
    *   however not accurate enough for [collision detection](http://www.evernote.com/shard/s484/nl/217355218/3d43d987-12c2-40e5-bf8e-6754c868ea4d)
    *   nor is it smooth enough for [visuals](http://www.evernote.com/shard/s484/nl/217355218/8446d918-bc51-46f5-822a-d8405da17ade)

|     |     |
| --- | --- |
| ![unknown_filename.png](./_resources/Internal_model.resources/unknown_filename.png) | *   Boxes: fixed nodes<br>*   Arrows: external forces |

[Mathematical model of the internal model in SOFA](mathematical model of-the-internal-model-in-sofa.md)
[Internal model as a scene graph in SOFA](internal model as-a-scene-graph-in-sofa.md)

