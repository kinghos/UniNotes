---
tags:
  - sequentialCircuits
---
Ripple counters are made by cascading together negative edge triggered T-type FFs in toggle mode. FFs are not clocked using the same clock, so they are not synchronous. Therefore outputs do not change at the same time, and propagation delay builds up. 

![[RippleCounterTiming.png]]Each subsequent counter output has half the frequency. This is why counters are often known as dividers.

Synchronous counter designs should always be preferred. All FF clock inputs are connected to the clock, so they all change at the same time. More complex combinational logic is needed to generate the appropriate FF inputs.