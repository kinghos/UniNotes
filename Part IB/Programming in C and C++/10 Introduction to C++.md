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
#### Enumeration
Declare with enum name, e.g.
```cpp
enum flag {is_keyword=1, is_static=2, ...}
flag f = is_keyword;
```
#### References
- Provide an alias for a variable
- Generally used for specifying parameters to functions and return values as well as overloaded operators
```cpp
int i[] = {1, 3};
int &refi = i[0];
int *ptri = &i[0];
```
- References must be initialised when declared
- Connection between a reference and what it refers to cannot be changed after initialisation
```cpp
refi++; // increments value referenced
ptri++; // increments pointer to &i[1]
```
When used as a function parameter, a referenced value is not copied
```cpp
void inc(int& i) {i++;}
```
- Declare a reference as `const` when no modification takes place
- It can be much more efficient to pass a large struct by reference
#### Overloaded functions
- Can define two functions with the same name, but varying in argument types
- Type conversion is used to find the "best" match, e.g. casting an int to long or double
- To overload, functions must be in the same scope
- Functions can have default arguments
#### Namespaces
- Data can be grouped into namespaces
- e.g. `using namespace Module1;`
- This is a scope and expresses logical program structure
- Collects related pieces of code
- Nameless namespaces limit the scope of variables, functions and classes within it to the local execution unit