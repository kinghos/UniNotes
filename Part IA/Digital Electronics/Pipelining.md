---
tags:
  - processorArchitecture
---
The single cycle processor is subdivided into 5 pipelined stages
![[Pipelining.png]]
Hazards present an issue:
- Data hazard - when an instruction tries to read a register that has not yet been written back
- Control hazard - when the decision of what instruction to fetch has not been made by the time the fetch takes place