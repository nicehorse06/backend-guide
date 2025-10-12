## 🧩 Object-Oriented Programming (OOP)

### 🧱 Core Concepts
- **Encapsulation**  
  - Bundling data (attributes) and methods into a single unit (class).  
  - Controls access via visibility modifiers (`private`, `protected`, `public`).  
  - Promotes data integrity and reduces coupling.

- **Abstraction**  
  - Hiding internal details while exposing necessary interfaces.  
  - Allows focusing on *what* an object does rather than *how*.  
  - Implemented via abstract classes or interfaces.

- **Inheritance**  
  - Enables code reuse by allowing subclasses to extend parent classes.  
  - Supports hierarchical relationships (e.g., `class Dog(Animal)`).
  - Risks: tight coupling, fragile base class problem.

- **Polymorphism**  
  - “Many forms” — same interface, different implementations.  
  - Method overriding (runtime) and overloading (compile time, in some languages).  
  - Enables flexible and extensible design.

- **Duck Typing (Python-specific)**  
  - Type is determined by behavior, not explicit inheritance.  
  - “If it walks like a duck and quacks like a duck, it’s a duck.”  
  - Encourages flexibility but requires careful testing and documentation.

---

### 💡 Benefits of OOP
- Modular structure → easier maintenance and testing.  
- Code reusability through inheritance and composition.  
- Abstraction hides complexity from higher-level modules.  
- Easier scalability and collaboration (clear boundaries).  
- Enables design patterns and dependency management.  

---

### 🧭 SOLID Principles
1. **S — Single Responsibility Principle (SRP)**  
   Each class should have only one reason to change.  
   → Keeps modules focused and easier to maintain.

2. **O — Open/Closed Principle (OCP)**  
   Software entities should be *open for extension* but *closed for modification*.  
   → Achieved using interfaces, inheritance, or composition.

3. **L — Liskov Substitution Principle (LSP)**  
   Subclasses should be replaceable by their base class without altering correctness.  
   → Example: Derived class must not violate parent behavior or expected return types.

4. **I — Interface Segregation Principle (ISP)**  
   Clients should not depend on interfaces they do not use.  
   → Prefer multiple small, specific interfaces over a single large one.

5. **D — Dependency Inversion Principle (DIP)**  
   High-level modules should not depend on low-level modules; both depend on abstractions.  
   → Enables flexibility and testability through dependency injection.

---

### 🔌 Dependency Injection (DI)
- **Definition**: Supplying dependencies (objects, services) from outside a class instead of creating them inside.  
- **Purpose**: Reduces coupling and increases testability (e.g., mocking).  
- **Types of Injection**
  - Constructor Injection (recommended)
  - Setter Injection
  - Interface Injection (less common)
- **Example (Python)**:
  ```python
  class Database:
      def connect(self): pass

  class UserService:
      def __init__(self, db: Database):
          self.db = db  # dependency injected externally
  ```
- **Framework Examples**:
  - Spring (Java), NestJS (TypeScript), FastAPI (Python’s Depends)

---

### 🧩 Interfaces and Abstract Classes
- **Interface**
  - Defines a contract — *what* methods a class should implement.
  - Promotes polymorphism and separation of concerns.
  - Python uses `abc` module for abstract base classes.
- **Abstract Class**
  - Can contain both abstract (unimplemented) and concrete (implemented) methods.
  - Cannot be instantiated directly.
- **Use Case**
  - Interfaces for interchangeable behaviors (e.g., payment gateways)
  - Abstract classes for shared logic + enforced methods.

---

### ⚙️ Practical Insights
- Prefer **composition over inheritance** to reduce coupling.
- Use **interfaces** or **abstract base classes** for interchangeable logic (e.g., multiple storage backends).
- Avoid deep inheritance chains (hard to maintain).
- Apply **design patterns** (Strategy, Factory, Observer) to implement SOLID.
- Use **encapsulation** to enforce clear API boundaries.
- In Python, leverage **dataclasses** for clean object definitions.
- **Unit testing** becomes simpler when dependencies are injected or mocked.
- Beware of **tight coupling** caused by direct class instantiation.

---

### 🚀 Advanced / Extended Topics
- **Design Patterns**
  - Creational: Singleton, Factory, Builder
  - Structural: Adapter, Decorator, Composite
  - Behavioral: Strategy, Observer, Command
- **Composition vs Inheritance**
  - Composition = “has-a” relationship  
  - Inheritance = “is-a” relationship
- **Mixins in Python**
  - Lightweight multiple inheritance for specific functionality.
- **OOP vs Functional Programming**
  - OOP focuses on state and behavior encapsulation.
  - FP emphasizes immutability and pure functions.
- **OOP in Distributed Systems**
  - DTOs (Data Transfer Objects)
  - Repository & Service layer patterns
- **OOP and Testing**
  - Mocking interfaces instead of concrete classes.
  - Dependency injection for easier test isolation.

---

### ⚡ Quick Summary
> **OOP organizes code into classes and objects for modularity, reusability, and maintainability.**  
> Key pillars: **Encapsulation, Abstraction, Inheritance, Polymorphism.**  
> Follow **SOLID** principles for scalable architecture.  
> Use **Dependency Injection** and **Interfaces** to reduce coupling.  
> Prefer **composition over inheritance** for cleaner, more flexible designs.
