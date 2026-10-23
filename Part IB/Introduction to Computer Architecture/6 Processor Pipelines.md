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