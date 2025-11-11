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
Isolation - The intermediate state of a transaction is invisible to other transactions. As a result, tra