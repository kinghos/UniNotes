#### Key feature of UNIX
- Separation of kernel from user space
	- Only essential features inside the OS
- Processes are the units of scheduling and protection
- All I/O looks like file operations
	- Everything is a file
#### Components of a Linux system
- Kernel
	- Maintains important abstractions of the operating system
	- Composed of independent modules that can be compiled, loaded and unloaded independently
	- Dynamic loading/unloading requires conflict resolution (making sure not accessing the same things)
- System libraries
	- Define standard functions apps use to interact with the kernel
- System utilities
	- Perform individual specialised management tasks (user mode)

#### Processes and threads
- Both are called tasks by Linux - threads are new processes that share its parent's address space
	- fork creates a task with an entirely new task context
	- clone creates a new task with its own identity, but sharing parent's data structures

![[LinuxProcesses.png]]

#### Completely Fair Scheduler
- Start by assuming every task out of N tasks should have 1/N of the CPU
- Adjust based on nice value from -20 to 19, smaller is higher priority giving higher weighting
- Actual length of time given a task is the target latency
- Minimum granularity is the minimum length of time for which a process will be scheduled
