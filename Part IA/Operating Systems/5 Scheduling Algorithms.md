#### First-Come First-Served
- Schedule depends purely on the order in which processes arrive
- Simplest possible scheduling algorithm
#### Convoy effect
Shortest-run jobs run behind longest-run jobs, increasing average waiting time
#### Shortest Job First
- Associate length of next CPU burst with each process
- SJF gives the least possible waiting time for a given set of processes

#### Shortest Remaining Time First
- Preemptive version of SJF
- Not optimal like SJF, as frequent context switching will lead to CPU thrashing

#### Predicting burst lengths
- Assume the next burst will not be too different from the previous
- Let $t_{n}$ be the measured length of the $n^{th}$ CPU burst
- Define $\tau_{n+1}$ to be the predicted length of the $(n+1)^{th}$ burst
$$\tau_{n+1}=\alpha t_{n}+\dots+(1-\alpha)^j \alpha t_{n-j}+\dots+(1-\alpha)^{n+{1}}\tau_{0}$$
For some constant $\tau_{0}$
$\alpha,(1-\alpha) \leq 1$
$\alpha \approx 1$ implies past history is irrelevant, and vice versa

#### Round Robin
- Each process is given a quantum (time-slice) of CPU time
- Once this elapses, the process is appended to the ready queue
- The quantum needs to be balanced between being too large or being too small, to prevent FCFS or context switching

#### Priority scheduling
- Each process has an integer priority, schedule highest priority (lowest number) process
- Starvation can occur if low priority processes never execute
- Solve by making dynamic, e.g. ageing increasing priority starting from a static base as time passes without process being scheduled

#### Multilevel Feedback Queues
- Partition the ready queue into many queues for different types of process
- Each process is permanently assigned a given queue
- Each queue has its own scheduling algorithm
- Scheduling must be done between the queues
	- Fixed priority
	- Time slices
- Processes can move between queues (example of ageing)
