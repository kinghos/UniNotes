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

#### Threads
- A thread represents an individual execution context
- Each thread has an associated Thread Control Block
- A scheduler determines which thread to run
	- Changing the running thread involves a context switch

#### Context switching
- Switching between processes means saving context of the current process, and restoring the context of the process being resumed
- No useful work is carried out while switching
- Varies in time depending on hardware support

#### Process states
![[ProcessStates.png]]
New: process is being created
Ready: process is ready to run and waiting for CPU
Running: process' instructions are being executed on the CPU
Waiting/Blocked: process has stopped executing and is waiting for an event to occur
Terminated: process has finished executing

#### Process creation
Most systems are hierarchical, forming a tree
- Resource sharing options:
	- Parent and children share all resouces
	- Subset of resources
	- No resources
- Memory initialisation options:
	-  Child starts with duplicate of the parent and then modifies it
	- Child explicitly has a program loaded into it
- Execution:
	- Parent and children execute concurrently
	- Parent waits until children terminate
On Unix:
- `fork` clones a child process from parent
- Then `execve` replaces child's memory space with a new program
- While the parent waits until the child exits

#### Process termination
1. Process performs an illegal operation
2. Parent terminates child
	- Child has exceeded allocated resources
	- Task assigned to child is no longer required
	- Cascading termination (parent is exiting)
3. Process executes last statement and asks the OS to delete it (exit
	- Parent waits and obtains status data from child
	- If parent didn't wait, process is a zombie
	- If parent terminated without waiting, process is an orphan
#### Inter-Process Communication
- All communications require some protocol with data transfer
	- in a commonly-understood format (syntax)
	- having mutually-agreed meaning (semantics)
	- taking place according to agreed rules (synchronisation)
- IPC basic requirement: access to shared memory on same host

#### Message passing vs shared memory
- Shared memory:
	- Communicating processes establish some part of memory both can access
	- Requires removing usual restriction that processes have memory protection
- Message passing
	- Processes send messages to each other mediated by the kernel
	- Requires support for processes to
		- name each other or a shared mailbox
		- send and receive synchronously or asynchronously (blocking vs non-blocking)
		- buffer messages to match rates if non-blocking
