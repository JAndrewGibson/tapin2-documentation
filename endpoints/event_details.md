# Event Details

Retrieve detailed metadata for a specific event by its ID.

- **Endpoint**: `v2/venues/{venueId}/events/{eventId}`
- **Method**: `GET`
- **Authentication**: Required (`Key` header)

## Parameters

| Name | Type | Located In | Description |
| :---| :---| :---| :---|
| `venueId` | Integer | Path | The unique identifier for the venue. |
| `eventId` | Integer | Path | The unique identifier for the event. |

## Response Structure

Returns a single event object. The structure is identical to the [Current Event](events_current.md) endpoint.

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
{
    "id": 188698,
    "title": "Example Event",
    "startDate": "04/29/2026 5:00 PM",
    "orderingStartDate": "04/29/2026 3:30 PM",
    "endDate": "04/30/2026 12:30 AM",
    "taxExempt": false,
    "isLastCall": false,
    "isCurrent": true,
    "eventType": {
        "id": 40,
        "title": "EXAMPLE_TYPE",
        "priceLevelId": 23
    }
}
```

## Venue-Specific Notes

- **Price Levels**: The `priceLevelId` within the `eventType` object is critical for correctly calculating product prices for this specific event.
- **Reporting**: The `includeInReports` field indicates if orders from this event should be included in financial exports.



## Related Endpoints

- [Current Event](events_current.md)
- [Events Range](events_range.md)
- [Get Products by Event](products_event.md)

---
[🔗 View Original Documentation](https://api.tapin2.co/Help/Api/GET-v2-venues-venueId-events-eventId)

[← Back to Endpoint Registry](../README.md)
