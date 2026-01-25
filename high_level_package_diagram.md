# HBnB Evolution – High-Level Package Diagram

```mermaid
classDiagram
    class PresentationLayer {
        +API
        +Services
    }

    class BusinessLogicLayer {
        +HBnBFacade
        +User
        +Place
        +Review
        +Amenity
    }

    class PersistenceLayer {
        +Repository
        +Database
    }

    PresentationLayer --> BusinessLogicLayer : uses Facade
    BusinessLogicLayer --> PersistenceLayer : CRUD operations
