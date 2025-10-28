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

}
```