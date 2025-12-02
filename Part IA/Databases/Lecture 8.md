- Nodes have a type, a unique label, and properties
- Edges are directed between two nodes. They have a type, optional label, and properties
- Can collate by type to convert to rDBMS tables
	- The edges table is all-key
	- rDBMS is not ideal for enormous many to many relations
	- For OLAP a denormal representation would probably be used
	- Bipartite: two types of node, all edges go from one type to the other

#### Neo4j Data Entry
- Edges and nodes have `<primary name>:<type>` and then key/value properties
- All edges have a direction as stored
- Arc names must be unique

- An arc type essentially models an E-R binary relation
- Pattern matching on paths is supported
- Transitive closure is free

Idempotent - repeating has no effect