Recurrence relations - substitution method, or draw out the tree, starting with the $\Theta$part and branching off into the recursive and other $\Theta$ parts

Master theorem - what you are looking for is which is polynomially larger - $n^{\log_{b}a}$ or $f(n)$. If they are of the same order, then $T(n) \in \Theta(n^{\log_{b}a} \lg n)$