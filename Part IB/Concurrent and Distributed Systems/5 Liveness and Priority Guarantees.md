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

#### Livelock
- Less easy to detect