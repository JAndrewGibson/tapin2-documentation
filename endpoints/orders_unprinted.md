# Unprinted Orders

Retrieve a list of orders that have been placed but not yet acknowledged by a printer or KDS.

- **Endpoint**: `v2/venues/{venueId}/orders/unprinted`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |

## Response Structure

Returns an array of order objects.

*Note: In active environments, this list is typically short as orders are processed and printed in real-time.*

## Example Response (Sanitized)

```json
[]
```

## Venue-Specific Notes

- **Polling**: Kiosk or terminal applications often poll this endpoint to determine if new orders need to be sent to the kitchen.
- **V1 vs V2**: Version 1 (`v1/venues/{venueId}/orders/unprinted`) is also supported but may return a different JSON schema for the individual order objects.

---
[← Back to Endpoint Registry](../README.md)
