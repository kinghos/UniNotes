Transistors only dissipate power when switching.
Tolerance to noise is quantified in terms of the noise margin

![[NoiseMargin.png]]

### Computer Architecture
A computer architecture is defined by its instruction set and architectural state e.g. for a MIPS processor, the architectural state comprised the program counter and the 32 registers
Based on its current architectural state, the processor executes a particular instruction with a particular set of data to yield a new architectural state

#### Microarchitecture
The microarchitecture is the specific arrangement of registers, ALUs, finite state machines (FSMs), memories and other logic building blocks (e.g., multiplexers) needed to implement an architecture

A microarchitecture can usually be divided into 2 interacting parts:
- Datapath - operates on worlds of data and contains structures like memories, registers, ALUs and multiplexers.
- Instruction Decoder/Control Unit - gets instructions from the datapath and tells it how to execute that instruction.

#### Simple computer
Address supplied from PC to memory yields instruction to be executed.
The instruction is presented to the rest of the datapath. PC is incremented.
Including Mux enables PC to be changed to an arbitrary value to permit branching.
More of the datapath can be added - control unit and registers