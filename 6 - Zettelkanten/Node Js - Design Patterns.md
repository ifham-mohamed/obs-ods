
2024-12-24 12:22

Status:

Tags:

## Learning objectives

- Design patterns and anti-patterns
- Singleton pattern
- Prototype pattern
- Factory pattern
- Builder pattern
- Adapter pattern
- Proxy pattern
- Decorator pattern
- Command pattern
- Observer pattern
- Strategy pattern

![[Pasted image 20241224122247.png]]

- **Design Patterns and Anti-Patterns**: Learn about common design patterns and anti-patterns to avoid.
- **Creational Patterns**: Understand and implement patterns like Singleton, Prototype, Factory, and Builder.
- **Structural Patterns**: Explore patterns such as Adapter, Proxy, Composite, and Decorator.
- **Behavioral Patterns**: Dive into patterns like Chain of Responsibility, Command, Iterator, Observer, and Strategy.

![[Pasted image 20241224122459.png]]

![[Pasted image 20241224122513.png]]
# Node Js - Design Patterns

Reusable, reliable solutions to problems that we face every day in software development.

- **Cataloged solutions**
- **Reusable in many different situations**
- **Well documented**
- **Language for collaboration**
- **Improve Architecture**

![[Pasted image 20241224122909.png]]


Design Pattern Essentials
1. Pattern name
2. The problem
3. The solution
4. Consequences

![[Pasted image 20241224123036.png]]

Other Patterns
• Module
• Revealing Module
• Revealing Constructor
• Callback
• Middleware
• Reactor
• Blockchain
• Scheduler
• Publisher Subscriber

![[Pasted image 20241224123115.png]]

### Anti-patterns:  
  
- **Definition**: Anti-patterns are bad solutions in software that should be avoided as they negatively impact applications.
- **Code Smells**: Recognizing anti-patterns can help identify "code smells" that indicate problematic code.
- **Examples in JavaScript and Node**: Avoid extending the prototype on an instance and using synchronous execution after initializing an app. Also, be aware of "callback hell" as a common anti-pattern.


### The singleton problem:  
  
- **Singleton Pattern**: Ensures only one instance of an object is created, preventing multiple instances.
- **Problem Example**: Multiple instances of a Logger class in different modules lead to incomplete log information.
- **Solution**: Using a singleton pattern can help maintain a single instance of the Logger, ensuring consistent logging across the application.

### Factory Method

![[Pasted image 20241224214839.png]]

- **Factory Method**: This design pattern defines an interface for creating an object but lets subclasses decide which class to instantiate. It encapsulates object creation, making the code more modular and easier to manage.
- **Implementation in JavaScript**: The video demonstrates how to create a `userFactory` function that decides which type of user (e.g., `shopper` or `employee`) to create based on the provided arguments.
- **Benefits**: Using the Factory pattern helps manage the complexity of object creation, especially as the application grows and requires more types of objects. It centralizes the creation logic, making the codebase cleaner and more maintainable.

### Builder pattern

![[Pasted image 20241224215857.png]]

- **Customization**: The Builder pattern allows for the creation of complex objects with various configurations by separating the construction process from the representation.
- **Telescoping Constructor Anti-pattern**: It addresses the problem of constructors with too many arguments, which can be confusing and hard to manage.
- **Implementation**: The video demonstrates how to use a `PersonBuilder` class to create instances of objects in a more readable and maintainable way, avoiding the pitfalls of the telescoping constructor.

### Adapter pattern:

![[Pasted image 20241224222053.png]]

- **Analogy**: The video uses the analogy of a skateboard and a snow skate to explain how an adapter works. Just like a snow skate adapts a skateboard for use on snow, an adapter in software allows incompatible classes to work together by converting one interface into another.
- **Purpose**: Adapters make incompatible classes compatible by keeping an object's interface but adapting it to a new environment or solution.
- **Implementation**: The video demonstrates how to build an adapter in JavaScript to allow code designed for a browser environment to work in a Node.js environment.

### Proxy pattern  

![[Pasted image 20241224234813.png]]

- **Proxy Definition**: A proxy is an object that controls access to another object, acting as a surrogate or placeholder.
- **Use Cases**: Proxies are useful for managing expensive objects, remote resources, data validation, security, caching, and logging.
- **Interface Requirement**: A proxy must provide the same interface as the original object, allowing the client to call the same methods on the proxy.

### Composite pattern  

![[Pasted image 20241224235528.png]]

- **Uniform Treatment**: The Composite pattern allows you to treat individual objects and compositions of objects uniformly, making it easier to work with complex tree structures.
- **Tree Structures**: It is particularly useful for organizing objects into tree structures to represent part-whole hierarchies, such as file systems where directories (branches) contain files (leaves).
- **Catalog Example**: The video uses a catalog example to illustrate how a composite can represent both individual items (leaves) and groups of items (branches), allowing operations like calculating totals and printing details to be applied uniformly.


### Decorator pattern  

![[Pasted image 20241225173628.png]]



- **Decorator Definition**: A decorator is a design pattern that allows you to dynamically attach additional properties and methods to existing objects.
- **Example**: The video uses the example of modifying a plain work van into a camper van by adding features like a bed, sink, and stove, rather than building a new van from scratch.
- **Flexibility**: Decorators provide a flexible alternative to subclassing for extending functionality, allowing for multiple modifications to be applied dynamically.
# Reference