#### Types

| Type     | Description            |
| -------- | ---------------------- |
| `char`   | characters (>= 8 bits) |
| `int`    | integers (>= 16 bits)  |
| `float`  | single-precision float |
| `double` | double-precision float |
- Precise size is architecture-dependent
- Type operators alter meaning: `unsigned`, `short`, `long`, `const`, `volatile`
	- Longs can be denoted in literals with `L` at the end, e.g. `8L`
	- Floats can be denoted with an `f`. Doubles are the default
	- Octals are denoted by a leading 0 e.g. `06` and hex numbers by `0x` e.g. `0x34`
- Fixed size types: `int16_t`,  `uint64_t`

#### Enums
```c
enum boolean {TRUE, FALSE}
enum months {JAN=1, FEB, MAR}
```
Numbering defaults from 0 counting up

#### Variables
- Variables must be declared before use
- Variables must be defined exactly once (i.e. allocated storage)
- Variable names cannot start with a digit

#### Operators
- Arithmetic/logical shifts are deduced based on the type of the operands.
- `sizeof` returns the number of bytes of the input variable
- Automatic type conversion is generally widening
- Narrowing is possible, e.g. `int` to `char`
- Casting is done as `c = (char) 1234L`

#### Expressions
- An expression is a literal, variable, function call or formed from expressions combined with operators e.g. `x *= y - z`
- Every expression has a type and a result
- An expression becomes a statement when followed by a semicolon
- Several expressions can be separated using a comma and evaluated left to right
- In a comma-separated expression, the type and value of the expression is the type and value of the rightmost expression

#### Blocks
- A block or compound statement is formed when multiple statements are surrounded with braces: `{s1;s2;s3}`
- This is then equivalent to a single statement

