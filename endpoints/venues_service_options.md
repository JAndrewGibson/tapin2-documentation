# GET v2/venues/{venueId}/service/{serviceId}/options

Retrieve details for the specified endpoint.

- **Endpoint**: `v2/venues/{venueId}/service/{serviceId}/options?locationId={locationId}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `serviceId` | Integer | Path | The parameter in path. |
| `locationId` | Integer | Query | Optional query parameter. |


## Response Structure

| Field | Type | Description |
| :---| :---| :---|
| `venueId` | Integer | Unique identifier for the venue. |
| `serviceId` | Integer | Unique identifier for the service. |
| `idleTimeUntilWarning` | Integer | Unique identifier for the record. |
| `orderConfirmationDuration` | Integer |  |
| `timeoutWarningDuration` | Integer | Timestamp in standard formatting. |
| `options` | Array |  |

## Example Response (Sanitized)

```json
{
    "venueId": 1001,
    "serviceId": 1,
    "idleTimeUntilWarning": 0,
    "orderConfirmationDuration": 0,
    "timeoutWarningDuration": 0,
    "options": []
}
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-service-serviceId-options)

[← Back to Endpoint Registry](../README.md)
