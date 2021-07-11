### Final vs Static
- For more info refer to [stackoverflow](https://stackoverflow.com/questions/13772827/difference-between-static-and-final)

### Interfaces
- When child classes implementing a particular interface and is upcasted(it is done implicitly), the instance receiving it will only be able to use the methods in the interface and the overriden methods in the child class.

- Abstract classes can have constants, members, method stubs (methods without a body) and defined methods, whereas interfaces can only have constants and methods stubs.

- Methods and members of an abstract class can be defined with any visibility, whereas all methods of an interface must be defined as public (they are defined public by default).

- When inheriting an abstract class, a concrete child class must define the abstract methods, whereas an abstract class can extend another abstract class and abstract methods from the parent class don't have to be defined.

- Similarly, an interface extending another interface is not responsible for implementing methods from the parent interface. This is because interfaces cannot define any implementation.

- A child class can only extend a single class (abstract or concrete), whereas an interface can extend or a class can implement multiple other interfaces.

- A child class can define abstract methods with the same or less restrictive visibility, whereas a class implementing an interface must define the methods with the exact same visibility (public).

**Note: -**
- Set, Map, SortedSet, List, Queue are interfaces.