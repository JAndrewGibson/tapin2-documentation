# Location Print Queue

Retrieve a list of pending print jobs for a specific location.

- **Endpoint**: `v3/venues/{venueId}/locations/{locationId}/print`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `locationId` | Integer | Path | The unique identifier for the location. |

## Response Structure

Returns an array of print job objects.

*Note: In active environments, this list contains the raw data to be sent to thermal printers or KDS screens.*

## Example Response (Sanitized)

```json
[]
```

## Venue-Specific Notes

- **Polling**: Printers and KDS controllers typically poll this endpoint at high frequency (1-3 seconds) to pull new tickets.
- **Data Format**: The print jobs often contain ESC/POS commands or raw text for the printer.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v3-venues-venueId-locations-locationId-print)

[← Back to Endpoint Registry](../README.md)
