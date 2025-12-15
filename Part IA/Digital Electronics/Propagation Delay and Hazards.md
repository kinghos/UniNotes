---
tags:
  - combinatorialCircuits
---
Gate propagation delay is the cumulative delay owing to a number of gates in cascade can increase the time before the output of a combinational logic circuit becomes valid.
e.g. in the RCA the sum at the output needs to wait for the carry to ripple through, so the MSB will experience the greatest delay.
Hazards are also possible, where brief logic level changes can affect the output.

![[Static1Hazard.png]]

Here, $w$ briefly goes to 0 when it should stay at 1.

Hazards can be removed by drawing a K-map:
- 1 Hazards can be removed by adding a term that overlaps the essential terms
- 0 Hazards can be removed by drawing the complement of the output onto a K-map, then adding a term which overlaps the essential terms