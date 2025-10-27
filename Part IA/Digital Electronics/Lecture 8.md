### Synchronous State Machines
- Finite state machine - a deterministic machine that produces outputs which depend on its internal state and external inputs
- States - The set of internal memorised values shown as circles on the state diagram
- Inputs - External stimuli, labelled as arcs on the state diagram
- Outputs - results from FSM

Two types of FSM - Moore and Mealy machines
- Outputs from Mealy machines depend upon the timing of the inputs
- Outputs from Moore machines come directly from clocked FFs so
	- They have guaranteed timing characteristics
	- They are glitch free
- Any Mealy machine can be converted to a Moore machine and vice versa, though their timing properties will be different.

#### Traffic light controller example
A traffic light has 4 states, so it could be represented with 2 FFs. However, 3 FFs means there will not be any need for combinational logic.
![[TrafficLightTransition.png]]
Here, R, A and G are the outputs of the FFs. Some states, e.g. 000, 011 are unused, and these can be ignored and treated as don't care conditions.
A K-map can be used to determine $D_R$. This ultimately gives $$
D_{R}=R\oplus A
$$
$D_A$ is clearly $\overline{A}$ and $D_{G}=R.A$
Now drawing the circuit:
![[Pasted image 20251027111951.png]]
##### Problems
- Check to see if the FSM can eventually reach a known state from any of the unused states
- If not, add logic for this e.g. adding unused states to the transition table
- Alternatively use Clear and Preset inputs to set a known state at power up
In this example, the FSM does self-start when powered on, as all unused states lead to used states.

State assignment is rarely obvious or straightforward. Algorithms exist for optimising assignment but are not suitable for manual execution.
If you have $m$ states, at least $\log_{2}m$ states are required to encode them.

Example: Divide by 5 counter which is high for 2 clock edges then low for 3 edges. Here, there are 5 states i.e. 3 FFs.
The FFs are connected together to form a shift register. The output from the final shift register in the chain is connected to the input of the first FF i.e. a continuous cycle. This needs 2 more FFs but is much more simple to wire.