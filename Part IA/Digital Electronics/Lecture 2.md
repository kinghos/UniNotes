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

### Quine-McCluskey Minimisation

Given a function and its minterms, the QM method is more effective at simplifying the linear algebra than Karnaugh maps

1. Create a table with 3 columns:
	- Group: the number of ones
	- Minterm
	- Binary representation of minterms
2. Make a second table with 3 columns:
	- Group
	- Matched pairs - comparing minterms in adjacent groups, and finding those that only differ by one variable
	- Binary representiation - mark the changing variable with an X