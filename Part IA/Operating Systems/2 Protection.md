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
- Microkernels are