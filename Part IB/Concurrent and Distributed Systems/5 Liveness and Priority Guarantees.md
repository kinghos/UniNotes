#### Liveness properties
- We want to avoid deadlock (threads sleeping waiting for one another) and livelock (threads execute but make no progress)
- We also want to avoid starvation, fairness and minimality (no unnecessary waiting or signalling)

#### Deadlock
- Set of k threads go asleep and cannot wake up
- Can happen when two mutual exclusion locks are taken at the same time, e.g. thread holding X tries to hold Y, while thread that holds Y tries to hold X
- Four conditions:
	- Mutual exclusion
	- Hold-and-wait
	- No preemption (lock is held until released)
	- Circular wait
- Can be prevented by
	- Ensuring it never happens
		- Static prevention through code structure
		- Dynamic avoidance through cycle finding
	- Let it happen, but recover
	- Ignoring it
		- Used widely

#### Static prevention
- Mutual exclusion
	- Allowing access is unsafe, but MRSW locks are an option
- Hold-and-wait
	- Require all resources are requested simultaneously, deny request if any resource is not available now
- No preemption
	- Stealing a resource is generally unsafe
- Circular wait
	- Impose a partial order on resource acquisition
	- Requires programmer discipline

#### Deadlock dynamic avoidance
- Assume maximum possible resource allocation is known, and a process granted all its desired resources will complete, terminate and free its resources
- Track actual allocations, and only grant if guaranteed no deadlock even if all others take max resources.
- When deadlock is detected:
	- Kill something deadlocked
	- Resume from a checkpoint

#### Banker's Algorithm
- Have m distinct resources and n threads
- Vector V of currently available resources
- A, the resource allocation matrix, and R the request matrix
	- Element i,j of A is the number of objects of type j owned by i
	- Element i,j of R is the number of objects of type j further needed by i
- Successively mark rows in A for threads that are not part of a deadlocked set
- If we cannot mark all rows of A we have deadlock
- Mark all zero rows of A, as clearly these cannot be deadlocked
- Initialise a working vector W to V
	- This describes any free resources at the start, plus any resources released by a hypothesised sequence of threads freeing and terminating
- Select an unmarked row i of A (a thread who's request can be satisfied)
- Set `W = W = A[i]`, mark row i and repeat
- Terminate when no such row can be found, and any unmarked rows are in the deadlock set

#### Livelock
- Less easy to detect

