# Global Categories

Retrieve a global list of all product categories.

- **Endpoint**: `{version}/Category`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Status: Known Deficiency

Probing `v2/Category` returns a `401 Unauthorized` error with standard venue API keys. This endpoint appears to require global administrative permissions and is not accessible for venue-level integrations.

For venue-specific categories, use [v2/venues/{venueId}/locations/{locationId}/categories](categories.md) instead.

---
[← Back to Endpoint Registry](../README.md)
