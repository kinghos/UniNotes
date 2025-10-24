### Sorting
The number of comparisons is usually the measure of efficiency for a sorting algorithm.

#### Insertion sort
```ocaml
let rec ins x = function
  | [] -> [x]
  | y::ys -> if x <= y then x :: y :: ys
			 else y :: ins x ys

let rec insort = function
  | [] -> []
  | x::xs -> ins x (insort xs)
```

Using `#trace ...` can be used to output a trace of a function

#### Quicksort
- Choose a pivot element $a$
- Divide: partition the input into two sublists
	- Those at most $a$ in value
	- Those exceeding $a$
- Conquer: recursively sort both sublists
- Combine: append the two sorted lists together

```ocaml
let rec quick = function
  | [] -> []
  | [x] -> [x]
  | a::bs ->
      let rec part l r = function
        | [] -> (quick l) @ (a :: quick r)
        | x::xs ->
            if (x <= a) then
              part (x::l) r xs
            else
              part l (x::r) xs
      in
      part [] [] bs
```

##### Append-free quicksort
```ocaml
let rec quik = function
  | ([], sorted) -> sorted
  | ([x], sorted) -> x::sorted
  | a::bs, sorted ->
     let rec part = function
       | l, r, [] -> quik (l, a :: quik (r, sorted))
       | l, r, x::xs ->
           if x <= a then
             part (x::l, r, xs)
           else
             part (l, x::r, xs)
     in
     part ([], [], bs)
```

#### Merge sort
```ocaml
let rec merge = function
  | [], ys -> ys
  | xs, [] -> xs
  | x::xs, y::ys ->
      if x <= y then
        x :: merge (xs, y::ys)
      else
        y :: merge (x::xs, ys)
```


- Insertion sort: simple to code, quadratic complexity
- Quicksort: fast on average, quadratic complexity in worst case
- Merge sort: optimal in theory, often slower than quicksort in practice 