#### Types of language
Declarative - specify what to do, not how to do it.
- Functional - functions at the core
- Logic - reason about facts and rules
- Reactive - reason about streams of data and events
- e.g. HTML, SQL, OCaml
Imperative - specify both what and how
- Procedural - group code into procedures
- OOP - group procedures and data together

#### OOP
OOP is a programming paradigm based on the concept of objects, which can contain data and code - data in the form of fields (attributes/properties) and code in the form of procedures/methods. Objects are defined by classes that group fields and methods.
Features:
- Encapsulation
- Abstraction
- Inheritance
- Polymorphism

#### Bytecode
Java compiles to architecture agnostic machine code. This can then run on any device through the JVM.
- Bytecode is compiled so it is not easy to reverse engineer
- The JVM ships with tons of libraries which make the bytecode small
- The hardest part of the compile is done by the compiler, leaving the computer-readable bytecode to be translated by the JVM
- However, there is still a performance hit compared to fully compiled native code.