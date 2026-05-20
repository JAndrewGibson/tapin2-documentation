# GET v2/venues/{venueId}/events/{fromDate}/{fromMins}/{toDate}/{toMins}/preorders

Retrieve details for the specified endpoint.

- **Endpoint**: `v2/venues/{venueId}/events/{fromDate}/{fromMins}/{toDate}/{toMins}/preorders?addDayToEndOfRange={addDayToEndOfRange}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `fromDate` | String | Path | The parameter in path. |
| `fromMins` | String | Path | The parameter in path. |
| `toDate` | String | Path | The parameter in path. |
| `toMins` | String | Path | The parameter in path. |
| `addDayToEndOfRange` | Boolean | Query | Optional query parameter. |


## Response Structure

Returns an empty or simple response.

## Example Response (Sanitized)

```json
[]
```

## Venue-Specific Notes

- **Sandbox Status**: Active and functional.
- **Payload Size**: The live sandbox returns a valid data payload.

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-events-fromDate-fromMins-toDate-toMins-preorders)

[← Back to Endpoint Registry](../README.md)
