#### Transaction Processing
A transaction on a database is a series of queries and changes that externally appear to be atomic.
Internal transactions - values are read, values are changed based on the values read
External transactions - some values changed or other side effects are external to the DBMS. The DBMS cannot help make these atomic. Instead the system designers have to think carefully about undoing them.