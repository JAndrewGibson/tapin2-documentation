# GET v4/venues/{venueId}/orders/small/modified/{fromDate}/{toDate}

- **Endpoint**: `v4/venues/{venueId}/orders/small/modified/{fromDate}/{toDate}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

> [!WARNING]
> **Deficient Endpoint**: This endpoint is non-functional or blocked in the sandbox environment.

## Observed Sandbox Behavior

*   **Status Code**: `-1` (Timeout / Latency Error)
*   **Identified Issue**: Consistently times out or returns bad request in the sandbox environment when processing large queries or dates, indicating high latency or database performance limitations.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v4-venues-venueId-orders-small-modified-fromDate-toDate)

[← Back to Endpoint Registry](../README.md)
