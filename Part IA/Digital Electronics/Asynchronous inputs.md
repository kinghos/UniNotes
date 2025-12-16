---
tags:
  - sequentialCircuits
---
Inputs can be taken independently of any clock or enable inputs, usually:
- Reset/Clear - force Q to 0
- Preset/Set - force Q to 1
These can be used to force a synchronous circuit into a known state, e.g. at start up.

- Setup time: the minimum duration that the data must be stable at the input before the clock edge
- Hold time: the minimum duration that the data must remain stable on the FF input after the clock edge
![[DelayTimingFlipFlop.png]]