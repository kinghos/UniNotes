

### Computer Architecture


#### Simple computer



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