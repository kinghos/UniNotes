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
