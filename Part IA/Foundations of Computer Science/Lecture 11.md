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