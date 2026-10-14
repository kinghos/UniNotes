#### Hardware foundations for atomicity
- On a simple single processor, the crudest way is to disable interrupts
	- Not suitable for multi-processor or DMA systems
- Alternatively, use a new ISA primitive for protection against parallel access to memory from another CPU

#### Atomic Compare and Swap (CAS)
- Instruction operands: memory address, prior and new values
	- If prior value matches in-memory value, new value is stored
	- Otherwise, instruction fails

#### Load Linked-Store Conditional
- Used in RISC systems
	- Load value from memory location with LL
	- Manipulate value in register
	- SC attempts to write back to same address and indicates success/fail
	- SC fails if memory neighbourhood modified since LL
	- Software checks SC value and typically loops on failure
	- Optimistic concurrency
- Doesn't lock up whole memory system while one core does one atomic operation

#### Fairness and Livelock in [[Finite State Machines]]
- A live state is one that can be returned to infinitely often in the future
- A dead(lock) state has no successors, machine stops if it is entered
- Startup states are those before live behaviour
- Bad states lead away from live states
- Livelock can be defined as when non-fair states are forced to loop - not deadlocked but no useful progress can be made