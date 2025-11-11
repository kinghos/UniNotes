#### Transaction Processing
A transaction on a database is a series of queries and changes that externally appear to be atomic.
Internal transactions - values are read, values are changed based on the values read
External transactions - some values changed or other side effects are external to the DBMS. The DBMS cannot help make these atomic. Instead the system designers have to think carefully about undoing them.

##### Transaction client flow
- Transaction "start" and "commit" calls bracket the body.
- The body consists of any number of queries and updates in any order
- The client may choose to abort at any time, all updates are then undone by the DBMS
- In some systems, the updates or commit may also abort and the client is forced to restart the transaction
- Support concurrent transactions

### ACID
Atomicity - All changes to data are performed as if they are a single operation. All changes are performed, or none are
Consistency - Every transaction applied to a consistent database leaves it in a consistent state, e.g. obeying properties
Isolation - The intermediate state of a transaction is invisible to other transactions. As a result, transactions that run concurrently appear to be serialised.
Durability - After a transaction successfully completes, changes to data persist and are not undone, even in the event of a system failure.

Many NoSQL systems weaken ACID properties. The result is BASE transactions:
BA - Basically available
S - Soft state
E - Eventual consistency

#### Data locking
A lock is special software or a hardware primitive that provides mutual exclusion. A resource can be locked for exclusive access by one concurrent application which must unlock it again after use. Other contending applications have to wait, which delays their completion.
- Locks are acquired and released by transactions
- Locks can be placed along a spectrum of granularity from very coarse-grained (whole DB) to very fine-grained (single data value)
- How locks are used to implement ACID is not part of any DBMS API, but rather implemented by the vendor.
- If transactions lock large amounts of data, or lock frequently used data, fewer concurrent updates can be supported, degrading throughput.

#### Data Redundancy
Data is redundant if it can be deleted and then reconstructed from the data remaining in the database.
Problems:
- Data in different places can disagree
- Correct transactions may have to acquire many locks
