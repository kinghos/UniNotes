##### API formal specification
```
store    : string * string -> unit
retrieve : string -> string option
```

Value: often just a character string, but could be a number, date, or even a polygon in a spatial database.
Field: a place to hold a value, also known as an attribute or column in an RDB
(relational database).
Record: a sequence of fields, also known as a row or a tuple in an RDB.
Schema: the specification of how data is to be arranged, specifying table and field
names and types and some rules of consistency (eg. air pressure field
cannot be negative).
Key: the field or concatenation of fields normally used to locate a record.
Index: a derived structure providing quick means to find relevant records.
Query: a retrieve or lookup function, often requiring automated planning.
Update: a modification of the data, preserving consistency and often implemented
as a transaction.
Transaction: an atomic change of a set of fields with further ACID properties.

Interfaces can be used as a bridge between applications and implementations. Implementations can be changed without affecting applications and vice versa

A DBMS is an interface between files on disk and the user or applications.

Big data - too big to fit in primary store
In-core - it all fits in

Consistency:
- Value range check - verifying if a number is within valid bounds
- Foreign key referential integrity - verifying if the foreign key provides a valid entry in its original table
- Atomicity - no field can have more than one value stored in it
- Entity integrity - verifying that any fields that must be filled are filled

**C**reate
**R**ead
**U**pdate
**D**elete

##### Why distribute data?
- Scalability - too large for a single machine
- Fault tolerance - failure does not mean the whole system goes down
- Lower latency - data can be more geographically spread out, meaning more users are closer to servers
##### Challenges with distributed databases
- Consistency, availability and partition tolerance must be maintained
- Impossible to maintain with current technology
