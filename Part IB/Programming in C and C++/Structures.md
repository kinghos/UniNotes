- Collection of one or more members/fields
- Method of abstraction/grouping
- May contain structures
- Can be assigned to, passed to, and returned from functions
- Declaring a structure creates a new type
```c
struct circle c;
struct circle c = {12, 23, 5};
struct circle d = {.x = 12, .y = 23, .r = 5};
struct circle c = circle_init();
struct circle {int x; int y; unsigned int r;} a, b; // several instances
```
- Access members with `.` or `->`
- Structs cannot store themselves, but can store pointers whose type is themselves.
#### Bit fields
```c
struct fields {int f1 : 2; int f2 : 3;};
```
- Allows low-level acess to individual bits of a word