---
tags:
  - sequentialCircuits
---
#### Counters
A counter is a clocked sequential circuit that goes through a predetermined sequence of states. An n-bit binary counter has n FFs and $2^n$ states which are passed through in the order $$
0, 1, 2, \dots 2^n-1, 0, 1,\dots
$$
Can be used for:
- Counting
- Producing delays of a particular duration
- Sequences for control logic in a processor
- Divide by m counter
Two types: [[Ripple Counters|ripple]] and [[Synchronous Counters|synchronous]] counters. Ripple counters should be avoided.