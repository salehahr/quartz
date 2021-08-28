---
title: Models in SOFA
date: "2020-07-15"
tags:
  - software/SOFA/models
  - -sa/processed
---

Source:  [SOFA extended documentation](sofa-extended-documentation.md)
Backlinks: [SOFA Introduction](sofa-introduction.md)

A simulation object can have several models

*   Each model is 'predestined' for a certain task
*   Each model is independent of the other
*   Synchronisation of models: via a [mapping](mappings.md) mechanism

Three typical models for a physical object

*   [Internal mechanical model](http://www.evernote.com/shard/s484/nl/217355218/ca7f5186-b72e-49f3-a775-84a7bf394f30?title=Internal%20model/Solid%20mechanics)
*   [Collision model](http://www.evernote.com/shard/s484/nl/217355218/3d43d987-12c2-40e5-bf8e-6754c868ea4d?title=Collision%20model)
*   [Visual model](visual-model.md)

![unknown_filename.png](./_resources/Models_in_SOFA.resources/unknown_filename.png)

One of the models acts as the master

*   typically the internal model
*   imposes its displacements to slaves using [mappings](mappings.md) (synchronisation of the models)

