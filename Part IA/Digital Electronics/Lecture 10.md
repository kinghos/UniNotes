### Elimination of Redundant States
$\lambda(p, x)=\lambda(q,x)$ and $\sigma(p,x)\equiv \sigma(q,x)$
where
$\lambda(p, x)$ is the output given the present state and input x and
$\sigma(p,x)$ is the next state given the present state p and input x

To eliminate redundant states, each pair of states must be compared.
![[Pasted image 20251031111215.png]]
Indicate in each cell any implied equivalent state pairs.
A cell will not contain any implied state pairs if the outputs are different, since this does not satisfy our earlier equivalence theorem.

- Mark each cell with different outputs with an X
- Any pairs with the same outputs must have their corresponding next state pairs written in the cell, e.g. A and B have the same output, so $D\equiv F$ and $C\equiv H$. Repeat for all cells iwth same output.
- Remove self-implied pairs, e.g. 