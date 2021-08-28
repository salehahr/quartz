---
title: Data structure in SOFA
date: "2020-07-15"
tags:
  - software/SOFA
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)

Three different solutions for three relevant levels \[of organisation of simulation data\].

1.  [Scenegraph](http://www.evernote.com/shard/s484/nl/217355218/bf18694a-5cea-4dbe-8ba2-95b6c187a636?title=Scene%20in%20SOFA) ( directed acyclic graphs)
    s. also: [Visitors](visitors.md)
    
2.  Component attributes
    *   Component params stored using Data<...> containers
    *   e.g. list of particle indices Data<vector<unsigned>>
    *   Engines
        *   Create connections between Data instances, for synchronisation of values
        *   Compute a value from several others (input/output processor)
        *   Are only used to apply straightforward relations between model parameters
        *   State update algorithms are implemented using [visitors](http://www.evernote.com/shard/s484/nl/217355218/8e1b1539-2194-4c70-b3b5-c3d4328fa151)
3.  [Mesh geometry](mesh-geometry.md) and [mesh-topology](mesh-topology.md)

