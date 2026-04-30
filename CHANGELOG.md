# Changelog

All notable changes to this documentation project will be noted here.

## [1.1.0] - 2026-04-30
### Added
- Documented `POST {version}/Category` endpoint.
- Identified and documented `500 Internal Server Error` deficiency for category creation in sandbox.
- Updated Category category to 100% completion in registry.
- Documented `POST v2/events/{minDate}/{maxDate}` endpoint.
- Updated `v2/venues/{venueId}/orders/unprinted` documentation with verified response structure and timezone notes.
- Documented `v2/cart/add`, `remove`, and `updatequantity` endpoints (marked as Blocked).
- Identified inconsistent timezone behavior (GET Events uses Local, Orders uses UTC).
- Updated Event category to 100% completion in registry.

## [1.0.0] - 2026-04-29
### Added
- Dark mode support added to GitHub Pages site via Jekyll midnight theme
- Changelog created

## [0.1.0] - 2026-04-29
### Added
- Initial endpoint documentation for Categories, Events, Locations, Products, Venues
- METHODOLOGY.md explaining verification process
- Known deficiencies section in README