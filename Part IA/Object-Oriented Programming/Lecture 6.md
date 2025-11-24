#### Garbage collection
- Deleting objects automatically
	- Can prevent memory leaks from the developer forgetting to free up memory manually
- Reference counting - keeping track of how many references point to a given object. If there are none, the programmer cannot access that object ever again so it can be deleted.
	- Starting at each stack reference, follow references of everything reachable, and mark each object found
	- Traverse all objects on the heap - if they are marked, unmark them. If they are not marked, queue them for deletion
- Java supports multiple GCs with different approaches:
	- Delete immediately (can be slow)
	- Delete next time
	- Don't delete
- The GC can decide to compact - rearrange the surviving objects in memory to reduce gaps. This requires updating references.

#### Heap division
- All objects are created in Eden
- If they survive a few GCs, they are promoted to Survivors
- If they survive a few more GCs, they are promoted to Tenured
- The GC runs frequently on Eden, less on Survivors and much less on Tenured.

#### Different GCs
- Serial GC - "stop-the-world" GC where the program stops executing while the GC runs
- Parallel GC - also "stop-the-world" but the collection runs on multiple threads
- Garbage first (G1) - modern default. GC monitors memory concurrently, doing as much as it can. Uses short stop-the-world events to do the deletions, creating regions in memory and prioritising based how much needs to be done.
- Epsilon GC - do nothing (no-op GC)
##### Destructor
- Method that runs when an object is destroyed
- Can be used to free up resources or memory used by the object.
- **Do not use `finalise()`**

#### Copying
- Shallow copying - copying reference
- Deep copying - clear individual copies
- Copy constructor - takes in an object of the same type and manually copies the data. Copies can be made as so
```java
Vehicle v = new Vehicle(5, 0.f, 5.f);
Vehicle vcopy = new Vehicle(v);
```
