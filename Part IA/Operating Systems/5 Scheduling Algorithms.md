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
