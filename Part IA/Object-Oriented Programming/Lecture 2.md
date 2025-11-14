An object is a bundle of state and behaviour
The state of an object is defined through its fields, the behaviours of an object are defined through its methods.

### Classes
- A class is a blueprint for a specific type of object
- An object is an **instantiation** of a class
- A class defines both type and implementation
	- Type: where the object can be used
	- Implementation: how the object does things.
- The methods of a class can be seen as an API

#### Constructors
- Constructors do not return anything, even void
- They must have the same name as the class
- Multiple constructors are permitted given they have different signatures
#### The `static` keyword
- A static field is created only once in the program's execution, despite being declared as part of a class.
- Every object will reference the same value
- Static methods do not need to be instantiated.

#### UML Diagrams
- Title
- State
- Behaviour
- - means private access, + means public access

#### Single Responsibility Principle
- Each class should have a single function
- Model View Controller:
	- Model - the code that stores and manipulates the underlying state
	- View - the code that deals with how to draw the state to the screen
	- Controller - the code that sequences everything together, handling input such as clicks, updating the view code when it needs to be updated.

#### Cohesion
- Cohesion measures how strongly grouped the responsibilities of a class are

#### Encapsulation
By setting state as private, you can control how that field is modified. In other words, encapsulation decouples behaviour from state.

| Modifier    | Class | Package | Subclass | Everyone |
| ----------- | ----- | ------- | -------- | -------- |
| `public`    | ☑     | ☑       | ☑        | ☑        |
| `protected` | ☑     | ☑       | ☑        | ❌        |
| no modifier | ☑     | ☑       | ❌        | ❌        |
| `private`   | ☑     | ❌       | ❌        | ❌        |
