#### Problems with data redundancy
Insertion - how can we tell if a newly-inserted record is consistent with existing records?
Deletion - we lose information about a Director if we delete all their films from the table
Update - What if a directors name is misspelled? We may update it correctly for one film, but not for another.

Performance issues - a transaction implementing a conceptually simple update has a lot of work to do, possibly locking the whole table

Breaking down tables e.g. table for people, table for films, reduces redundancy. A third table can be used to hold the relationship between the two.

Suppose $R(X)$ is a relational schema with $Z\subseteq X$. If for any records u and v in any instance of R we have
$$
u.[Z]=v.[Z]\implies u.[X]=v.[X],
$$
then Z is a superkey for R. If no proper subset of Z is a superkey, then Z is a key for R. We write $R(\underline{Z}, Y)$ to indicate that Z is a key for $R(Z\cup Y)$

A database is said to have referential integrity when all foreign key constraints are satisfied.

A schema with a simple key:
```sql
CREATE TABLE genres (
genre_id integer NOT NULL,
genre TEXT NOT NULL,
PRIMARY KEY (genre_id));
```
A schema that is all-key and that has two foreign keys:
```sql
CREATE TABLE has_genre (
movie_id varchar(16) NOT NULL -- up to 16 chars
REFERENCES movies (movie_id),
genre_id integer NOT NULL
REFERENCES genres (genre_id),
PRIMARY KEY (movie_id, genre_id));
```

Implementing multiple relationships with two tables is possible.
Two tables:
$$
R(\underline{X,Z}, U)
$$
$$
Q(\underline{X,Z}, V)
$$
Can be combined into one:
$$RQ(\underline{X, Z, type}, U, V)$$
Using a tag domain(type) = {r, q} (for some constant values r and q)
- represent an R-record {x, z, u} as an RQ-record (x, z, r, u, NULL)
- represent a Q-record {x, z, v} as an RQ-record (x, z, q, NULL, v)
- 