### Procedural Programming
Procedural programs can change the machine state.
They can interact with its environment, and use control structures like branching, iteration and procedures.
Computer memory is abstracted:
- References to memory cells
- Arrays
- Linked structures, especially linked lists

```ocaml
ref;; (*Create a box*)
(!);; (*Inspect the contents of the box*)
(:=);; (*Update the contents of the box*)
```
The return type of `:=` is unit.
```ocaml
let p = ref 5
p := !p + 1
let ps = [ref 77; p]
List.hd ps := 3
```
Here, ps is not updated, only the reference at the head.

#### Commands
A series of expressions can be executed by being separated with semicolons, the value of the last expression is what is returned.
A typical command returns unit.
```ocaml
1 + (print_endline "abc"; 3; 101);; (*is equivalent to*)
1 + (let () = print_endline "abc" in let _ = 3 in 101)
```
This code prints "abc", then 102

**Semicolons will terminate if statements**
```ocaml
if true then
  print_endline "it was true"
else 
  print_endline "it was false";
  print_endline "more printing here"
```
***This code will only print "more printing here" as the semicolon terminates the if statement***

#### The `while` command
```ocaml
let tlopt = function
| [] -> None
| _::xs -> Some xs

let length xs =
  let lp  = ref xs in (* list of uncounted elements *)
  let np  = ref 0  in (* accumulated count *)
  let fin = ref false in
  while not !fin do
    match tlopt !lp with
    | None -> fin := true
    | Some xs ->
        lp := xs;
        np := 1 + !np
  done;
  !np (* the final count is returned *)
```
`while` returns unit.

#### Private, Persistent References
```ocaml
exception TooMuch of int
let makeAccount initBalance =
  let balance = ref initBalance in
  let withdraw amt =
     if amt > !balance then
       raise (TooMuch (amt - !balance))
     else begin
       balance := !balance - amt;
       !balance
     end
  in
  withdraw
```
When