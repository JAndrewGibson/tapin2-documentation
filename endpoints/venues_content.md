# GET v2/venues/{venueId}/content/{locationId}

Retrieve details for the specified endpoint.

- **Endpoint**: `v2/venues/{venueId}/content/{locationId}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `locationId` | Integer | Path | The parameter in path. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `venueId` | Integer | Unique identifier for the venue. |
| `locationId` | Integer | Unique identifier for the location. |
| `idleTimeUntilWarning` | Integer | Unique identifier for the record. |
| `orderConfirmationDuration` | Integer |  |
| `timeoutWarningDuration` | Integer | Timestamp in standard formatting. |
| `content` | Object |  |

## Example Response (Sanitized)

```json
{
    "venueId": 1001,
    "locationId": 2001,
    "idleTimeUntilWarning": 0,
    "orderConfirmationDuration": 0,
    "timeoutWarningDuration": 0,
    "content": {}
}
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-content-locationId)

[← Back to Endpoint Registry](../README.md)
