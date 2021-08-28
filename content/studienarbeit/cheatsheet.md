---
title: Cheatsheet
date: "2020-09-30"
tags:
  - -sa/processed
  - software/SOFA/SofaPython3
---

Parent: [SofaPython Index](SofaPython Index.md)

**Imports/Plugins**
import SofaRuntime
from SofaRuntime import PluginRepository
PluginRepository.addFirstPath(SOFA\_INSTALL\_DIR)
SofaRuntime.importPlugin("SofaComponentAll")
SofaRuntime.importPlugin("SofaPython3")
SofaRuntime.importPlugin("SofaOpenglVisual")

From root
root = Sofa.Core.Node("root")
c = root.createObject("MechanicalObject", name="t", position=\[
                              \[0, 0, 0\], \[1, 1, 1\], \[2, 2, 2\]\])
c1 = root.addObject("MechanicalObject", name="c1")

From nonroot
nonroot\_node = Sofa.Core.Node("a\_node")
nonroot\_node.addObject("MechanicalObject", name="c1")
.addData("d", value="coucou", type="string")
.addData("data1", value="@/c1.d") # @ is root

Add data from relative/absolute paths
c4.addData('data1', value="@/n1/c3.data1") # absolute path (chained)
c4.addData('data2', value="@../n1/c3.data1") # relative path (down, chained)
c1.addData('data4', value="@n1/c3.data2") # relative (up, chained)

Add data from parent
        c1 = root.addObject("MechanicalObject", name="c1")
        c1.addData("d", value="coucou", type="string")
        c1.addData("d2", value="@c1.d")

Get
root.getClassName()
c.getTemplateName()
c,getDataFields()

**GUI**
import Sofa.Gui

Sofa.Simulation.init(root)
Sofa.Gui.GUIManager.Init("simple\_scene", "qglviewer") # alt: 'qt' instead of qglviewer
Sofa.Gui.GUIManager.createGUI(root)
Sofa.Gui.GUIManager.MainLoop(root)
Sofa.Gui.GUIManager.closeGUI()

