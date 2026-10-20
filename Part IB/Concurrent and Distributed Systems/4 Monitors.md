#### Multiple-Readers Single Writer
- Shared resource accessed by a set of threads
- Safe for many threads to read simultaneously but a writer must have exclusive access
```cpp
int nr = 0;
rSem = new Semaphore(1);
wSem = new Semaphore(1);
wait(wSem);
// perform update to data
signal
```