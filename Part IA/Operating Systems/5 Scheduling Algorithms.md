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
