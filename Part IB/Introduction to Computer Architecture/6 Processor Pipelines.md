#### Building a datapath
- Datapath - elements that process data and addresses in the CPU
- Branch instructions
	- Read register operands
	- Compare operands, in ALU
	- Calculate target address
		- Sign-extend displacement
		- Shift left 1 place
		- Add to PC value

#### Control path
- The signals that control the operations of blocks in the datapath
- Datapath is fixed, control path determines how each part of the datapath is used

#### Pipelines
- Example 5 stage pipeline:
	- IF - instruction fetch from memory
	- ID - instruction decode and register fetch
	- EX - execute operation or calculate address
	- MEM - memory access
	- WB - write back result to register

#### Hazards
- Situations that prevent starting the next instruction in the next cycle
- Structural hazards - a required resource is busy
	- Pipelined data paths require separate instruction/data memories, usually as different caches taken from one memory
- Data hazard - need to wait for previous instruction to complete its data read/write
	- Forwarding - use result when it is computing, without waiting for it to be stored in a register
	- This doesn't always fix stalls - you can't forward backwards!
	- Code scheduling - reorder code to avoid use of load result in next instruction, e.g. group all loads together so compiler does those in one pipeline step
- Control hazard - deciding on control action depends on previous instruction
	- Wait until branch outcome before fetching next instruction
	- Branch prediction