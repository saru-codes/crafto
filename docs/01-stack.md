# Crafto Tech Stack (SaaS-capable)

## Backend
- Laravel 11 (PHP 8.3)
- PostgreSQL
- Redis (cache + queues)
- Horizon (queue monitoring)

## Admin Panel
- Filament (CRUD + dashboards)

## Public Site Rendering (MVP)
- Blade + Tailwind (SEO-friendly, fast to ship)

## Search + Filters
- Meilisearch
- Laravel Scout

## Payments
Two layers:
1) Crafto SaaS subscriptions: Stripe + Laravel Cashier (later)
2) Store checkout payments per site: Stripe Checkout (MVP)

## Media Storage (MVP)
- Local storage on VPS using Laravel filesystem (public disk)
- Spatie Media Library for uploads and asset management
- Can migrate to S3-compatible storage (Cloudflare R2 / AWS S3) if scaling requires it

## Observability (recommended)
- Telescope (dev)
- Sentry (prod)
