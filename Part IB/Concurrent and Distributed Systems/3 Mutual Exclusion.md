#### Semaphores
- Busy waiting remains inefficient
	- Wastes CPU cycles
	- Better to sleep until resources available
- Semaphores are variables initialised to an integer value (often 0)
- Supports two operations, `wait()` and `signal()`
- Implemented as an integer and a queue
```c
wait(sem) {
	if (sem > 0) {
		sem = sem - 1
	} else suspend caller & add thread to queue for sem
}

signal(sem) {
	if no threads are waiting {
		sem = sem + 1
	} else wake up some thread on queue
}
```
#### Inter-Processor Interrupts
- Mark thread as runnable
- Send an interrupt to the target CPU
- IPI handler runs thread scheduler, preempts running thread, triggers context switch.

#### Mutual exclusion with a semaphore
- Initialise semaphore to 1, `wait()` is lock, `signal()` is unlock
#### Condition synchronisation
- Initialise semaphore to 0, A proceeds only after B signals
