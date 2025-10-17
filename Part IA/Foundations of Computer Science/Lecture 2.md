### Expression evaluation
Focus on expressions, ignoring side effects 

```ocaml
let rec power x n = 
  if n = 1 then x
  else if even n then
    power (x *. x) (n / 2)
  else 
    x *= power (x *. x) (n / 2)
```
`val power : float -> int -> float`

```ocaml
let rec nsum n =
  if n = 0 then
    0
  else
    n + nsum (n - 1)
```
In this example, nothing can progress until the final expression is evaluated - `nsum(0)`. This means all intermediate values are stored in the stack, which takes up memory, and if enough layers are reached there can be a stack overflow error.