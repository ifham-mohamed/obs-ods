
2024-11-23 21:56

Status:

Tags:

https://blog.cleancoder.com/


![[Pasted image 20241123224818.png]]
# Technical - Clean Architecture

### Clean Architecture Overview

**Clean Architecture** is a software design philosophy introduced by Robert C. Martin (Uncle Bob) to ensure software systems are:

- **Maintainable**: Easy to change and adapt.
- **Testable**: Easily unit-tested due to clear separation of concerns.
- **Independent**: Unaffected by frameworks, UI, databases, or external systems.
- **Stable**: Core business logic is resilient to external changes.

At its core, Clean Architecture emphasizes **layered design** and **dependency rules**, where **high-level policies (business rules)** are independent of **low-level details (frameworks, databases, etc.)**.

---

### **Key Principles**

1. **Separation of Concerns**:
    - Divide the application into distinct layers with clear responsibilities.
2. **Dependency Inversion**:
    - Inner layers (core business logic) should not depend on outer layers (UI, database, etc.). Instead, the outer layers depend on abstractions defined in the core layers.
3. **Testability**:
    - Core logic can be tested independently of infrastructure or UI.

---

### **The Layers**

1. **Entities (Core Business Rules)**:
    - Represent the core of the system, such as business objects and enterprise-wide rules.
    - Independent of frameworks or technology.
2. **Use Cases (Application Rules)**:
    - Handle the application-specific business rules.
    - Orchestrate the interaction between entities and other layers.
    - Example: "Process a payment" or "Register a user."
3. **Interface Adapters (Controllers/Presenters/Gateways)**:
    - Adapt the data from the external systems (UI, database, APIs) to the use cases.
    - Example: Converting a user form submission into a format the use case understands.
4. **Frameworks and Drivers (External Systems)**:
    - Includes tools, libraries, frameworks, and external systems (e.g., React, Node.js, databases).
    - They implement the interfaces defined in the core layers.

---

### **Dependency Rule**

- Dependencies flow **inward**, from outer layers to inner layers.
- Inner layers know nothing about the outer layers.

---

### **How to Use Clean Architecture**

1. **Start with the Core**:
    - Define the **Entities** and their business logic.
    - Define **Use Cases** that orchestrate the system's primary behavior.
2. **Abstract the External Details**:
    - Define interfaces for external dependencies (e.g., repositories, APIs).
    - Implement these interfaces in the outer layers.
3. **Use Dependency Injection**:
    - Pass dependencies (e.g., database connections) into the application rather than hardcoding them.
4. **Test the Core in Isolation**:
    - Write unit tests for **Entities** and **Use Cases** without worrying about the UI or database.

---

### **Where to Use Clean Architecture**

1. **Scalable Applications**:
    - Projects expected to grow in complexity, such as e-commerce platforms, banking systems, or SaaS products.
2. **Long-Lived Systems**:
    - Applications requiring regular updates or adaptations (e.g., healthcare systems).
3. **Test-Driven Development (TDD)**:
    - Systems where automated tests are a priority, making core logic easily testable.
4. **Multi-Platform Apps**:
    - Applications with multiple frontends (web, mobile) can reuse the same business logic.

---

### **Why Use Clean Architecture**

1. **Flexibility**:
    - Swap out technologies (e.g., replace the database) without impacting the core logic.
2. **Maintainability**:
    - Developers can focus on specific layers without being overwhelmed by the entire system.
3. **Testability**:
    - Core logic can be tested independently of external dependencies.
4. **Resilience to Change**:
    - Business rules remain stable even as external systems evolve.

---

### **Real-World Example**

#### **Scenario**: Building a Library Management System

1. **Entities**:
    - Define core objects like `Book`, `User`, and their relationships (e.g., `borrowBook()`, `returnBook()`).
2. **Use Cases**:
    - `BorrowBookUseCase`: Checks if a book is available and allows a user to borrow it.
    - `ReturnBookUseCase`: Marks the book as returned and updates the user's borrowing history.
3. **Interface Adapters**:
    - A REST API controller receives a "borrow book" request, validates the input, and calls `BorrowBookUseCase`.
    - Database gateways fetch and update `Book` and `User` records.
4. **Frameworks and Drivers**:
    - Use frameworks like Express.js for API handling or Sequelize for database interaction.
    - Implement gateway interfaces defined in the core to interact with the database.

---

#### **How Clean Architecture Applies**

- **Testing**: Unit-test `BorrowBookUseCase` without needing a database or API.
- **Resilience**: If you switch from SQL to NoSQL, only the database gateway implementation changes.
- **Reuse**: Use the same `BorrowBookUseCase` for a web app and a mobile app.

---

### Example Code

**Entities**:

```javascript
class Book {
  constructor(id, title, isAvailable = true) {
    this.id = id;
    this.title = title;
    this.isAvailable = isAvailable;
  }

  markBorrowed() {
    if (!this.isAvailable) throw new Error('Book is already borrowed.');
    this.isAvailable = false;
  }

  markReturned() {
    this.isAvailable = true;
  }
}
```

**Use Case**:

```javascript
class BorrowBookUseCase {
  constructor(bookRepository, userRepository) {
    this.bookRepository = bookRepository;
    this.userRepository = userRepository;
  }

  async execute(bookId, userId) {
    const book = await this.bookRepository.findById(bookId);
    const user = await this.userRepository.findById(userId);

    if (!book.isAvailable) throw new Error('Book is not available.');
    book.markBorrowed();

    await this.bookRepository.save(book);
    user.borrowBook(bookId);
    await this.userRepository.save(user);
  }
}
```

**Interface Adapter**:

