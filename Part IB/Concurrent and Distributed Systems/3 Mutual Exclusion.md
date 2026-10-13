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
