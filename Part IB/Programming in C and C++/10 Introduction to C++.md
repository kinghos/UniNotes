#### Big picture differences
- Character literals are type `char`
- New type `bool`
- Reference types, type constructor `&`, can have `int x, *y, &z`
- `enum` types are distinct, not just integers
- Generalised form of `struct` with `class`
- Names for `enum, class, struct, union` can be used directly as types
- Member functions can specify `this` to be `const`

#### `Auto` and `thread_local`
- `auto` is reused in initialised definitions to mean the type of the initialising expression, e.g. `auto x = foo(3)`
- `thread_local` is an additional storage class, alternative to `static`
