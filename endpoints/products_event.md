# Get Products by Event

Retrieve a list of products specific to a particular event.

- **Endpoint**: `v2/venues/{venueId}/events/{eventId}/products`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Status: Known Deficiency

This endpoint currently returns a `404 Not Found` error in the sandbox environment. While logically part of the event management flow, product lists are typically retrieved at the venue or location level using `v2/venues/{venueId}/products` or `v2/venues/{venueId}/locations/{locationId}/products`.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-events-eventId-products)

[← Back to Endpoint Registry](../README.md)
