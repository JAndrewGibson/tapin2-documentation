# GET v2/venues/{venueId}/orders/modified/{fromDate}/{fromMins}/{toDate}/{toMins}

- **Endpoint**: `v2/venues/{venueId}/orders/modified/{fromDate}/{fromMins}/{toDate}/{toMins}?addDayToEndOfRange={addDayToEndOfRange}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

> [!WARNING]
> **Deficient Endpoint**: This endpoint is non-functional or blocked in the sandbox environment.

## Observed Sandbox Behavior

*   **Status Code**: `400` (Timeout / Latency Error)
*   **Identified Issue**: Consistently times out or returns bad request in the sandbox environment when processing large queries or dates, indicating high latency or database performance limitations.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-orders-modified-fromDate-fromMins-toDate-toMins)

[← Back to Endpoint Registry](../README.md)
