# Unprinted Orders (V1)

Legacy endpoint for retrieving unprinted orders.

- **Endpoint**: `v1/venues/{venueId}/orders/unprinted`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Status: Known Deficiency

This endpoint currently returns a `404 Not Found` error in the sandbox environment. Probes indicate that the V1 order system is legacy and unprinted activity should be monitored via the standard `v2/venues/{venueId}/orders/unprinted` endpoint.

---
[← Back to Endpoint Registry](../README.md)
