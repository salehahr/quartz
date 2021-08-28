---
title: Mesh topology
date: "2020-08-22"
tags:
  - software/SOFA/meshing
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Data structure in SOFA](data-structure-in-sofa.md)
See also: [Mesh geometry](mesh-geometry.md)

Mesh topology: how the vertices are connected to each other (using what element?)

Hierarrchy of mesh topology:
![unknown_filename.png](./_resources/Mesh_topology.resources/unknown_filename.png)

Topology objects consist of four functional members which creates/modifies/gets topology arrays/geometrical information:

*   Container
*   Modifier
*   Algorithms
*   Geometry

![unknown_filename.1.png](./_resources/Mesh_topology.resources/unknown_filename.1.png)

Topological mapping:

*   Define a new mesh topology from an existing one, using the same DOFs
*   e.g. for subsetting a set of nodes, edges, or to split quads into 2 triangles each
    *   these topologies are therefore assigned to the same [MechanicalState](http://www.evernote.com/shard/s484/nl/217355218/d4586073-9cf7-40f7-9750-a8736a94457f)

![unknown_filename.2.png](./_resources/Mesh_topology.resources/unknown_filename.2.png)

