---
title: Basic python script in Sofa
date: "2020-07-15"
tags:
  - software/SOFA
  - software/python
  - -sa/processed
---

Parent: [SofaPython Index](sofapython-index.md)

Imports
import Sofa

General functions

*   createGraph(self, root)
*   reset()
*   onKeyPressed()
*   ...

Required in every script:
createScene(rootNode)

Create a child from a node
node.createChild('Name')

Add an object component to the node:
node.createObject(type in string, kwargs\*\*)

