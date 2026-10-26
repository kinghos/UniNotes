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