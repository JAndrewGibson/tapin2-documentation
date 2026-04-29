# Venue Reports (V1)

Legacy endpoint for retrieving venue sales and performance reports.

- **Endpoint**: `v1/venues/{venueId}/reports/{reportType}/{fromDate}/{toDate}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Status: Known Deficiency

This endpoint currently returns a `500 Internal Server Error` in the sandbox environment. Probes indicate that the V1 reporting system may have been deprecated or replaced by the V2/V3 reporting infrastructure used in the Tapin2 Management Console. 

Users seeking report data should typically use the Management Console export features or inquire about the V2 reporting API availability.

---
[← Back to Endpoint Registry](../README.md)
