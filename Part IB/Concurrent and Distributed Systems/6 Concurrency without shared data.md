#### No shared data
- Have only one thread access any particular piece of data
- Other threads ask for operations to be done on their behalf
- Active object handles the changes
#### Message passing
- Dynamic invocations between threads can be seen as message passing
- Used to build RPC (remote procedure call)
	- Include name of operation to invoke, alongside parameters
	- Receiver checks operation and invokes code
	- Returns the return value as another message
	- Asynchronous process - waiting for reply is optional
- Avoids race conditions
#### Composite operations
- Build systems that act on multiple distinct objects
- Transactions - operations that will happen atomically
- [[Part IA/Databases/Lecture 5#ACID|ACID]] principles
#### Serialisability
- Execute transactions serially
- Operations are serialisable if they can be executed for both threads without conflicting, e.g. all of T1's operations on any object happen after T2's updates
- Conflict serialisability is satisfied for a schedule S if and only iff
	- It contains the same set of operations as some serial schedule T
	- All conflicting operations are ordered the same way as in T