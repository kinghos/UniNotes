---
tags:
  - booleanAlgebra
---
To simplify into POS form, group the zeros and apply DeMorgan's laws.
Some values can be mostly ignored - "don't care conditions". These can be represented as an X on a Karnaugh map, and treated as either a 0 or a 1.

- Cover - a term is said to cover a minterm if that minterm is part of that term
- Prime implicant - a term that cannot be further combined
- Essential prime implicant - a prime implicant that covers a minterm that no other prime implicant covers
- Covering set - a minimum set of prime implicants which includes all essential terms plus any other prime implicant required to cover all minterms
