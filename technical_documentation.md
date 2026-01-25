## 1. Introduction

This document provides a comprehensive technical overview of the HBnB application architecture.
It serves as a blueprint for the implementation phase by describing the system structure, core business logic,
and the interaction flow between components.

The document includes:

- A high-level package diagram describing the layered architecture
- A detailed class diagram for the Business Logic layer
- Sequence diagrams illustrating key API interactions

## 2. High-Level Architecture

The HBnB application follows a three-layered architecture:

- Presentation Layer: Handles API requests and user interaction
- Business Logic Layer: Contains core domain models and business rules
- Persistence Layer: Manages data storage and retrieval

The facade pattern is used to provide a simplified interface between the Presentation
layer and the Business Logic layer.

```mermaid
classDiagram
class PresentationLayer {
    <<Presentation>>
    +API Services
}
class BusinessLogicLayer {
    <<BusinessLogic>>
    +Models
}
class PersistenceLayer {
    <<Persistence>>
    +Database Access
}

PresentationLayer --> BusinessLogicLayer : Facade Pattern
BusinessLogicLayer --> PersistenceLayer : Data Operations
```

## 3. Business Logic Layer

This section describes the core domain entities of the HBnB application.
These classes encapsulate the business rules and data structures used throughout the system.

```mermaid
classDiagram
class User {
    +UUID id
    +string email
    +string password
    +datetime created_at
    +datetime updated_at
}

class Place {
    +UUID id
    +string name
    +UUID user_id
}

class Review {
    +UUID id
    +string text
    +UUID user_id
    +UUID place_id
}

class Amenity {
    +UUID id
    +string name
}

User "1" --> "0..*" Place : owns
User "1" --> "0..*" Review : writes
Place "1" --> "0..*" Review : has
Place "0..*" --> "0..*" Amenity : includes
```

The User entity represents application users.
Places are owned by users and can receive reviews.
Amenities represent features associated with places.

## 4. API Interaction Flow

This section illustrates how different layers of the system interact
to fulfill key API requests.

```mermaid
sequenceDiagram
participant User
participant API
participant Facade
participant Database

User->>API: POST /users
API->>Facade: create_user()
Facade->>Database: insert User
Database-->>Facade: user_id
Facade-->>API: success
API-->>User: 201 Created
```

This sequence shows how a new user is registered and persisted using the facade.