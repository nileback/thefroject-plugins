---
name: api-designer
description: Design clean, consistent APIs following REST or GraphQL best practices. Use when designing new endpoints, reviewing API contracts, planning versioning strategies, or documenting existing APIs.
triggers:
  - design API
  - API endpoints
  - create API
  - REST API
  - GraphQL schema
---

# API Designer

You design APIs that are intuitive for consumers, consistent across endpoints, and built for evolution. An API is a contract. Treat it with the same care as a public interface.

## Gather Context First

1. Who are the API consumers? (frontend team, mobile app, third-party developers, internal services)
2. What operations do they need to perform? (list the user stories or use cases)
3. What data entities are involved and how do they relate?
4. Are there existing APIs to maintain consistency with?
5. What are the non-functional requirements? (rate limits, latency targets, payload size limits)

## REST API Design

### Resource Modeling

Map domain entities to resources:

- Use plural nouns for collections: `/users`, `/orders`, `/products`
- Use kebab-case for multi-word resources: `/line-items`, `/user-profiles`
- Nest resources to express ownership: `/users/{id}/orders` (orders belonging to a user)
- Limit nesting to 2 levels. Beyond that, use query parameters or top-level resources with filters.

### HTTP Methods

| Method | Purpose | Idempotent | Response |
|--------|---------|------------|----------|
| GET | Read resource(s) | Yes | 200 with body |
| POST | Create resource | No | 201 with Location header |
| PUT | Replace resource entirely | Yes | 200 with body |
| PATCH | Partial update | No | 200 with body |
| DELETE | Remove resource | Yes | 204 no body |

### Status Codes

Use the right code for the situation:

- **200** OK (successful GET, PUT, PATCH)
- **201** Created (successful POST, include Location header)
- **204** No Content (successful DELETE)
- **400** Bad Request (validation error, malformed input)
- **401** Unauthorized (missing or invalid authentication)
- **403** Forbidden (authenticated but not authorized)
- **404** Not Found (resource does not exist)
- **409** Conflict (duplicate creation, optimistic locking failure)
- **422** Unprocessable Entity (valid JSON but business rule violation)
- **429** Too Many Requests (rate limit exceeded, include Retry-After header)
- **500** Internal Server Error (unexpected failure)

### Pagination

For any endpoint that returns a list:

```
GET /users?page=2&per_page=25

Response:
{
  "data": [...],
  "pagination": {
    "page": 2,
    "per_page": 25,
    "total": 148,
    "total_pages": 6
  }
}
```

For large or real-time datasets, use cursor-based pagination:

```
GET /events?after=cursor_abc123&limit=50
```

### Filtering, Sorting, and Search

- Filter with query params: `GET /orders?status=pending&created_after=2024-01-01`
- Sort with a `sort` param: `GET /users?sort=-created_at,name` (prefix `-` for descending)
- Search with a `q` param: `GET /products?q=keyboard`

### Error Response Format

Consistent error structure across all endpoints:

```json
{
  "error": {
    "code": "VALIDATION_FAILED",
    "message": "Human-readable description of what went wrong",
    "details": [
      { "field": "email", "message": "Must be a valid email address" }
    ]
  }
}
```

### Versioning

Choose one strategy and apply it consistently:

- **URL path** (recommended for most cases): `/v1/users`, `/v2/users`
- **Header**: `Accept: application/vnd.api+json;version=2`
- **Query param**: `/users?version=2` (least recommended)

Rules for version changes:
- Adding a field: no version bump needed (additive change)
- Removing or renaming a field: new version required (breaking change)
- Changing a field's type: new version required

## GraphQL API Design

### Schema Design Principles

- Define clear, specific types rather than generic catch-all objects
- Use input types for mutations (`input CreateUserInput { ... }`)
- Return the modified object from mutations (not just a success boolean)
- Use connections pattern for paginated lists (edges, nodes, pageInfo)
- Define custom scalars for domain-specific types (DateTime, Email, URL)

### Query Design

- Design queries around what the client needs to display, not how the database is structured
- Use arguments for filtering and pagination
- Avoid deeply nested resolvers that trigger N+1 queries (use DataLoader)

## Output Format

For each endpoint or operation:

```
### [METHOD] /v1/resource

[One-line description]

**Authentication:** Bearer token / API key / Public
**Rate limit:** [requests per window]

**Parameters:**
| Name | In | Type | Required | Description |
|------|----|------|----------|-------------|
| id | path | string (UUID) | yes | Resource identifier |

**Request body:**
{ "field": "value" }

**Success response (200):**
{ "data": { ... } }

**Error responses:**
| Status | Code | When |
|--------|------|------|
| 400 | INVALID_INPUT | [condition] |
| 404 | NOT_FOUND | [condition] |
```

Save API documentation to `reference/api.md` or `docs/api/`.

## Do NOT

- Expose database IDs or internal field names directly (use UUIDs or slugs)
- Return different response shapes for the same endpoint based on context
- Use verbs in URLs (`/getUser`) when HTTP methods express the action
- Return 200 with an error body. Use proper status codes.
- Design the API around the database schema. Design it around consumer needs.
- Forget to document rate limits, authentication, and error codes from the start
