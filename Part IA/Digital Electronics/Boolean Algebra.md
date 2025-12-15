
| Gate | Symbol         |
| ---- | -------------- |
| NOT  | $\overline{A}$ |
| AND  | $A.B$          |
| OR   | $A+B$          |
| XOR  | $A\oplus B$    |
##### Order of operations
AND takes precedence over OR, e.g.
$a.b+c.d = (a.b)+(c.d)$

##### Distribution
$a.(b+c+\dots)=(a.b)+(a.c)+\dots$
$a+(b.c. \dots)=(a+b).(a+c). \dots$
##### Absorption
$a+(a.c)=a$
$a.(a+c)=a$

##### Consensus theorem
$a.b +\bar{a}.c + b.c =a.b +\bar{a}.c$
$(a+b).(\bar{a}+c).(b+c)=(a+b).(\bar{a}+c)$

Try expanding each term until it includes one instance of each variable, then simplify.
e.g. $a.b+a = a.b + a.b + a.\bar{b} = a.\bar{b}+a.b=a$

##### DeMorgan's Theorem
$\overline{a+b+c+\dots}=\bar{a}.\bar{b}.\bar{c}$
$\overline{a.b.c.\dots}={\bar{a}+\bar{b}+\bar{c}}$

##### Truth tables
A minterm must contain all variables (in either complement or uncomplemented form). e.g. $\bar{x}.y.z$ but not $y.z$. Minterms are essentially the values for which the function outputs 1.

##### Disjunctive Normal Form
- A boolean function expressed as the disjunction (ORing) of its minterms is said to be in the Disjunctive Normal Form
- A boolean function expressed as the ORing of ANDed variables is said to be in Sum of Products form


A maxterm of n boolean variables is the disjunction (ORing) of all the variables either in complemented or uncomplemented form.
$$
f = x.\bar{y}.z+x.\bar{y}.z+x.y.\bar{z}
$$
#### Karnaugh Maps
To simplify into POS form, group the zeros and apply DeMorgan's laws.
Some values can be mostly ignored - "don't care conditions". These can be represented as an X on a Karnaugh map, and treated as either a 0 or a 1.

- Cover - a term is said to cover a minterm if that minterm is part of that term
- Prime implicant - a term that cannot be further combined
- Essential prime implicant - a prime implicant that covers a minterm that no other prime implicant covers
- Covering set - a minimum set of prime implicants which includes all essential terms plus any other prime implicant required to cover all minterms

### [[Quine-McCluskey Minimisation]]

