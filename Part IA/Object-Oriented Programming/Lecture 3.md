#### Primitives
Values of variables:
- For primitive types in memory, they are stored directly
- For objects, the value of the associated variable is a reference, pointing to the data associated with that object.
- Values are copied on assignment.
- Values that are references also copy but NOT therefore the objects

#### The function stack
When a function is called, three things are stored
- Arguments
- Local variables
- Memory address to jump to when the function completes
These things are stored in a stack. When a stack frame is popped, all the variables it created will be deleted

#### The heap
The heap has gaps between objects.

#### Pointers
Pointers point directly to memory addresses and allow more direct memory manipulation.
References can be thought of as limited pointers.
