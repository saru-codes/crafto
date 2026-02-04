# Architecture

## Core idea
Crafto is one platform that hosts many websites ("sites"). Each site has its own pages, posts, listings, products, and settings.

## Components
- Admin app (Filament): manages sites + content
- Public renderer (Blade): renders pages/posts/listings/products for visitors
- Search engine (Meilisearch): powers search + faceted filters

## Request flow (public)
1) Request comes to Crafto with a domain (or /s/{siteSlug} in dev)
2) Resolve site from domain/slug
3) Load page by slug
4) Render sections in order using Blade components
5) Cache where possible

## Background jobs
- Indexing job: when listing/product/post changes, update Meilisearch index
- Media processing (optional): image conversions
- Email notifications (orders, admin alerts)

## Scaling notes
- Start single DB with site_id scoping
- Redis cache + queues
- Later: isolate tenants further if needed
