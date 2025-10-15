##### Truth tables
A minterm must contain all variables (in either complement or uncomplemented form). e.g. $\bar{x}.y.z$ but not $y.z$

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