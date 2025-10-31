In OCaml, functions can be:
- passed as arguments to other functions
- returned as results
- put into lists, trees etc.
but they cannot be tested for equality

#### Unnamed functions
Mathematically, $\text{fun}\ x  \to E$ is the function $f(x)=E$
```ocaml
fun n -> n * 2
(fun n -> n * 2) 4 (*Returns 8*)
let double = fun n -> n * 2
fun x -> match x with 0 -> true | _ -> false
```

### Currying
In its simplest form, a function can only have one argument. Multiple arguments can either be taken with tuples, or with a function that returns another function as a result. Expressing a function taking multiple arguments as nested functions is known as currying.
```ocaml
fun k -> (fun n -> n * 2 + k)
```
