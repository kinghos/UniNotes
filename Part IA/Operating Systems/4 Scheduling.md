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

#### Scheduling Criteria
- Turnaround time, minimising time for any process to complete
- Waiting time, minimising the time a process sits in the Ready queue
- Response time, minimising the time to start responding
- CPU utilisation, maximising the time the CPU is actively in use
- Throughput, maximising the rate at which processes complete execution
Typically, we want to maximise utilisation and throughput, and minimise turnaround, waiting and response time.

#### Multiple processor scheduling
- Asymmetric multiprocessing
	- Only one processor accesses the system data structures
	- Alleviates the need for data sharing
- Symmetric multiprocessing (SMP) - currently the most common
	- Each processor is self-scheduling
	- All processes can be in a single ready queue, or each processes has its own private ready queue
- Processor affinity when a process has affinity for which processor it runs
	- Soft affinity indicates preference
	- Hard affinity indicates constraint
	- Variations including processor sets
#### Non-Uniform Memory Access
- Affects CPU scheduling as it means different CPUs have faster or slower access to parts of memory
- Memory placement affects affinity
- Costs of switching to a different CPU could be much higher than without NUMA
#### Load balancing
- Load balancing attempts to keep workload evenly distributed
	- Push migration has a periodic task check load on each CPU and push tasks off overloaded CPUs onto other CPUs
	- Pull migration has idle CPUs pull waiting tasks off busy CPUs
- Multicore - multiple CPU cores on the same chip, increasing speed and efficiency
- Hyperthreading - increasing number of threads per core so that one thread can make progress while another stalls
- Virtualisation challenges OS scheduler as hypervisor and guests are all scheduling against each other.