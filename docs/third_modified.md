# API Examples

This document provides practical examples for using the Petstore API.

## Authentication Example

Before using the API, you need to authenticate. Here's a simple example:

```bash
curl -X POST https://petstore.example.com/api/v1/auth \
  -H "Content-Type: application/json" \
  -d '{"username": "user1", "password": "password123"}'
```

The API will return a token:

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "expires_in": 3600
}
```

## Retrieving Pets

### List All Available Pets

```bash
curl -X GET https://petstore.example.com/api/v1/pets \
  -H "Authorization: Bearer YOUR_TOKEN"
```

Response:

```json
{
  "data": [
    {
      "id": 1,
      "name": "Buddy",
      "status": "available",
      "category": "dog",
      "tags": ["friendly", "trained"]
    },
    {
      "id": 2,
      "name": "Whiskers",
      "status": "available",
      "category": "cat",
      "tags": ["playful"]
    }
  ],
  "pagination": {
    "total": 45,
    "page": 1,
    "per_page": 2
  }
}
```

### Find Pets by Status

```bash
curl -X GET https://petstore.example.com/api/v1/pets?status=available \
  -H "Authorization: Bearer YOUR_TOKEN"
```

## Adding a New Pet

```bash
curl -X POST https://petstore.example.com/api/v1/pets \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "name": "Max",
    "category": "dog",
    "status": "available",
    "tags": ["young", "playful"]
  }'
```

Response:

```json
{
  "id": 3,
  "name": "Max",
  "category": "dog",
  "status": "available",
  "tags": ["young", "playful"],
  "created_at": "2025-06-26T10:30:00Z"
}
```

## Updating a Pet

```bash
curl -X PUT https://petstore.example.com/api/v1/pets/3 \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -d '{
    "name": "Max",
    "category": "dog",
    "status": "adopted",
    "tags": ["young", "playful", "adopted"]
  }'
```

## Deleting a Pet

```bash
curl -X DELETE https://petstore.example.com/api/v1/pets/3 \
  -H "Authorization: Bearer YOUR_TOKEN"
```

## Handling Errors

If you make an invalid request, the API will return an error:

```bash
curl -X GET https://petstore.example.com/api/v1/pets/999 \
  -H "Authorization: Bearer YOUR_TOKEN"
```

Response:

```json
{
  "error": {
    "code": "RESOURCE_NOT_FOUND",
    "message": "Pet with ID 999 not found",
    "status": 404
  }
}
```

## Further Examples

For more examples, refer to our [API Reference](second.md) or try out these endpoints in the interactive API explorer.