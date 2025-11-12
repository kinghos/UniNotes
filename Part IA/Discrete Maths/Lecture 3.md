#### Conjunctive statements
$P \text{ and } Q$
or in other words both P and also Q hold
or in symbols $P \land Q$ or $P\ \&\ Q$
The proof strategy is to first prove P and subsequently prove Q or vice versa
##### Example
For every integer n we have that $6|n \iff 2\ |\ n \land 3\ |\ n$
To prove, assume $6\ |\ n$ and prove $2\ |\ n$, then $3\ |\ n$
For the other side, assuming $2\ |\ n \land 3\ |\ n$ means you assume both statements are true.

#### Existential quantification
There exists and individual x in the universe of discourse for which the property $P(x)$ holds.
$$\exists x.P(x)$$
The proof strategy is to find a witness for the existential statement; that is a value of x, say w, for which you think $P(x)$ will be true, and show that indeed $P(w)$, i.e. the predicate $P(x)$ instantiated with the value w, holds.

To use an assumption of the form $\exists x.P(x)$, introduce a new variable $x_0$ into the proof to stand for some individual for which the property $P(x)$ holds. This means that you can now assume $P(x_0)$ true.

#### Unique existence
The notation $\exists!x.P(x)$ stands for the unique existence of an x for which the property P(x). In other words, x is the only value for which $P(x)$ holds.
To prove $\forall x.\exists!y.P(x,y)$ for an arbitrary x, construct the unique witness and name it, say as f(x) showing that $P(x, f(x))$ and $\forall y.P(x,y)\implies y=f(x)$

