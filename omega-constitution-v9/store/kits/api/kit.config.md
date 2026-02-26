# KIT AUTO-ACTIVATION CONFIG

**Kit:** API  
**Activates when:** `CONTEXT.md` → Project Type = API / Backend Service  
**Subordinate to:** All Constitution files

## Files Included
- `API_KIT.md` — RESTful structure, auth, rate limiting, versioning, errors, pagination, health checks, webhooks, idempotency, CORS, monitoring

## What This Kit Provides
The agent uses these patterns as starting points for:
- RESTful endpoint structure and naming
- Authentication pattern selection
- Rate limiting tier definitions
- API versioning strategy
- Error response format standardisation
- Pagination patterns
- HTTP status code usage
- Health check endpoint design
- Webhook signature and retry patterns
- Idempotency key implementation
- CORS configuration
- Monitoring and alerting requirements

## Override Rules
- If TECH_STACK.md specifies GraphQL instead of REST, adapt patterns accordingly
- If INTERFACES.md defines a different error format, INTERFACES.md wins
- If SECURITY.xml conflicts with any kit pattern, SECURITY.xml wins (always)
