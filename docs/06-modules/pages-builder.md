# Module: Pages Builder (MVP)

## Concept
A Page is composed of ordered Sections.
Each section has:
- type: string (hero, features, faq, etc.)
- props: JSON (title, subtitle, image, buttons, etc.)

## Admin (Filament)
- Pages CRUD
- Add/remove/reorder sections
- Edit section props (forms per section type)
- Preview and publish

## Rendering (Blade)
- Load page by slug
- For each section: render matching Blade component
Example mapping:
- hero -> resources/views/sections/hero.blade.php
- features -> resources/views/sections/features.blade.php

## MVP section library
- hero
- features
- gallery
- testimonials
- pricing
- faq
- contact
- footer_cta
