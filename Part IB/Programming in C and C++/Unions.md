- Holds a number of different types
```c
union u {int i; float f; char c;};
```
- Size is the size of its largest member
- Type held can change during execution
- Type retrieved must be the type most recently stored
- Can be nested inside [[Structures|structures]]