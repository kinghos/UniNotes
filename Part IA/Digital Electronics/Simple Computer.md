---
tags:
  - processorArchitecture
---
Address supplied from PC to memory yields instruction to be executed.
The instruction is presented to the rest of the datapath. PC is incremented.
Including Mux enables PC to be changed to an arbitrary value to permit branching.
More of the datapath can be added - control unit and registers
![[MemoryAccess.png]]
Mux can access registers in memory.

##### Branching
If a branch instruction is decoded and the ALU zero flag (flag indicating if the ALU output is 0) is set, then the AND gate output (the branch Mux control input) will become 1 and the input to the PC will now come from the jump adder.