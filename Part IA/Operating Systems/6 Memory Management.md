- The CPU can only access registers and main memory directly.
- Multiple levels of cache attempt to hide main memory latency (L1, L2, L3)
- Memory unit only sees a stream of address + read request or address + data + write request
#### Hardware address protection
- Base and limit registers define the logical address space
- CPU must check user-mode memory access to ensure it is in that range
#### Address binding
- Programs on disk are brought into memory to create running processes
- Address binding happens at three different points:
	- Compile time - if memory location known absolute code can be generated, requires recompilation if base location changes
	- Load time - need to generate relocatable code if memory location is not known at compile time
	- Execution time - binding delayed until run time if the process can be moved during its execution from one memory segment to another
- Bindings map one address space to another - requires hardware support
- 