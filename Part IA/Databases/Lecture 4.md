#### Problems with data redundancy
Insertion - how can we tell if a newly-inserted record is consistent with existing records?
Deletion - we lose information about a Director if we delete all their films from the table
Update - What if a directors name is misspelled? We may update it correctly for one film, but not for another.

Performance issues - a transaction implementing a conceptually simple update has a lot of work to do, possibly locking the whole table

Breaking down tables e.g. table for people, table for films, reduces redundancy. A third table can be used to hold the relationship between the two.