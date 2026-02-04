# Tenancy Strategy

## MVP: Single Database + site_id everywhere
- Every content table includes `site_id`
- Authorization + policies prevent cross-site access
- Query scopes ensure only current site data is visible

Pros:
- Fast to build and deploy
- Simple backups and migrations

## Future: Stronger isolation (optional)
- Database-per-tenant or schema-per-tenant
- Consider only if scale or compliance demands it

## Domain mapping
- `site_domains` table maps domain -> site
- Middleware resolves site by host header
