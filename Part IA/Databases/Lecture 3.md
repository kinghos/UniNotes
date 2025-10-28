Suppose that S and T are sets. The Cartesian product, $S \times T$ is the set $$
S \times T = \{(s,t)|s\in S, t\in T\}
$$
A binary relation over $S\times T$ is any set $R$ with
$$
R\subseteq S\times T 
$$
S and T are referred to as domains
If we have n sets, $S_1, S_2, ..., S_n$
then an n-ary relation R is a set $$
R \subseteq S_{1} \times S_{2} \times \dots \times S_{n}= \{ (s_{1, s_{2}, \dots, s_{n}}) |s_{i} \in S_{i} \}
$$
Associate a name, $A_i$ with each domain $S_i$
Instead of tuples use records - sets of pairs each associating an attribute name with a value in domain $S_i$

A database relation R is a finite set. R's schema can be specified as
$$
R(A_{1}:S_{1},A_{2}:S_{2}, \dots A_{n}:S_{n})
$$
For example:
Schema: `Students(name: string, sid: string, age: integer)`
An instance of this schema:
```sql
Students = {
	{(sid, fm21), (name, Fatima), (age, 20)},
	{(name, Eva), (sid, ev77), (age, 18)},
	{(age, 19), (name, James), (sid, jj25)}
}
```

#### Relational Algebra abstract syntax
![[Pasted image 20251028111947.png]]
- $p$ is a simple boolean predicate over attributes values
- $\mathbf{X} = \{ A_{1}, A_{2}, \dots, A_{k} \}$ is a set of attributes
- $M=\{ A_{1} \mapsto B_{1}, A_{2}\mapsto B_{2},\dots A_{k}\mapsto B_{2}\}$ is a renaming map
- A query Q must be well-formed: all column names of result are distinct. In $Q_1\times Q_2$, the two sub-queries cannot share any column names while in $Q_1\cup Q_2$, the two sub-queries must share all column names.

| Operator   | RA                                     | SQL                                         |
| ---------- | -------------------------------------- | ------------------------------------------- |
| Selection  | $\sigma_{A>12}(R)$                     | `SELECT DISTINCT * FROM R WHERE R.A > 12`   |
| Projection | $\pi_{B,C}(R)$                         | `SELECT DISTINCT B, C FROM R`               |
| Renaming   | $\rho_{\{B\mapsto E, D\mapsto F\}}(R)$ | `SELECT A, B AS E, C, D as F FROM R`        |
| Union      | $R \cup S$                             | `(SELECT * FROM R) UNION (SELECT * FROM S)` |
|            |                                        |                                             |
