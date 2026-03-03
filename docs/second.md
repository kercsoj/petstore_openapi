# Page 2

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

<table><thead><tr><th width="184.953125">Method</th><th width="149.61328125">Endpoint</th><th>Description</th></tr></thead><tbody><tr><td>GET</td><td><code>/pets</code></td><td>List all pets</td></tr><tr><td>GET</td><td><code>/pets/{id}</code></td><td>Get a pet by ID</td></tr><tr><td>POST</td><td><code>/pets</code></td><td>Create a new pet</td></tr><tr><td>PUT</td><td><code>/pets/{id}</code></td><td>Update a pet</td></tr><tr><td>DELETE</td><td><code>/pets/{id}</code></td><td>Delete a pet</td></tr></tbody></table>

## Response Codes

* `200` - Success
* `400` - Bad request
* `401` - Unauthorized
* `404` - Not found
* `500` - Server error

## Further Reading

* [OpenAPI Specification](https://swagger.io/specification/)
* [REST API Design Best Practices](https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design)

**Note**: This is example documentation only and does not reflect actual API endpoints.

[This link 1](four/) should be redirected via redirect clause.

[This link 2](four.md) should be redirected via redirect clause.

[This link 3](four/) should be redirected via redirect clause.

[This link 4](four.md) should be redirected via redirect clause.
