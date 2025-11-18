# Page 1

Welcome to the Petstore OpenAPI documentation!

## Features

* RESTful API
* OpenAPI Specification
* Example endpoints

## Getting Started

1. Clone the repository
2. Install dependencies
3. Run the server

## Example Code

```bash
git clone https://github.com/example/petstore_openapi.git
cd petstore_openapi
```

## Mermaid support

```mermaid
erDiagram
    ProgramEntity ||--o{ ProgramRequirementEntity : "has"
    ProgramEntity ||--o{ ProgramEnrollmentEntity : "has"
    ProgramEntity }o--|| UserEntity : "owned by"
    
    ProgramCourseEntity ||--o{ ProgramRequirementEntity : "is dependency in"
    ProgramCourseEntity ||--o{ ProgramRequirementEntity : "is dependent in"
    
    ProgramRequirementEntity }o--|| ProgramEntity : "belongs to"
    ProgramRequirementEntity ||--o{ ProgramProgressEntity : "tracked in"
    
    ProgramEnrollmentEntity }o--|| ProgramEntity : "for"
    ProgramEnrollmentEntity }o--|| UserEntity : "belongs to"
    ProgramEnrollmentEntity ||--o{ ProgramProgressEntity : "has"
    
    ProgramProgressEntity }o--|| ProgramEnrollmentEntity : "belongs to"
    ProgramProgressEntity }o--|| ProgramRequirementEntity : "tracks"

    ProgramEntity {
        UUID id
        string name
        Date createdAt
        Date updatedAt
    }
    
    ProgramCourseEntity {
        UUID id
        string canvasCourseId
        string canvasUrl
        Date createdAt
        Date updatedAt
    }
    
    ProgramRequirementEntity {
        UUID id
        Date createdAt
        Date updatedAt
    }
    
    ProgramEnrollmentEntity {
        UUID id
        Date createdAt
        Date updatedAt
    }
    
    ProgramProgressEntity {
        UUID id
        Date createdAt
        Date updatedAt
    }
    
    UserEntity {
        UUID id
    }
```

## License

See the [LICENSE](../LICENSE/) file for details.
