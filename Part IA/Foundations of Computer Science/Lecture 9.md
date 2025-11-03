Sequential programs - searching, data processing
Reactive programs - autonomous devices, resource allocation

Producer -> Filter -> ... -> Filter -> Consumer

The producer outputs a stream of data.
The filter stages convert the input stream to an output stream.
The consumer takes as many elements as necessary. It decides when data is needed.

#### The unit type
`()` is the only member of the unit type. It behaves as a tuple and is a constructor. It can be used to delay the processing of a function
```ocaml
let f () -> 'Hello' ^ 'World'
f () (*Does not concat until this line called*)
```

### Lazy lists
```ocaml
type 'a seq =
| Nil
| Cons of 'a * (unit -> 'a seq)

let head = function
  | (Cons (x, _)) -> x
  | _ -> raise (Failure "head")
  
let tail = function
  | (Cons (_, xf)) -> xf ()
  | _ -> raise (Failure "tail")
  
let rec from k = Cons (k, fun () -> from (k+1))
```
Calling `tail` here generates the next element in the list. Using the unit type helps "stop" the generation of the list, and instead allowing it to be extended on demand.
#### Consuming a list
```ocaml
let rec get n s =
  match n, s with
  | 0, _            -> []
  | n, Nil          -> []
  | n, Cons (x, xf) -> x :: get (n-1) (xf ())
```
This gets the first n elements as a list

#### Appending a list
```ocaml
let rec interleave xq yq =
  match xq with
  | Nil -> yq
  | Cons (x, xf) -> Cons (x, fun () -> interleave yq (xf ()))
```
Combined with `get`, this can combine two lazy lists with alternating terms.

### Functionals for lazy lists
```ocaml
let rec filterq p = function
| Nil -> Nil
| Cons (x, xf) ->
    if p x then
      Cons (x, fun () -> filterq p (xf ()))
    else
      filterq p (xf ())
```

```ocaml
let rec iterates f x =
  Cons (x, fun () -> iterates f (f x))
```
This returns the infinite sequence $x, f(x), f(f(x)),\dots$
