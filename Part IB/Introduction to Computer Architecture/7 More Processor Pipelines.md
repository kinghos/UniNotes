Use [[D Flip-Flop|D Flip-Flops]] in-between each pipeline stage to control the flow of data.
#### Load-to-use hazard
```
lw     t2, 0(t1)
add    t3, t3, t2
```
- This has a load-to-use dependency on register t2
- Forwarding can be used by sending the register value through a mux ahead in the pipeline
- Will always occur - best to do general compiler optimisation of load hoisting, performing load instructions early on
#### Execute-to-execute hazard
- Use another forwarding path
- Two paths handles all arithmetic operations
#### Branching 
- Pipeline will have to be flushed
- Dynamic prediction possible by using a buffer that stores recent branch conditions
#### Exceptions and interrupts
- Unexpected events require changing flow of control
- Save PC of offending/interrupted instruction (SEPC)
- Save indication of the problem (SCAUSE)
- Jump to handler pointed to by (STVEC)
- Precise/restartable exceptions (harder to handle) require flushing the instruction and previous instructions, then rerunning the instruction
- Imprecise exceptions - pipeline just has to flush
