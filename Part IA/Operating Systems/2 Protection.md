#### Evolution of OSes
- Open shop - one machine, one CPU, one program, all programming is machine code
- Batch systems - tape drives run a set of programs in a batch
- Multiprogramming - one machine, one CPU, one running program but many loaded programs
- Timesharing - switching jobs so frequently that users have the illusion many jobs are running simultaneously

Single tasking OS
- Command interpreter receives input from user
- Once finished, termination causes command interpreter stub to reload command interpreter
#### Dual-mode operation
- Allows OS to stop malicious or buggy code from doing bad things
- Use hardware - a mode bit - to distinguish at least two mods of operation
	- User mode when executing on behalf of a user
	- Kernel mode when executing on behalf of the OS
	- Some instructions designated as privileged, only executable in kernel mode
- Increasingly CPUs support multi-mode operations
- Often nested rings, further inside can do more.

#### Kernels
- The kernel sits between the hardware and the higher level application software - the kernel is more privileged
- Protection prevents applications from doing I/O
	- Unprivileged instruction to transition from user to kernel mode - usually called a trap or software interrupt

#### System calls
- Invoked by a trap with OS having vectors to handle
- Enforces the code run when mode switch occurs
- Prevents an application from switching to kernel mode and then just doing as it likes
- Provide a language agnostic standard interface to the OS services
- Usually accessed via a high-level API e.g. glibc
- Each system call is identified by a number that indexes a system call table
	- Invoked by putting the relevant number and parameters in the right place and trapping
	- Return status and any values made available to application in user space
	- Usually managed by a built-in runtime support library
- Three ways to pass parameters:
	- Load into registers
	- Place onto stack for the kernel to pop off
	- Place into a block of memory and put the block's address into a register
- Latter two are preferred, as registers are limited in number and size
#### Microkernels
- OS interfaces must be extremely stable, making it difficult to add new system calls or remove system calls
- Microkernels are an alternative, where by moving OS services into local, sometimes privileged servers, it increases modularity and extensibility
- Message passing is used to access servers, replacing trapping
- Many common OSes blur the distinction between kernel and microkernel, e.g. Linux

#### Virtualisation
Allows operating systems to be run alongside each other above a hypervisor
- Type 1 runs directly on the host hardware, possibly using hardware extensions
- Type 2 runs above a full OS kernel
- Can support cross-architecture using emulation (slow) or interpretation (if not natively compiled)
VMs encapsulate an entire system and boot the VM over a hypervisor
Containers expose functionality in the kernel so that each container acts as a separate entity even though they all share the same kernel functionality, e.g. Docker

#### Security
- Defence of the system against internal and external attacks
- Systems generally distinguish among users, to determine who can do what
	- User IDs are used to associate files and processors with users to determine what they can access
	- Group identifiers allow sets of users to be defined and controls managed
- Privilege escalation allows users to gain more rights

#### Principle of least privilege
- Objects should be given just enough privileges to perform their tasks
	- Applies to software and hardware
- Properly set permissions can limit damage if object has a bug and gets abused
	- Can be static (during life of system/process)
	- Can be dynamic (changed by process as needed) by domain switching, privilege escalation
- Compartmentalisation
	- Process of protecting each individual concept regarding access to data
- Covert channels leak information using side-effects
	- Hardware include wire tapping or EM radiation
	- Software include page fault statistics or input dependent timing
- Domain of protection - domain limits access to (and operations on) objects
	- A domain is a set of access rights, where an access right is an object corresponding to its set of valid operations that can be performed on that object

#### Access matrix 
- A matrix of domains against objects.
- Shows which operations can be performed on what objects
- Separation of policy from mechanism
- Can be represented in two ways:
	- By object, as an Access Control List
	- By domain, storing as Capabilities
##### ACLs
- Each column is an access list for one object
- Often used in storage system
- If stored on disk, check performed