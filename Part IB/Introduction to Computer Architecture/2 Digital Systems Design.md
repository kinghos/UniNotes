#### Digital Circuit Design
- [[D Flip-Flop|D Flip-Flops]] are used to store state and control the flow of information
- Time is considered "discrete" in clocked circuits
- Consider [[Setup and Hold Conditions|setup and hold times]]
- Clock trees
	- Use buffers to propagate the clock to every part of the chip so the clock edge appears at the same time everywhere
	- Not very power efficient - can use up to a third of the power of the chip

#### Hardware Description Languages
- e.g. SystemVerilog
- Alternative to designing a state machine, then making a [[Karnaugh Maps|Karnaugh map]], and deriving boolean algebra and a circuit diagram
- A simple 2-bit counter in SystemVerilog would be
```verilog
module counter2bit(
		input clk
		input go
		output logic [1:0] n);
	always ff @(posedge clk)
		if(go) n <= n+1;
endmodule
```
- Implementation
	- SystemVerilog can be passed into a simulation, or
	- Synthesised, and then placed and routed
	- This then generates a low level laid out design, from which
		- You can run a timing analysis (resulting in a pass/fail)
		- You can run a gate-level simulation

#### Synthesis
- 