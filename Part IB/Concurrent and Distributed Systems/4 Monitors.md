#### Multiple-Readers Single Writer
- Shared resource accessed by a set of threads
- Safe for many threads to read simultaneously but a writer must have exclusive access
```cpp
int nr = 0; // num readers
rSem = new Semaphore(1); // protects access to nr
wSem = new Semaphore(1); // protects writes to data
turn = new Semaphore(1); // write is awaiting a turn

// writer thread
wait(turn);
wait(wSem);
// perform update to data
signal(turn);
signal(wSem);

// reader thread
wait(turn);
signal(turn);
wait(rSem);
nr = nr + 1;
if (nr == 1) { // first in
	wait(wSem);
}
signal(rSem);
// read data
wait(rSem);
nr = nr - 1;
if (nr == 0) { // last out
	signal(wSem);
}
signal(rSem);
```
- This ensures that the writer will acquire turn when it tries to enter, which prevents further readers from entering.

#### Monitors
- One thread can only ever be executing within the monitor
	- If a thread calls a monitor method, it will block if another thread is holding the monitor
	- Hence all methods within the monitor can proceed on the basis that mutual exclusion has been ensured
- `synchronised` keyword in Java
- Related methods are combined together (e.g. through a class) along with initialisation code, in a single construct
- Allow condition variables
	- Explicitly declared and managed by programmer
	- No integrated counter, not a stateful semaphore
	- `wait` - suspend thread and add it to the queue for CV, release monitor lock
	- `signal` - if any threads queued on CV, wake one thread
	- `broadcast` - wake all threads queued on CV