```mermaid
sequenceDiagram
    autonumber
    
    participant User
    participant Frontend
    participant API
    participant Backend
    participant Database

    User->>Frontend: Login Request
    Frontend->>API: Authenticate
    API->>Database: Validate User
    Database-->>API: User Valid
    API-->>Frontend: Auth Token
    Frontend-->>User: Dashboard Access

    User->>Frontend: Upload File
    Frontend->>API: Send File
    API->>Backend: Process & Scan
    Backend->>Database: Store Results
    Backend-->>API: Scan Complete
    API-->>Frontend: Return Results
    Frontend-->>User: Display Report
```