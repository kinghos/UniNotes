#### Queues
- Job queue: batch processes awaiting admission
- Ready queue: processes in main memory, ready and waiting to execute
- Wait queue: set of processes waiting for e.g. I/O or other processes
#### CPU I/O Burst Cycle
- Process execution interleaves CPU execution with waiting for I/O
- CPU burst distribution helps parameterise scheduling
- I/O bound - many short CPU bursts
- CPU-bound - many longer CPU bursts
#### Schedulers
- Short-term or CPU scheduler
	- Selects which process should be executed next
	- Often the only scheduler in a system
	- Invoked frequently so must be fast
- Long-term or job scheduler
	- Controls the degree of multiprogramming
	- Selects which processes should be brought into the ready queue
	- Invoked infrequently so may be slow
	- Strives for good process mix between CPU and I/O bound processes
#### Idling
If there is nothing to do:
- Busy wait in the scheduler: short-response times but ugly, inneficient
- Halt CPU until interrupted: save energy but increases latency
- Invent an idle process
	- Consumes resources and may slow interrupt response, but can do some housekeeping.
#### Dispatcher
The dispatcher gives control of the CPU to the selected process by:
- Switching context
- Switching to user mode
- Executing the user process from the selected location
Dispatch latency is the time it takes to complete this
#### When to enter the scheduler?
The decision can be made when:
1. a running process blocks
2. a running process terminates
3. a timer expires
4. a waiting process unblocks
For 1 and 2, the scheduler is non-preemptive, otherwise it is.

