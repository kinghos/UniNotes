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