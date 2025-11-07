Both SQL and relational algebra model in the same way.
Relational algebra is set-theoretic (no duplicates)
SQL allows modification of data.

Normalised data prevents:
- Modelling inconsistency
- Lower update performance / more writes
- Lower concurrency (more locks to stay consistent)
