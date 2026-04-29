# Events Range

Retrieve a list of events within a specific date range for a venue.

- **Endpoint**: `v2/venues/{venueId}/events/{minDate}/{maxDate}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :--- | :--- | :--- | :--- |
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `minDate` | String | Path | Start of the date range (`YYYY-MM-DD`). |
| `maxDate` | String | Path | End of the date range (`YYYY-MM-DD`). |

## Response Structure

Returns an array of event objects. The structure is identical to the [Current Event](events_current.md) endpoint.

| Field | Type | Description |
| :--- | :--- | :--- |
| `id` | Integer | Unique identifier for the event. |
| `title` | String | Name of the event. |
| `startDate` | String | Scheduled start time. |
| `isCurrent` | Boolean | Whether the event is currently active. |
| `eventType` | Object | Metadata about the event category. |

## Example Response (Sanitized)

```json
[
    {
        "id": 10001,
        "title": "Example Event A",
        "startDate": "04/25/2026 7:00 PM",
        "isCurrent": false,
        "eventType": {
            "id": 5,
            "title": "EXAMPLE_CATEGORY_A",
            "priceLevelId": 10
        }
    },
    {
        "id": 10002,
        "title": "Example Event B",
        "startDate": "04/27/2026 8:00 PM",
        "isCurrent": false,
        "eventType": {
            "id": 6,
            "title": "EXAMPLE_CATEGORY_B",
            "priceLevelId": 20
        }
    }
]
```

## Venue-Specific Notes

- **Date Formatting**: Ensure dates in the path are formatted as `YYYY-MM-DD`.
- **Preorder Windows**: For suite-based venues, this endpoint is often used to show customers a calendar of upcoming games for advanced ordering.

---
[← Back to Endpoint Registry](../README.md)
