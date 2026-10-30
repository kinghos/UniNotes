#### Instruction Set Architectures
- An ISA is the repertoire of instructions that the processor can perform
- Examples include x86-64 (in CISC style), and ARM (RISC)
- Most important interface in a computer system
- Large cost to port and tune ISA-dependent parts of a modern software stack
- Large cost to recompile
- Closed-source software - no source code, so can't recompile
- Most of the costs for a new chip is developing software for it
- Most are proprietary for historical reasons

#### RISC philosophy
- [[3 Eight Great Ideas|Make the common case fast]]
- Orthogonal instruction set design
	- General purpose registers
	- All arithmetic operations use the same operands
- Simple instruction decode
	- Fixed-length instructions
- Modular
	- Standard extensions

#### Features
- Integer registers `x0...x32`
	- `x0` is always 0