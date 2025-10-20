### Lists
```ocaml
let x = [3; 5; 9]
let y = [(1, "one"); (2, "two")]

(*Append operator*)
x @ [2; 10]

List.rev ["one"; "two"]
```
#### Tuples
- Fixed size
- Heterogeneous
- Comma as separator

Lists can be constructed using two primitives:
- `[]` <- nil, empty list
- `::` <- cons
```ocaml
let l = 9 :: []
let l2 = 5 :: l
let l3 = 3 :: l2
(*val l3: int list = [3; 5; 9]*)
```
`x::l` is the list with head `x` and tail `l`

```ocaml
let rec up_to m n = 
  if m > n then []
  else
    m :: up_to (m+1) n
``` 

#### Pattern matching
```ocaml
let null = function
  | [] -> true
  | _::_ -> false
```

```ocaml
let is_zero = function
  | 0 -> true
  | _ -> false
```

Polymorphic functio