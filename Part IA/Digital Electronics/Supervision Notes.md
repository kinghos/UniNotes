- Moore machines can have outputs labelled akin to Mealy machines, but with the slash inside the state, e.g. "001 / 0" and "0010" / 1 means 0010 is the state that outputs 1.
- The output of a Moore machine can only change when the clock ticks - the output is a function of the state
- The output of a Mealy machine is different, the state controls which function is used to determine the outputs from the inputs.
- Using a Mealy machine can reduce the amount of states needed, i.e. less FFs.
- Gray's code can simply be done with 2 FFs
- Carry select -> run both 0 and 1 carry outs into the next stage, then choose which path to take based on the actual carry out once calculated

Only one thing crossed out in a cell in an implication table is enough to disregard the cell.
You can use formulas without deriving them
Consider if the circuit is not grounded - it must be a full loop for current to flow.

Architecture specifies the quantity and size of registers - do not conflate with architectural state. Architecture is essentially a blueprint of a chip. Microarchitecture is an implementation of said architecture.
Caveats of pipelining
- branching

Consider the bounce of switches.

