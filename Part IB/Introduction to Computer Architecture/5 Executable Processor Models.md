#### RISC-V Instruction Types
- Instruction function encoded in the opcode, funct3, funct7
- Source and destination registers in the same place

- R-type instructions
	- Register-to-register operations
	- Arithmetic operations: `ADD, SUB`
	- Logical operations: `XOR, OR, AND`
	- Shifts: `SLL, SRL, SRA`
	- Comparisons: `SLT, SLTU`
- I-type instructions
	- Shift immediate - `shamt` = shift amount
	- Arithmetic/shift instructions - one operand is a constant provided by a 12-bit sign extended immediate
		- No funct7 field
	- Load instructions:
		- `LW` - load 32 bit word
		- `LB & LH` load byte/half word sign extended
		- `LBU & LHU` load byte/half word unsigned
- S-type store instructions
	- `SB, SH, SW` - store byte, half-word, word
- B-type branch instructions
	- `BEQ, BNE, BLT, BGE, BLTU & BGEU`
- U-type for forming large constants
	- LUI - load upper immediate
	- AUIPC - add upper immediate to PC for far jumps
- Pseudo assembler instructions e.g. `JAL` that aim to make code more human-readable

#### Instruction execution
- Fetch
- Decode
	- Opcode determines either instruction to be performed
	- or class of instruction to be performed
- Execute
	- Values fed into ALU
	- Opcode selects the function
- Branch
- Memory access
- Writeback