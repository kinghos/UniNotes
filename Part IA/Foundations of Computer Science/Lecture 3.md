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

`null` is a polymorphic function - takes `'a list` (alpha list) as input, which can be a list of any type

```ocaml
let rec nlength = function
  | [] -> 0
  | _ :: xs -> 1 + nlength xs
```
This function has nested computation, meaning it has a time and space complexity of $O(n)$

```ocaml
let rec addlen = function
  | (n, []) -> n
  | (n, _::xs) -> addlen(n+1, xs)
```
This function is tail recursive, so its time complexity stays the same but its space complexity is $O(1)$

```ocaml
let rec append = function
  | ([], ys) -> ys
  | (x::xs, ys) -> x :: append (xs, ys)
```  

#### Reversing a list
This function has complexity $O(n^2)$
```ocaml
let rec nrev = function
  | [] -> []
  | x::xs -> (nrev xs) @ [x]
```

Using an accumulator to make the function tail recursive, the complexity becomes $O(n)$
```ocaml
let rec rev_app = function
  | ([], ys) -> ys
  | (x::xs, ys) -> rev_app (xs, x::ys)
```