```javascript
class ExpressController {
  constructor(borrowBookUseCase) {
    this.borrowBookUseCase = borrowBookUseCase;
  }

  async borrowBook(req, res) {
    try {
      const { bookId, userId } = req.body;
      await this.borrowBookUseCase.execute(bookId, userId);
      res.status(200).send('Book borrowed successfully!');
    } catch (error) {
      res.status(400).send(error.message);
    }
  }
}
```

---

### Conclusion

Clean Architecture is powerful for creating scalable, maintainable, and testable software systems. Use it when building systems where core business logic should remain stable despite changes in technology or external systems. Real-world examples like library systems, e-commerce, or banking platforms benefit greatly from this architecture.


# Clean Architecture Application in Node.js
### Summary
Clean Architecture in Node.js helps decouple business logic from external dependencies, enabling easier changes and maintenance.

### Highlights
- 🏗️ Clean Architecture shields business logic from external changes enhances code maintainability with  importance of modular and maintainable software systems..  
- 🔄 Swapping databases becomes simple with proper architecture.  
- ⚙️ Interfaces and dependency injection reduce coupling.  
- 📦 Entities encapsulate business rules and validation.  
- 🛠️ Use cases organize application logic effectively.  
- 📧 Email notifications can be decoupled from business logic.  


- 📦 Entity Creation: Emphasizes creating an entity class for the product to encapsulate business rules.
- 🔄 Use Cases: Discusses the need for a use case layer to handle business logic separate from controllers.
- 🚀 Dependency Injection: Introduces dependency injection using interfaces for flexibility and testing.
- 📬 External Libraries: Shows integration of external services like email and message brokers for notifications.
- ✅ Testing Focus: Highlights the importance of testability in each architecture layer.
- 🔄 Principles of independence from frameworks, UI, databases, and external packages.
- 🧪 Emphasis on testability of business logic without external dependencies.
- ⚙️ Practical demonstration of a simple Express application before and after applying Clean Architecture.
- 🚧 Identification of common problems in tightly coupled code and how Clean Architecture resolves them.

### Key Insights
- 🔒 **Decoupling Business Logic**: Clean Architecture emphasizes keeping business logic isolated from external libraries, making code more adaptable to changes. This approach reduces technical debt over time.  
- 🔄 **Ease of Database Swapping**: By applying Clean Architecture principles, switching databases (e.g., from MySQL to MongoDB) can be done with minimal code changes, significantly improving flexibility.  
- 🧩 **Use of Interfaces**: Implementing interfaces allows for a clear contract between components, enhancing code readability and making unit testing more straightforward. This promotes better software design practices.  
- 🏢 **Role of Entities**: Entities encapsulate data and enforce business rules, ensuring that the application logic adheres to specific criteria before executing actions. This leads to more robust application behavior.  
- ⚙️ **Importance of Use Cases**: Organizing application logic into use cases clarifies the responsibilities of different parts of the code, leading to improved maintainability and scalability.  
- 📧 **Decoupling Notifications**: By delegating notification responsibilities to dedicated functions, business logic remains clean, allowing for easier updates to notification methods without impacting core functionalities.  
- 📚 **Learning Curve**: Although Clean Architecture concepts can be abstract, practical implementation examples clarify the benefits and encourage developers to adopt these practices for better software engineering outcomes.  
- 📚 **Separation of Concerns:** Clean Architecture promotes the separation of different concerns in the application, making the codebase more maintainable and scalable. This leads to clearer responsibilities for each layer, enhancing code quality.
- 🔄 **Flexibility in Implementation:** By using interfaces, you can swap out implementations without affecting the rest of the application. This is crucial for adapting to changes in technology or requirements over time.
- 🔍 **Testability:** Each layer can be tested independently. This enables developers to write unit tests for business logic without worrying about the implementation details of the framework or database.
- 🛠️ **Dependency Management:** Utilizing dependency injection simplifies managing dependencies, as it allows for easier mocking and stubbing during tests, leading to more robust code.
- 📈 **Business Logic Encapsulation:** By creating entities that encapsulate business rules, the application becomes more aligned with business requirements, ensuring relevant validation and logic are consistently applied.
- 🌐 **Integration with External Services:** The architecture effectively accommodates integration with external services, facilitating notifications and interactions without tightly coupling the business logic with those services.
- 🔗 **Future-Proofing:** The design choices made using Clean Architecture provide a foundation that can adapt to future needs, whether that involves changing the database, the web framework, or integrating new functionalities.
- 📖 Clean Architecture promotes a clear separation of concerns, enhancing maintainability and flexibility in software development. This ensures that changes in one area have minimal impact on others.
- 🔄 The concentric circle model visually represents how core business logic remains insulated from peripheral concerns, allowing for easier updates and modifications without affecting the overall system.
- 🧪 Testability is a fundamental principle; business rules should be independently testable, which significantly improves the reliability of the software as it evolves.
- 🏗️ By adhering to the independence principle, developers can swap out frameworks, databases, or even UI components without needing to rewrite core business logic, thus saving time and reducing errors.
- 🚧 Common pitfalls in traditional architectures include tightly coupled components that make testing and changing implementations cumbersome. Clean Architecture mitigates these risks.
- ⚙️ Practical implementation examples help solidify the understanding of theoretical concepts, demonstrating how Clean Architecture can be applied effectively in real-world scenarios.
- 📊 The video encourages viewers to explore the provided repository to see before-and-after comparisons, reinforcing the importance of Clean Architecture in practical coding environments.





![[NoteGPT_MindMap_1732382673914.png]]
![[NoteGPT_MindMap_1732379268654.png]]
![[NoteGPT_MindMap_1732380585706.png]]
# Reference