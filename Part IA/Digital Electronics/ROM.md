---
tags:
  - combinatorialCircuits
---
ROM is a data storage device that is:
- usually written into once
- read at will
- essentially a lookup table where a group of input lines specifies the address of locations holding words
e.g. if $n=4$, then ROM has $2^4=16$ possible locations. If $m=4$, then each location can store a 4-bit word. Therefore the total number of bits stored is $m\times2^n=64$.

ROM can be used to act as combinational logic. Storing the minterms in appropriate memory locations means no logic simplification is required and multiple Boolean expressions can be implemented. This is reasonable efficient if lots of minterms need to be generated.

However, ROM can be quite inefficient with only a few non-zero entries, as the number of minterms to be implemented is quite small.
