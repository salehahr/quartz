---
title: Mesh geometry
date: "2020-07-15"
tags:
  - software/SOFA/meshing
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)
Parent: [Data structure in SOFA](data-structure-in-sofa.md)
See also: [Mesh topology](mesh-topology.md)

Mesh geometry: location of vertices in space

Meshes

*   k-simplices (triangles)
*   k-cubes (quads)

\--> decomposition into k-cells

*   1-cell: edges
*   2-cells: triangles, quads
*   3-cells: tetrahedron, hexahedron

Mesh data:

*   containers, similar to STL std::vector classes
*   there are as many data structures for mesh data as [topological elements](topological-elements.md),
    e.g. vertices, edges, triangles, quads, tetras, hexas
    

e.g. in spring-mass models: edge container -- stores spring stiffness, damping value, ith element for ith edge

