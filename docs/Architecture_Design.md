# Architecture & Design Patterns

## Design Patterns Applied

In the development of the Volunteer Impact Tracker, our team implemented the following design patterns to ensure scalability, maintainability, and clean code architecture:

### 1. Singleton Pattern
* **Application:** Database Connection Management (MongoDB).
* **Justification:** We applied the Singleton pattern to the database connection module. This guarantees that only a single instance of the database connection is created and shared across the entire Node.js server lifecycle. This approach prevents memory leaks, optimizes connection pooling, and reduces server load.

### 2. Factory Method
* **Application:** User Role Creation (Project Manager vs. Volunteer).
* **Justification:** The system handles multiple user types with distinct permissions. Instead of writing complex conditional logic (`if/else`), we utilize a UserFactory. During registration, the factory dynamically instantiates the correct user model with appropriate access rights, adhering to the Open/Closed Principle.

### 3. Adapter Pattern
* **Application:** External Email Service Integration.
* **Justification:** Our system sends automated notifications (e.g., Charter Ratification alerts) using an external email provider (SendGrid). By implementing an `EmailAdapter`, we decoupled our core business logic from the specific third-party API. If we decide to switch to another provider (like AWS SES) in the future, we only need to write a new adapter without modifying the core system.
