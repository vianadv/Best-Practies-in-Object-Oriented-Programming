# Best-Practies-in-Object-Oriented-Programming
A comprehensive guide to Software Engineering best practices, covering OOP pillars, SOLID principles, Object Calisthenics, and DDD

# 🚀 Software Engineering Best Practices: OOP, SOLID & Clean Design

This repository is a compendium of my studies on how to write clean, maintainable, and high-quality code. It organizes fundamental concepts ranging from the pillars of Object-Oriented Programming (OOP) to strict code design rules and architecture.

## 🏛️ Fundamentals & Pillars

### Cohesion and Responsibility
A class should perform and possess only what makes sense for its existence. If a class validates data, saves information, and executes business rules all at once, it is doing too much and must be divided.

### Encapsulation
Hide internal processes. Those who use a method do not need to know how it works "under the hood," only how to interact with it. This allows internal logic to change without breaking the external components.

### Coupling
The secret is **low coupling**. We should always depend on stable abstractions (interfaces) rather than concrete implementations that change frequently.

---

## 💎 SOLID Principles

* **S - Single Responsibility:** A class should have one, and only one, reason to change.
* **O - Open/Closed:** Software entities should be open for extension, but closed for modification. Add new features by creating new files, not by altering existing ones.
* **L - Liskov Substitution:** Derived classes must be substitutable for their base classes without breaking the system.
* **I - Interface Segregation:** No client should be forced to depend on methods it does not use.
* **D - Dependency Inversion:** Depend on abstractions, not on concretions. High-level modules should not depend on low-level modules.

---

## 🏋️ Object Calisthenics (The "Clean Code" Workout)

A set of 9 strict rules to elevate the level of object-oriented design:

1.  **Only one level of indentation per method:** If you have an `if` inside a `for`, extract the content to a new method.
2.  **Don't use ELSE:** Use **Fail Fast** (throw errors early) and **Early Return** techniques. If the code hits a `return`, everything below it is ignored.
3.  **Wrap all primitives:** If a data type has rules or validations (like a Social Security Number or Email), it deserves its own class. **If data has a rule, it deserves a class.**
4.  **First-Class Collections:** A class that contains a collection should not have any other member variables.
5.  **One dot per line (Law of Demeter):** Do not talk to "strangers." Avoid long chains like `order.getCustomer().getAddress().getCity()`. Use `order.getCustomerCity()` instead.
6.  **Don't abbreviate:** Save confusion, not letters. Clear names prevent people from having to guess what the code does.
7.  **Keep entities small:** Ideally, keep classes between 50 to 200 lines. If you can't explain what a class does quickly, it is too large.
8.  **No more than two instance variables per class:** This forces high cohesion and the creation of new abstractions.
9.  **Tell, Don't Ask:** Do not use *getters* and *setters* to decide what to do outside the object. Tell the object what to do and let it manage its own state.

---

## 🏗️ Domain-Driven Design (DDD)

* **Ubiquitous Language:** Developers and business experts must speak the same language in the code.
* **Bounded Context:** The system should be divided into specific areas where terms have specific meanings.
* **Entities vs Value Objects:** Entities have a unique identity (ID); Value Objects are defined by their attributes and are immutable.
* **Aggregates:** A cluster of domain objects that can be treated as a single unit to ensure data integrity.

---

> "Simplicity is the ultimate sophistication." — Leonardo da Vinci
