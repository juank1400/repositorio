```mermaid
graph TD
    subgraph "Client"
        A[User / API Client]
    end

    subgraph "Quarkus Application Layer"
        B{MovieResource }
        C{MovieRepository)}
        D[Movie]
        E[Hibernate ORM / Panache]
    end

    subgraph "Data Layer"
        F[H2 In-Memory Database]
    end

    A -- HTTP (GET / POST) --> B
    B -- Uses --> C
    B -- Uses static methods e.g. listAll() --> D
    C -- Interacts with --> E
    D -- Maps to 'Movie' table via --> E
    E -- Reads/Writes to --> F
```
