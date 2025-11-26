Worst case complexity of a join $R\bowtie S$ is $|R|\times|S|$
Index - data structure created and maintained within a database system, reduces time needed to locate records
```sql
CREATE INDEX index_name on S(B)
DROP INDEX index_name
```

Indexes speed up reads but can slow down updates
SQL works on multisets - duplicates are important for aggregate functions


#### Null
NULL is a placeholder, not a value. 
It is not a member of any domain (type)
Three-valued logic is needed
$\bot$ represents "we don't know"
![[NullTable.png]]

However, null can lead to ambiguity, due to there being multiple possible interpretations:
- There is a value, but we don't know what it is
- No value is applicable
- The value is known, but you are not allowed to see it
Have to be careful with equality, but SQL considers the equality operation on NULL to always be false. You can use the `IS NULL` operation to check if a field is null.

#### Compose operator
If $f(g(x))=y$ then $(f\circ g)(x) = y$

Given two binary relations
$$R\subseteq S\times T$$
$$Q\subseteq T\times U$$
their composition is $Q\circ R\subseteq S\times U$

### Directed graphs
![[DirectedGraph.png]]
- A is a binary relation over V: $A\subseteq V\times V$
- The arc $(u,v)\in A$, then we have an arc from u to v, also known as a directed edge or a relationship
![[GraphComposition.png]]
Composition on the graph will look at each relationship within the graph, and join the outputs to their corresponding inputs.

#### Iterated composition
Defined as $R^1\triangleq R, R_{n+1}\triangleq R \circ R^n$
Supposing $v_{1},v_{2},\dots,v_{k+1}$ is a sequence of vertices, then this sequence represents a path in G of length k when $(v_{i},v_{i+1})\in A$ for $i \in \{ 1,2,\dots,k \}$
Often written as $v_{1} \to v_{2} \to\dots v_{k}$

#### Transitive closure (notes need updating)
Suppose R is a binary relation over $S,R\subseteq S\times S$. The transitive closure of R, denoted $R^+$ is the smallest binary relation on S such that $R\subseteq R^+$ and $R^+$ is transitive. 