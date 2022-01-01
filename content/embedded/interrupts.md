---
title: interrupts
date: 2022-01-01
tags:
  - embedded
  - -definitions
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

* Allows processor to abruptly change flow of control
* Upon interrupting:
	* A hardware in the processor changes the value of the `PC` (program counter) register
	* The interrupt service routine (ISR) is executed
	* After the ISR ends, the processor resumes execution of the original code