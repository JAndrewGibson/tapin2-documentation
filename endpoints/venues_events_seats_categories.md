# GET v2/venues/{venueId}/events/{eventId}/seats/{seatId}/categories

- **Endpoint**: `v2/venues/{venueId}/events/{eventId}/seats/{seatId}/categories`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

> [!WARNING]
> **Deficient Endpoint**: This endpoint is non-functional or blocked in the sandbox environment.

## Observed Sandbox Behavior

*   **Status Code**: `500` (500 Internal Server Error)
*   **Identified Issue**: Consistently returns a 500 Internal Server Error in the sandbox environment, indicating a potential null pointer or configuration failure on the server synchronization layer.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-events-eventId-seats-seatId-categories)

[← Back to Endpoint Registry](../README.md)
