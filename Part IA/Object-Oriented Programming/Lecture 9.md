Try-with-resources - will clear declared statements in the brackets after the block ends

#### Benefits of exceptions
- Documentation
- Type safety
- Separation of concern - main logic and exception logic are separated with the try-catch

#### Checked vs unchecked
Checked - must be handled or passed up
- Client must take a recovery action
- Java requires you to declare exceptions that your method throws
- Java requires catching the exception when the function is called
Unchecked - not expected to be handled
- Nothing the client could do
- Programming error
- Extends `RuntimeException`
- e.g. `NullPointerException`

- Never ignore an exception
- Never catch `Exception`
- Document exceptions at the API level
- Avoid implementation-specific exceptions (be more general in their names)
- Never use exceptions for control flow

#### Assertions
Check ba 