# API Overview 123

Our API is REST-based and uses JSON for both requests and responses.

## Base URL

```
https://api.example.com/v1
```

## Authentication

All requests must include an `Authorization: Bearer <token>` header.
See [docs/auth/tokens.md](../auth/tokens.md) for token generation.

## Rate limits

- 1000 requests per hour per token
- Burst up to 100 per minute

## Versioning

API version is in the URL path. Current version: `v1`.

## Error responses

All error responses follow this format:

```json
{
  "error": {
    "code": "invalid_request",
    "message": "The 'limit' parameter must be between 1 and 100",
    "param": "limit"
  }
}
```

Common error codes:

- `invalid_request` — malformed request
- `unauthorized` — missing or invalid token
- `forbidden` — token does not have required scope
- `not_found` — resource does not exist
- `rate_limited` — request rate exceeded
