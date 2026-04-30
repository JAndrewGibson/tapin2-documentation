# Events Range

Retrieve a list of events within a specific date range for a venue.

- **Endpoint**: `v2/venues/{venueId}/events/{minDate}/{maxDate}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `minDate` | String | Path | Start of the date range (`YYYY-MM-DD`). |
| `maxDate` | String | Path | End of the date range (`YYYY-MM-DD`). |

## Response Structure

Returns an array of event objects. The structure is identical to the [Current Event](events_current.md) endpoint.

| Field | Type | Description |
| :---| :---| :---|
| `id` | Integer | Unique identifier for the event. |
| `title` | String | Public name of the event. |
| `startDate` | String | Scheduled start time (format: `MM/DD/YYYY H:MM AM/PM`). |
| `endDate` | String | Scheduled end time. |
| `orderingStartDate`| String | When customers can begin placing orders. |
| `lastCallDate` | String | When ordering will be disabled. |
| `isLastCall` | Boolean | Whether the event is currently in the "Last Call" period. |
| `isCurrent` | Boolean | Whether this is the active/live event at the venue. |
| `taxExempt` | Boolean | Whether sales for this event are tax-exempt. |
| `eventType` | [Object](../models/event_type.md) | Category/Pricing configuration for the event. |

## Example Response (Sanitized)

```json
[
    {
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
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-events-minDate-maxDate)

[← Back to Endpoint Registry](../README.md)
