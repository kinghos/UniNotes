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
- ACID principles