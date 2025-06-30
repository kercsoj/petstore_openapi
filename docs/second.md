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

<table><thead><tr><th valign="top">Method</th><th valign="top">Endpoint</th><th>Description</th></tr></thead><tbody><tr><td valign="top">GET</td><td valign="top"><code>/pets</code></td><td><p>List all pets</p><p></p><p>List all pets</p><p></p><p>List all pets</p><p></p><p>List all pets</p></td></tr><tr><td valign="top">GET</td><td valign="top"><code>/pets/{id}</code></td><td>Get a pet by ID</td></tr><tr><td valign="top">POST</td><td valign="top"><code>/pets</code></td><td>Create a new pet</td></tr><tr><td valign="top">PUT</td><td valign="top"><code>/pets/{id}</code></td><td>Update a pet</td></tr><tr><td valign="top">DELETE</td><td valign="top"><code>/pets/{id}</code></td><td>Delete a pet</td></tr></tbody></table>

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
