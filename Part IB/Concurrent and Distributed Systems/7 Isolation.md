#### Strict isolation
- Strict isolation - guarantee we never experience lost updates, dirty reads, or unrepeatable reads
- Non-strict isolation - let transaction continue to execute despite potential problems (optimistic)
- Can be enforced with two-phase locking, timestamp ordering and optimistic concurrency control
#### Two-phase locking
- Associate a lock with every object
- Transactions proceed in two phases
	- Expanding phase: locks are acquired but none are released
	- Shrinking phase: locks are released, and no further are acquired
- Operations can occur in either phase, given that the right locks are held
- Problems:
	- Requires knowledge of which locks required
	- Risk of deadlock
	- Non-strict isolation: releasing locks during execution means others can access those objects
- Rollback - returning the world to a state before the transaction happened, implementing atomicity