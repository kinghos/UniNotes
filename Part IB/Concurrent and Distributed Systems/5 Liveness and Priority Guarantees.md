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
- 