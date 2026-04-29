# Tabs Unprinted

Retrieve a list of tabs that have not yet been printed or acknowledged.

- **Endpoint**: `v2/venues/{venueId}/tabs/unprinted`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Status: Known Deficiency

This endpoint currently returns a `404 Not Found` error in the sandbox environment. It is possible that unprinted tab activity is now handled through the unified order fulfillment system or requires specific venue configuration that is not active in this sandbox.

---
[← Back to Endpoint Registry](../README.md)
