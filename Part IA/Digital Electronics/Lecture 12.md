

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
![[MemoryAccess.png]]
Mux can access registers in memory.

##### Branching
If a branch instruction is decoded and the ALU zero flag (flag indicating if the ALU output is 0) is set, then the AND gate output (the branch Mux control input) will become 1 and the input to the PC will now come from the jump adder.


#### Multicycle processor
Single cycle processors have 3 main weaknesses:
- Clock cycle needs to be long enough to cope with slowest instruction
- Needs 3 adders, 1 in ALU and 2 in the PC logic
- Separate instruction and data memory
In a multicycle processor:
- Instructions are broken into multiple shorter, faster steps
- More complex instructions take more steps than simple ones so simple instructions execute faster than complex ones.
- Only one adder is needed i.e. it can be reused
- Only one memory is required since instruction is fetched in the first step and data may be read or written in later steps.
![[MulticycleProcessor.png]]
However, the design is more complex and more registers are needed. The controller is now a FSM rather than combinational logic since it has to produce different outputs on different steps.
#### Execution time
$\frac{\text{Time}}{\text{Program}}=\text{instruction count} \times \text{average time to execute instruction}$
$\frac{\text{Time}}{\text{Instruction}}=\text{clocks per instruction} \times \text{clock period}$

#### Pipelining
The single cycle processor is subdivided into 5 pipelined stages
![[Pipelining.png]]
Hazards present an issue:
- Data hazard - when an instruction tries to read a register that has not yet been written back
- Control hazard - when the decision of what instruction to fetch has not been made by the time the fetch takes place