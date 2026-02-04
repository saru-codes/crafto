# Database Schema (MVP)

## Tenancy + Settings
- sites: id, name, slug, status, created_at
- site_domains: id, site_id, domain, is_primary
- site_settings: id, site_id, key, value_json

## Builder
- pages: id, site_id, title, slug, seo_title, seo_description, published_at
- page_sections: id, page_id, type, sort_order, props_json

## Blog
- posts: id, site_id, title, slug, content, excerpt, featured_image_id, published_at
- categories: id, site_id, name, slug
- tags: id, site_id, name, slug
- post_category (pivot)
- post_tag (pivot)

## Listings
- listing_types: id, site_id, name, slug
- attributes: id, listing_type_id, key, label, field_type, options_json, is_filterable, is_sortable
- listings: id, site_id, listing_type_id, title, slug, description, data_json, published_at
- listing_media (optional pivot if not using media library directly)

## Ecommerce
- products: id, site_id, title, slug, description, price, compare_at_price, status
- product_variants (optional MVP): id, product_id, sku, price, stock
- carts: id, site_id, session_id, data_json
- orders: id, site_id, number, status, subtotal, total, currency, customer_json, stripe_ref, created_at
- order_items: id, order_id, product_id, title, qty, price
