#### Processes vs Programs
- A program is static, on disk
- A process is dynamic, a program in execution
- Process is the unit of protection and resource allocation - multiple processes can be created from a single program
Processes contain:
- Text containing program code
- Data containing global variables
- Heap containing memory allocating during runtime
- One or more threads containing
	- Program counter
	- Stack for variables, parameters, addresses, etc.

#### Process Control Block
- Data structure representing a process containing:
	- Process ID
	- Current process state
	- CPU scheduling information
	- Memory-management information
	- Accounting information, e.g. CPU used, clock time elapsed
	- I/O status information
- Process context is the machine environment while the process is running
	- Program counter
	- CPU registers
