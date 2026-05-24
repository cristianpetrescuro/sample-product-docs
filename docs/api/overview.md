# API Overview

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
