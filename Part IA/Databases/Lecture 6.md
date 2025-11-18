#### Semi structured data
For the example of a textbook, which has some structure in the form of chapters:
- Store in two parts
	- Keep the documents in its native form
	- Store the indexable features in relational tables
- NoSQL - store just once, and use something instead of SQL
	- Keep the document largely in native form
	- Develop database tools that can navigate semi structured data. These must return best-effort query answers, given that schema violations could be frequent.

Unstructured documents can be "shredded", i.e. broken down and given structure by a human curator or LLM. 

#### BASE
- BAse: Basically available: availability promoted over consistency. Any change in data made at one point is promulgated to all the different nodes
- Soft state: stored values may change without any application intervention owing to eventual consistency updates or network partition
- Eventual consistency: all readers through the system will eventually see the same state as each other.

#### Key/value store
- Values stored can be generalised from strings to blobs
- Many implementations are distributed, spreading the data randomly all over all participating machines as shards
- Opaqueness implies the DBMS knows nothing about what is stored - it would not mind if values were encrypted and it never saw the encryption keys
- Distribution provides redundancy and load balancing
- Implementations can range between ACID and BASE semantics

#### Serialising 
Serialising is converting a data structure into a series of bytes for transfer over a network or storing in a file.
- Main two formats used are JSON and XML
- Both contain tree-structured text with named nodes and hence are broadly similar
- XML can be unstructured, as all data can be in one large element.
- However XML documents may be associated with a schema

##### Schema rigorousness spectrum
1. A schema, named with a URL exists. The schema dictates precisely the element names and which elements may be allowed inside which others along with occurrence limits.
2. The schema is relaxed: e.g. the order of elements inside a parent element is unimportant
3. Other attributes or elements beyond those in the schema are also allowed
4. There is no schema at all

#### Document-oriented database systems
- A document oriented database stores data in the form of semi-structured objects. They are also known as aggregate-oriented databases
- Query of a distant database encounters a round-trip time
- Denormalised data is not directly semantically related to the key it is stored under
- A denormal DBMS enables us to rapidly pull much or all of the data likely to be needed using one key
- One or two fetches of denormal data should enable all sorts of fast, local operations in an application-specific way
#### Document query languages
- Query unstructured text
- Query tags e.g. picking out certain attributes from semi-structured parts of the document
#### Problems with NoSQL
- Key nesting can cause replication of data, which multiplies with any replication arising from the data being denormal
- It is "horizontally scalable" meaning it expands with more machines, not upgrading existing machines.