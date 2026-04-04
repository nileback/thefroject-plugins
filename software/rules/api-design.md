---
description: API design standards
globs:
  - "src/api/**"
  - "src/handlers/**"
---

# API Design Rules

- Use consistent naming conventions for endpoints and fields
- Return appropriate HTTP status codes (don't use 200 for errors)
- Include pagination for list endpoints
- Version APIs when making breaking changes
- Document all endpoints with request/response examples
- Validate request bodies against schemas
- Use consistent error response format across all endpoints
