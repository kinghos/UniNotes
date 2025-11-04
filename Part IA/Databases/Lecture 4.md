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