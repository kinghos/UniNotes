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