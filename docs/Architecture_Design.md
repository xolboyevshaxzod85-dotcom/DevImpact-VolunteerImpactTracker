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
## Architecture Decision Records (ADRs)

### ADR 1: Selection of the MERN Stack for Volunteer Impact Tracker

**Status:** Accepted

**Context:**
The Volunteer Impact Tracker requires a responsive web application to manage user roles, project charters, and risk matrices. We need a technology stack that supports rapid development, handles dynamic JSON data natively, and provides a component-driven UI for complex multi-step forms.

**Decision:**
We have selected the MERN stack (MongoDB, Express.js, React.js, Node.js) based on the following justifications:
* **MongoDB (Database):** A NoSQL document database is perfectly suited for storing hierarchical, document-based data like Project Charters and nested Risk Matrices. It allows us to iterate quickly without rigid relational schema migrations.
* **Node.js & Express (API Server):** Using JavaScript on the backend unifies our development language across the entire project. Express provides a lightweight, highly customizable framework for building our RESTful APIs and integrating our design patterns (e.g., Controllers and Services).
* **React.js (Frontend):** React's component-based architecture is ideal for our UI requirements, specifically the interactive multi-step Charter Creation Form and the dynamic KPI Dashboard. It ensures efficient state management and rapid DOM updates.

**Consequences:**
* **Positive:** Unified codebase (JavaScript/JSON top to bottom), rapid prototyping, and highly scalable component structure.
* **Risk Mitigation:** Since MongoDB lacks strict schema enforcement at the database level, we mitigate data integrity risks by using **Mongoose** for strict application-level validation.
