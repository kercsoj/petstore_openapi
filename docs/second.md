# API Documentation

This page contains detailed information about the Petstore API endpoints.

## Authentication

All API requests require authentication. You can authenticate using API keys or OAuth2.

### API Keys

To use API key authentication:

1. Register an account on the developer portal
2. Generate your API key in the dashboard
3. Include the API key in the header of your requests

Example:

```http
GET /v2/pets HTTP/1.1
Host: api.petstore.example.com
X-API-KEY: your_api_key_here
```

## Endpoints

### Pets

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/pets` | List all pets |
| GET | `/pets/{id}` | Get a pet by ID |
| POST | `/pets` | Create a new pet |
| PUT | `/pets/{id}` | Update a pet |
| DELETE | `/pets/{id}` | Delete a pet |

## Response Codes

- `200` - Success
- `400` - Bad request
- `401` - Unauthorized
- `404` - Not found
- `500` - Server error

## Further Reading

* [OpenAPI Specification](https://swagger.io/specification/)
* [REST API Design Best Practices](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

**Note**: This is example documentation only and does not reflect actual API endpoints.

Change

<a href="four">This link 1</a> should be redirected via redirect clause.

<a href="four.md">This link 2</a> should be redirected via redirect clause.

[This link 3](four) should be redirected via redirect clause.
