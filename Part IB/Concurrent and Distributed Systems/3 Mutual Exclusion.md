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
#### N-resource allocation
- Suppose there are N instances of a resource
- Initialise a semaphore `sem`, initialised to N
	- Any job wanting a resource uses `wait`
	- After N jobs get a printer, the next sleeps.
	- To release a resource, `signal`

#### Producer-consumer problem
- Shared buffer `B[]` with N slots
- Producer thread wants to
	- Produce an item
	- If there's room, insert it into next slot
	- Otherwise, wait until there is room
- Consumer thread wants to:
	- If there's anything in buffer, remove an item (consume it)
	- Otherwise, wait until there is something
- Solved by having two semaphores: `spaces` and `items`
	- Producer and consumer will wait on spaces, and signal on items
	- The resource is a slot in the buffer
	- `spaces` allocates empty slots (for producer)
	- `items` allocates full slots (for consumer)
	- This solution does not have explicit mutual exclusion - many threads might break this
		- Add one more semaphore, `guard`, that is where the buffer logic is handled

#### Invariants
- An important goal of locking is to avoid exposing inconsistent intermediate states to other threads
- Invariants hold as mutex is acquired
- Invariants may be violated while mutex is held
- Invariants must be restored before mutex is released
- e.g. deletion from a doubly linked list
	- Invariant: an entry is in the list, or not in the list
	- Updating pointers around a deleted node is fine so long as the lock isn't released in-between pointer updated