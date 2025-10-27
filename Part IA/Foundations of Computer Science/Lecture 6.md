### Custom Datatypes
An enumeration type can be declared like so:
```ocaml
type vehicle = Bike
             | Motorbike
             | Car
             | Lorry
```
The representation in memory is more efficient than if stored with strings. More vehicles can be added by extending the definitions. Different custom types cannot be intermixed, unlike strings or integers.

#### Generalising
```ocaml
type vehicle = Bike
    | Motorbike of int
    | Car of bool
    | Lorry of int

let v = Motorbike 250
```
This can then be pattern matched
```ocaml
let wheels = function
  | Bike -> 2
  | Motorbike _ -> 2
  | Car robin -> if robin then 3 else 4
  | Lorry w -> w
```

#### Polymorphic types
```ocaml
type 'a option = 
  | None
  | Some of 'a

type ('a, 'b) result =
  | Ok of 'a
  | Error of 'b
```
Can be used in place of an exception to return something

### Exceptions
Exception handling allows code to recover by raising an exception or but attempting an alternative
```ocaml
try
  print_endline "pre exception";
  raise (NoChange 1);
  print_endline "post exception"
with
  | NoChange _ ->
    print_endline "handled a NoChange exception"
```
`raise` will jump to the nearest try/with handler that matches the exception.

```ocaml
exception Change
let rec change till amt =
  match till, amt with
  | _, 0         -> []
  | [], _        -> raise Change
  | c::till, amt -> if amt < 0 then raise Change
                    else try c :: change (c::till) (amt - c)
                         with Change -> change till amt
```
`Change` is raised if we run out of coins or if the amount goes negative. The recursive call is in an exception handler, this means the choice is undone if it goes wrong. This means the most recent choice is undone, so if the code needs to backtrack it will keep catching exceptions down the stack. If the top level has an error then it must be impossible to give change.

### Recursive Types
```ocaml
type 'a mylist = 
  | Nil
  | Cons of 'a * 'a mylist
```

This code declares a recursive type for a binary tree
```ocaml
type 'a tree =
  | Lf
  | Br of 'a * 'a tree * 'a tree
```

```ocaml
let tree = Br(1, Br(2, Br(4, Lf, Lf),
                       Br(5, Lf, Lf)),
			     Br(3, Lf, Lf))
```

Pattern matching can be done on these recursive types
```ocaml
let rec count = function
| Lf -> 0
| Br (v, t1, t2) -> 1 + count t1 + count t2

let rec depth = function
| Lf -> 0
| Br (v, t1, t2) -> 1 + max (depth t1) (depth t2)
```
