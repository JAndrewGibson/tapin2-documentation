# GET v2/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}

- **Endpoint**: `v2/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

> [!WARNING]
> **Deficient Endpoint**: This endpoint is non-functional or blocked in the sandbox environment.

## Observed Sandbox Behavior

*   **Status Code**: `500` (500 Internal Server Error)
*   **Identified Issue**: Consistently returns a 500 Internal Server Error in the sandbox environment, indicating a potential null pointer or configuration failure on the server synchronization layer.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-reports-reportType-fromDate-toDate)

[← Back to Endpoint Registry](../README.md)
