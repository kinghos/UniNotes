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
