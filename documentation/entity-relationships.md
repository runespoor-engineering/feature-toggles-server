# Entity Relationships Diagram

```mermaid
erDiagram
    User {
        uuid id
        uuid[] projectIds
        string username
        string email
        enum role
    }

    Project {
        uuid id
        uuid[] userIds
        uuid[] environmentIds
        string name
        uuid accessKey
    }

    Environment {
        uuid id
        uuid[] flags
        string name
    }

    Flag {
        uuid id
        string name
        boolean enabled
        json meta
        string description
        enum modificationLevel
    }

    User }|--o{ Project : creates
    Project ||--o{ Environment : contains
    Environment ||--o{ Flag : contains
```