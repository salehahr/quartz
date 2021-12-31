---
title: nonlinear-control-flow
date: 2021-12-30
tags:
  - embedded
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

# General considerations for non-linear control flow
* Mostly relevant for time-critical code, such as interrupt processing
* Loop unrolling can be performed to reduce the nonlinearity of the control flow and thus reduce loop overhead

## Loop overhead
* Additional instructions (comparisons, branching)
* The jumps/branching introduces execution delaysx

## The instruction pipeline
![](/embedded/_img/instruction-pipeline.png)
* Each row is an instruction
* In the pipeline, the processor works on multiple instructions at a given clock cycle --> increased throughput
* In case of branching, already partially executed instructions need to be discarded
	* e.g. the second row is a branch instruction
	* upon execution of the branch instruction, the decode and fetch operations for the two consecutive instructions have already been carried out
	* these, however, now need to be discarded, due to the jump
	* the pipeline restarts at the new instruction that the branch instruction directs to