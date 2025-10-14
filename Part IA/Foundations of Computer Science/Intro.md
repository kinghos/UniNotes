Recursive functions are declared with `let rec f x ...`
match statements can be used to determine outputs of a function e.g.
```ocaml
let rec g v = match v with
| 0 -> 1
| 1 -> 1 
| n -> g (n-1) + g (n-2);;
```

Pattern matching is done in this example with `x` being the first element, and `xs` being the rest of the list. The base case is `[]`. This function would return the length of the list.
The first pattern is to the right of the arrow, then when that pattern is failed to match, the next pattern is checked
```ocaml
let rec i = function (x::xs) -> 1 + i xs
	| [] -> 0;; 
```

OCaml can manage lists of any type, through treating the unknown type as "$\alpha$" type
```ocaml
let k (y::ys) = y;;
```
This returns `val k : 'a list -> 'a = <fun>`

The following syntax can be used to take multiple arguments and is known as "currying" - this declares y as a function.
```ocaml
let addr x y = x + y
```

The comma operator is used to declare a tuple. Here, `listify "hi" [1;2;3;];;` returns `(string * int) list = [("hi", 1); ("hi", 2); ("hi", 3)]`
```ocaml
let rec listify i = function
| [] -> []
| x::xs -> (i,x) :: listify i xs;;
```

The reverse apply operator, `|>`, means you provide the argument first and the function next, allowing you to chain functions.
```ocaml
[1;2;3;]
|> map (fun x->(x,x))
|> map (fun (a,b)->a+b);;
```

Here, p is a function. The compiler can automatically determine that p is a function that returns a boolean based on its usage within the filter function.
```ocaml
let rec filter p lst = match lst with
| [] -> []
| x::xs when p x -> x :: filter p xs
| _::xs -> filter p xs;;
```

Types can be declared with the `type` keyword.
```ocaml
type ncCell = O | X | Blank;;
type sudukoCell = N of int | Empty;; (*Parameter for argument*)
type a' tree1 = ... (*Creates new type of form int tree1 for example where int can be any type*)
```
