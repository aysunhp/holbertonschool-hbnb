# HBnB Evolution – Technical Documentation (Part 1)

## 1. Introduction

This document provides the complete technical documentation for **HBnB Evolution**,
a simplified AirBnB-like application.  
The purpose of this document is to serve as a **blueprint for the implementation phases**
by clearly defining the system architecture, business logic, and interaction flow
between components.

The documentation covers:
- High-level architecture using a layered approach
- Detailed design of the Business Logic layer
- Interaction flow for core API calls using sequence diagrams

This document will be used as a reference throughout the development lifecycle.

---

## 2. High-Level Architecture

### 2.1 Overview

The HBnB Evolution application follows a **layered architecture** composed of three
main layers:

- **Presentation Layer**
- **Business Logic Layer**
- **Persistence Layer**

Communication between layers is simplified using the **Facade Pattern**, ensuring
separation of concerns and maintainability.

---

### 2.2 High-Level Package Diagram

See `high_level_package_diagram.md` for detailed diagram.

---

### 2.3 Architecture Explanation

#### Presentation Layer
Handles user interaction through API endpoints and services.  
This layer does **not** contain business rules and communicates only with the
Business Logic layer via the `HBnBFacade`.

#### Business Logic Layer
Contains the core entities and rules of the application.
The `HBnBFacade` acts as a unified entry point, coordinating operations across entities.

#### Persistence Layer
Responsible for data storage and retrieval.
All database operations are abstracted through repositories.

---

## 3. Business Logic Layer – Class Design

### 3.1 Overview

The Business Logic layer defines the core entities of the HBnB system:
- User
- Place
- Review
- Amenity

All entities inherit common attributes from a base class to ensure consistency.

### 3.2 Detailed Class Diagram

See `business_logic_class_diagram.md` for Mermaid.js diagram.

---

### 3.3 Entity Descriptions

- **User**: Application user; can register, update profile, admin flag.
- **Place**: Property listed by a user; may have multiple amenities.
- **Review**: Feedback for a place; linked to user and place.
- **Amenity**: Features associated with places (WiFi, Pool, etc.).
- **BaseEntity**: Provides common attributes like id, created_at, updated_at.

---

## 4. API Interaction Flow – Sequence Diagrams

See `sequence_diagrams.md` for diagrams covering:

1. User Registration  
2. Place Creation  
3. Review Submission  
4. Fetching a List of Places

---

## 5. Conclusion

This technical document provides a complete overview of the HBnB Evolution
application architecture and design.  
Combining layered architecture, Facade pattern, and clear entity modeling
ensures scalability, maintainability, and clarity for future implementation.
