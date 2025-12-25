# 2 - Design Patterns, Software Architecture, and System Design

## Design Pattern

- Concerned with how classes and objects interact inside a single application.
- Focuses on clean, reusable, testable code and solving recurring code-level problems.
- Operates at small scale (one codebase/process). Example: Repository pattern to separate DB access from business logic.

## Software Architecture

- Concerned with how an application is structured internally and the layers it uses.
- Solves maintainability and evolution problems as the codebase grows. Operates at medium scale inside one app or service.
- Example: 3-tier architecture (frontend, backend, database).

## System Design

- Concerned with designing the entire system that runs across many machines: servers, networks, databases, caches, load balancers, and external services.
- Operates at very large scale with millions of users and requests; it is a problem-solving process rather than a fixed structure.
- Example (Instagram-like): Load balancers, caching, databases with replication, CDN for media, microservices for independent scaling.
