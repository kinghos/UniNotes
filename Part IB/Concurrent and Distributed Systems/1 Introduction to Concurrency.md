#### Threads and processes
- Processes are instances of programs in execution
- Threads are entities managed by the scheduler
	- Represents an individual execution context
	- A thread control block holds saved context
- Threads run in the address spaces of their processes
- Context switches save state of one thread and restores the state of another

#### Concurrency with a single CPU
- Process/OS concurrency
	- Process X runs for a while (until it blocks or is interrupted)
	- OS runs for a while
	- Process X resumes where it left off
- Inter-process concurrency
	- Process X runs for a while, then OS; then Process Y; then OS, then Process Z, etc.
- Intra-process concurrency
	- Process X has multiple threads X1, X2, etc.
	- X1 runs for a while, then X3, then X1, then 