### Java's Generics Implementation
Adding generics while retaining backwards compatibility:
1. Templates - the generic class is treated as a template by the compiler, which generates new classes from it whenever you ask for something, e.g. `ArrayList<Integer>` creates a class for `ArrayListInteger`. C++ uses this method
2. Type erasure - At compile time, do all the type checks you can, then delete the type information in the compiler output. e.g. `ArrayList<Integer>` is checked, and then written to bytecode as plain ArrayList. The JVM will never know and so dynamic checks aren't possible. This is what Java implements. Primitives **cannot** be passed in
Pros of type erasure:
- Bytecode unchanged, hence backwards compatible
- 