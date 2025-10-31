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
let fn = fun k -> (fun n -> n * 2 + k)
let partial = fn 1 (*partial is the function (fun n -> n * 2 + k)*)
```
A curried function **returns another function as its result**

The `^` operator concatenates strings.

```ocaml
let prefix = fun a -> (fun b -> a ^ b)
let promote = prefix "Professor "
promote "Mopp" (*Professor Mopp*)
```
Operators like `>=` can be passed as functions using brackets `( >= )`

Function to transpose a matrix
```ocaml
let rec transp = function
  | []::_ -> []
  | rows -> (map List.hd rows) ::
            (transp (map List.tl rows))
```

Matrix multiplication
```ocaml
let rec dotprod xs ys =
  match xs, ys with
  | [], [] -> 0.0
  | x::xs, y::ys ->  (x *. y) +. (dotprod xs ys)
  
let rec matprod arows brows =
  let cols = transp brows in
  map (fun row -> map (dotprod row) cols) arows
```

### Predicates
A predicate is a boolean-valued function.
```ocaml
let rec exists p = function
| [] -> false
| x::xs -> (p x) || (exists p xs)
```
Here, the OR function evaluates the first argument first - if it is true, it doesn't waste time evaluating the second argument.