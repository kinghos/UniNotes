Regular languages are closed under finite intersections
### The pumping lemma
Some examples of non-regular languages include:
- The set of strings over $\{ (,),a,b, \dots ,z \}$ in which parentheses are well balanced
- The set of strings over $\{ a,b, \dots ,z \}$ that are palindromes, that read the same backwards as forwards
- The set of strings over $\{ a,b \}$ consisting of some number of $a$s followed by the same number of $b$s.

Let $L$ be a formal language over $\Sigma$. An expansion/pumping bracket in $L$ is defined to be a tuple of strings $(u_{1},v,u_{2})$ where $v\not=\epsilon$ such that for all $n\geq 0$, we have $u_{1}v^nu_{2}\in L$
$u_{1}v$ is known as the left hand component and $u_{1}vu_{2}$ as the concatenation of the pumping bracket
A number $\ell>1$ is said to have the pumping property with respect to $L$ when any string $w\in L$ satisfying $|w|\geq \ell$ is the concatenation of some pumping bracket in $L$ whose left-hand component has length less than or equal to $\ell$.

#### The lemma
Let $M$ be a DFA. Then the cardinality $\#Q_{M}$ of the set of states of $M$ satisfies the pumping property with respect to $\mathcal{L}(M)$ (in other words $\ell=\#Q_{M}$)

For any regular language $L$ there exists a number $\ell >1$ satisfying the pumping property with respect to $L$.
