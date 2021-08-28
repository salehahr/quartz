---
title: Initialising graph in SP3
date: "2020-09-23"
external_url: "http://github.com/SofaDefrost/plugin.SofaPython3.deprecated/pull/110"
tags:
  - -sa/processed
  - software/SOFA/SofaPython3
---

**Parent:** [SofaPython Index](sofapython-index.md)

<http://github.com/SofaDefrost/plugin.SofaPython3.deprecated/pull/110>

"Can you share an example of a scene and a component you have in mind ?
Because currently to summary the discussion during sofa-meeting the problem with init/bdwInit/reinit is that it that this is severely ill defined and we are considering to totally remove that from Sofa and use alternatives pattern among which:

*   have an onSimulationStart / onSimulationStop event to detect when the simulation is on or not
*   avoid using getContext() to fetch other components unless you store them in SingleLink.
*   systematic use of SingleLinks to exhibit inter component dependency
*   use ComponentState tracker to detect the change of state of one component from another
    [sofa-framework/sofa
- 1168](http://github.com/sofa-framework/sofa/pull/1168)
    
*   use the node notification API to detect node adding/removal."

