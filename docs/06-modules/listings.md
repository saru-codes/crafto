# Module: Listings (Directory)

## Goal
Support directories like properties/jobs/services with fast search and filters.

## Model
- listing_types define a directory (e.g., "Properties")
- attributes define fields (price, location, bedrooms...)
- listings store values in data_json

## Filters/Search
Use Meilisearch faceted search.
- Facets: category, location, price ranges, dynamic attributes
- Sorting: newest, price asc/desc, featured

## Public routes (example)
- /{listingTypeSlug}
- /{listingTypeSlug}/{listingSlug}
