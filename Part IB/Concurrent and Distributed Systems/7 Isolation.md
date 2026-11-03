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
#### Rollback
- Returning the world to a state before the transaction happened, implementing atomicity
- Can be implemented by:
	- Undoing, by recording a log of operations. However, not all operations are undoable, e.g. set
	- Copying, by making a copy of an object before its first modification which is restored to.
#### Timestamp ordering
- Assign a timestamp to a transaction as it begins
- Each object records the timestamp of the last transaction to successfully access it.
- A transaction can only access an object if its timestamp is after the last transaction on that object
- Deadlock
- Allows more concurrency than 2PL
- Can be augmented to distinguish reads and writes
- Needs a rollback mechanism
- Does not provide strict isolation - can lead to repeated cascading aborts
- Good for distributed systems
#### Optimistic concurrency control
- Assume conflicts are rare
- Execute transaction on a shadow/copy of the data
- Before committing, check if everything is OK, if so update, otherwise retry
- OK means shadows were mutually consistent, and no one else has committed later changes to any object we are hoping to update
- Key idea is to look for a serialisable order that accepts the transaction

#### Implementing OCC
- Tag all objects with version/generation numbers
- When taking shadow copies, take note of version number
- Committing a transaction submits the edited shadows to a validator
- Read validation
	- Must ensure that all versions of data read by T were valid at some particular time t - the tentative start time for T
- Serialisability validation
	- Must ensure that there are no conflicts with any committed transactions which have a later start time
- Optimality matching
	- For a batch, must choose a serialisation that commits as many as possible
- Not suited for a high conflict rate