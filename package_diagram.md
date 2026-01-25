classDiagram
    %% Presentation Layer
    class PresentationLayer {
        +API
        +Services
    }

    %% Business Logic Layer
    class BusinessLogicLayer {
        +HBnBFacade
        +User
        +Place
        +Review
        +Amenity
    }

    %% Persistence Layer
    class PersistenceLayer {
        +Repository
        +Database
    }

    %% Relationships
    PresentationLayer --> BusinessLogicLayer : uses Facade
    BusinessLogicLayer --> PersistenceLayer : CRUD operations
