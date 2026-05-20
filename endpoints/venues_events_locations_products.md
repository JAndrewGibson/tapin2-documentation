# GET v2/venues/{venueId}/events/{eventId}/locations/{locationId}/products

Retrieve details for the specified endpoint.

- **Endpoint**: `v2/venues/{venueId}/events/{eventId}/locations/{locationId}/products?dob={dob}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The parameter in path. |
| `eventId` | Integer | Path | The parameter in path. |
| `locationId` | Integer | Path | The parameter in path. |
| `dob` | String | Query | Optional query parameter. |


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
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-events-eventId-locations-locationId-products)

[← Back to Endpoint Registry](../README.md)
